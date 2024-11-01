# Exerc-cios-de-Fixação
Console.Clear();

Console.WriteLine("Técnico em Informática"); 
Console.WriteLine("---------------------------------------------------");
Console.ForegroundColor = ConsoleColor.Red;
Console.Write("- GSO"); 
Console.WriteLine(" - Gestão de Sistemas Operacionais"); 
Console.ForegroundColor = ConsoleColor.Blue;
Console.Write("- OCA I"); 
Console.WriteLine(" - Operação e Configuração de Aplicativos I"); 
Console.ForegroundColor = ConsoleColor.Green;
Console.Write("- PC I"); 
Console.WriteLine(" - Programação de Computadores I");

Console.ResetColor();
Console.WriteLine("Pressione uma tecla para finalizar...");
Console.ReadKey();

https://github.com/ermogenes/aulas-programacao-csharp/blob/master/content/vscode-v2.md#configurando-o-c-dev-kit

https://gist.github.com/diegoneri/b9cf965f0489b7ac58436ee257b10888#file-program-cs

https://github.com/ermogenes/aulas-programacao-csharp/blob/master/content/saida-console.md#tocar-um-sinal-sonoro

https://github.com/ermogenes/aulas-programacao-csharp/blob/master/content/string.md#sequ%C3%AAncias-de-escape


LINKS E CÓDIGOS DE LINGUAGEM CSHARP (30 de Agosto)
https://gist.github.com/ermogenes/62f9db0816c7771e0fc0f29c72fbbdcb
https://gist.github.com/ermogenes/62f9db0816c7771e0fc0f29c72fbbdcb


https://github.com/diegoneri/NomeNinja/blob/main/Program.cs


LINK E CÓGIGOS DE LINGUAGEM CSHARP (6 de Setembro)

// Divisão
double numerador, denominador, quociente;

Console.Write("Numerador...: ");
numerador = Convert.ToDouble(Console.ReadLine());

Console.Write("Denominador.: ");
denominador = Convert.ToDouble(Console.ReadLine());

quociente = numerador / denominador;

Console.WriteLine($"{numerador:N4} / {denominador:N4} = {quociente:N4}");

https://gist.github.com/ermogenes/c9c1044ef06b51895ae8fab5da12223e


https://github.com/ermogenes/aulas-programacao-csharp





NÚMEROS DIAS E MESES


string mes = "";
int dias = 0;

Console.Clear();
Console.WriteLine("--------------------------");
Console.WriteLine("Dias de um mês");
Console.WriteLine("--------------------------\n");

Console.Write("Informe o mês por extenso:  ");
mes = Console.ReadLine()!.ToUpper();

switch(mes)
{
    case "JANEIRO":
    case "MARÇO":
    case "MAIO":
    case "JULHO":
    case "AGOSTO":
    case "OUTUBRO":
    case "DEZEMBRO":
        dias = 31;
        break;
    case "FEVEREIRO":
        dias = 28;
        break;
    case "ABRIL":
    case "JUNHO":
    case "SETEMBRO":
    case "NOVEMBRO":
        dias = 30;
        break;
    
    default:
        Console.WriteLine("Mês inválido");
        Environment.Exit(0);
        break;
}

Console.WriteLine($"O mês de {mes} possui {dias} dias");

// if (dias > 0)
// {  
// Console.WriteLine($"O mês de {mes} possui {dias} dias");
// }





CALCULADORAAAAAAAA MENU



﻿Console.Clear();
double numero01, numero02, resultado;
string operacao;

Console.WriteLine("-----------");
Console.WriteLine("Calculadora");
Console.WriteLine("-----------\n");

Console.WriteLine("----------------------");
Console.WriteLine("Operações disponíveis:");
Console.WriteLine("----------------------");
Console.WriteLine("A. Soma");
Console.WriteLine("B. Subtração");
Console.WriteLine("C. Multiplicação");
Console.WriteLine("D. Divisão");
Console.WriteLine("----------------------\n");

Console.Write("Operação: ");
operacao = Console.ReadLine()!.ToUpper();
Console.Write("Número 01: ");
numero01 = Convert.ToDouble(Console.ReadLine());
Console.Write("Número 02: ");
numero02 = Convert.ToDouble(Console.ReadLine());

switch(operacao)
{
    case "A":
        resultado = numero01 + numero02;
        break;
    case "B":
        resultado = numero01 - numero02;
        break;
    case "C":
        resultado = numero01 * numero02;
        break;
    case "D":
        resultado = numero01 / numero02;
        break;
    default:
        Console.WriteLine("Operação não suportada!");
        return;
}

Console.WriteLine($"Resultado: {resultado:N4}");




BHASKARA


﻿double a, b, c, delta, x1, x2;

Console.WriteLine("-- Equação do segundo grau usando a Fórmula de Bhaskara--\n");

Console.Write("(a): ");
a = Convert.ToDouble(Console.ReadLine());

Console.Write("(b): ");
b = Convert.ToDouble(Console.ReadLine());

Console.Write("(c): ");
c = Convert.ToDouble(Console.ReadLine());

Console.WriteLine();

if (a == 0)
{
    Console.WriteLine("Não equivale a uma equação de segundo grau!");
}
else
{
    delta = b * b - 4 * a * c;

    if (delta < 0)
    {
        Console.WriteLine($"Visto que delta = {delta:N2}, a equação não possui raízes reais!");
    }
    else
    {
        x1 = (-b + Math.Sqrt(delta)) / (2 * a);
        x2 = (-b - Math.Sqrt(delta)) / (2 * a);

        Console.WriteLine($"x1 = {x1:N2} e x2 = {x2:N2}");
    }
}





EXERCÍCIO ALCOOL OU GASOLINAAAAA



Console.Clear();

Console.WriteLine("--- Combustível para Abastecimento: Etanol ou Gasolina? ---\n");

Console.Write("Registre o preço do etanol (R$).....: ");
decimal etanol = Convert.ToDecimal(Console.ReadLine());

Console.Write("Registre o preço da gasolina (R$)...: ");
decimal gasolina = Convert.ToDecimal(Console.ReadLine());

string recomendacao;

if (AbastecerComGasolina(etanol, gasolina))
{
    recomendacao = "Gasolina";
}
else
{
    recomendacao = "Etanol";
}

double razao = RazaoEtanolGasolina(etanol, gasolina) * 100;

Console.WriteLine($"\nO preço do etanol é equivalente a {razao:N1}% do preço da gasolina.");
Console.WriteLine($"\nRecomendação: Realize o abastecimento com {recomendacao.ToUpper()}.");

double RazaoEtanolGasolina(decimal precoEtanol, decimal precoGasolina)
{
    return Convert.ToDouble(precoEtanol / precoGasolina);
}

bool AbastecerComGasolina(decimal precoEtanol, decimal precoGasolina)
{
    const double MinRazaoUsoGasolina = 0.73;
    return RazaoEtanolGasolina(precoEtanol, precoGasolina) >= MinRazaoUsoGasolina;
}
 
