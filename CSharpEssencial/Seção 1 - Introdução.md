# Seção 1 - Introdução

### A linguagem C#

O C# é uma linguagem de programação moderna, open source, flexivel, orientada a objetos e de tipo seguro que permite criar diversos tipos de aplicativos, seguros e robustos que são executados no .NET

A sua sintaxe orientada a objetos foi baseada em C++ e inclui influencias de outras linguagens de programação como Object Pascal e Java

O C# é uma linguagem de programação usada para criar programas atraves da escrita de um codigo fonte em linguagem de alto nivel

Para que o computador entenda o codigo fonte escrito em C# que é uma linguagem considerada de alto nivel é preciso transformar o codigo fonte em um codigo que seja entendido pela maquina 

codigo executavel… esse processo é conhecido como compilação.

Fase de Compilação → Transforma o codigo fonte de um programa C# para um codigo executavel, que é o codigo que a maquina entende, usando um compilador.

Quando se cria um codigo fonte em C# e esse codigo fonte passa pelo processo de compilação,  esse processo transforma o codigo C# em um codigo intermediario IL ou bytecode. Esse codigo intermediario é executado pelo CLR da plataforma dotnet, criando varios arquivos que são chamados de assemblies dessa forma a CLR realiza a execução Just In Time(JIT) para converter o codigo CIL em codigo de maquina que o sistema operacional pode executar diretamente

OBS: Após todo o processo de compilação sempre será gerado um arquivo .exe ou .dll

Fase de Execução → O CLR faz o gerenciamento do codigo IL que foi gerado no processo de compilação

OBS: O compilador JIT traduz codigo IL para o codigo de maquina no momento que o programa será executado usando a “maquina virtual” de cada ambiente 

IL → Corresponde a o codigo intermediario que é gerado na fase de compilação e antes da fase de execução.

Caracteristica C# 

→ Simples e poderosa

→ Fortemente tipada

→ Possui controle de versões - onde cada assembli gerado exe ou dll tem informação da versão do codigo permitindo a coexistencia de dois assemblies de versões diferentes no mesmo ambiente

→ Suporte a codigo legado

→ Flexibilidade

→ O gerenciamento da memoria é feito pelo garbage collector , reduzindo as chances de o desenvolvedor cometer erros

→ Linguagem orientada a objetos

OBS: As palavras reservadas da linguagem não podem ser usadas como identificadores a menos que incluam @ como prefixo. EX: @as

OBS: É chamado de identificador os nomes que são atribuidos a classes, propriedades, variaveis e outros recursos

→ Diferenciam maiusculos de minusculos (case sensitive)

→ Permitem caractere unicode

→ os identificadores não podem conter mais de 512 caracteres

```csharp
// Comentario de Linha
/**/ Bloco de comentario
{} Delimitador de bloco de comandos 
; Terminação de comandos e instruções
= Atribuição
== Comparação ou igualdade
```

### Organização de código

Quando é criado um programa na linguagem C# e é executado o processo de compilação, é gerado um arquivo final com a extensão .exe ou .dll. Esse arquivo possui o nome de assembly

assembly → arquivo fisico onde o .exe significa arquivo executavel e o .dll é um arquivo que pode ser usado por mais de um programa

namespaces → são containers para as classes e outros namespaces, usamos namespaces para agrupar as classes relacionadas

Com a utilização de namespaces é possivel se ter classes de mesmo nome dentro de  um mesmo projeto.

Para refernciar a classe deve ser usado o nome completo

```csharp
nome_donamespace.nome_da_classe
```

A diretiva using simplifica o uso dos namespaces

Solution → é um container para projetos, pode conter um ou mais projetos

Para se executar qualquer programa feito na linguagem C# será preciso do .NET runtime

OBS: O .NET SDK inclui o .NET runtime

Versões C# e as Versões do .NET

| Versões da Plataforma | Versões da Linguagem C# | Versões do Visual studio |
| --- | --- | --- |
| .NET 7.x | C# 11 | VS 2022 |
| 6 | 10 | 19 |
| 5 | 9 | 19 |
| 3 | 8 | 17 |
| 2 | 7.3 | 17 |
| .NET Standard 2.1 | 8.0 | 19 |
| 2.0 | 7.3 | 17 |
| 1 | 7.3 | 17 |
| .NET Framework | 7.3 | 17 |

OBS: A versão do C# depende da versão do compilador fornecida com o .NET SDK

Os recursos abstraidos pelo top level statement a partir do .NET 6 é consequencia do uso de namespaces globais e as diretivas using implicitas. Onde o compilador adiciona automaticamente um conjunto de diretivas usings na base do projeto que é criado, de forma global, não precisando ser declararados. É possivel ver essa propriedade pelo arquivo.csproj na tag <InplicitUsings></InplicitUsings>

Por padrão agora novos projetos começam com um arquivo chamado `GlobalUsings.g.cs` onde existem os `global using`s que ele usará. Você pode mudar o que está lá no arquivo (ainda que o mais recomendado seja não mexer diretamente neles.

Pode até mesmo mudar o *template* que é usado para gerá-lo, mas não recomendo fazer, se for o caso crie um *template* novo e passe usar no lugar.

Se quiser que não crie isso pode usar `--use-program-main` no `dotnet` CLI. Ou fazer pelo Visual Studio

Além disso é possível configurar no projeto que algum deles não devem ser usados implicitamente:

Fonte: Stack Overflow

Não confunda usings implícitos com usings globais. Esses são relacionados, mas coisas separadas. Você pode ter um sem o outro, ou ambos, ou nenhum.

Imagino que os usings implícitos não são especificados em um arquivo no projeto, caso contrário, não seriam mais implícitos.

Quanto aos usings globais, qualquer declaração de using prefixada com "global" está disponível em todo o projeto. Eles não precisam estar em nenhum arquivo específico, você pode colocá-los todos em Program.cs se quiser (não estou dizendo que você deve). Na prática, você vai querer seu próprio Imports.cs ou Usings.cs, não tenho certeza se a comunidade convergiu em um nome de arquivo nesse estágio inicial.

Fonte: Reddit

### Versões SDK no .NET Instaladas

```powershell
C:\Program Files\dotnet\sdk
```

```powershell
C:\Program Files\dotnet\shared\Microsoft.NETCore.App
```

```powershell
dotnet --list-sdks
```

```powershell
dotnet --list-runtimes
```

Escolher a versão do .NET SDK

criar um arquivo global.json na raiz da pasta

para criar um arquivo global.json usa-se o comando 

```powershell
dotnet new globaljson --sdk-version <versao> --force
```

```json
{
 "sdk": {
         "version":"versao"
	}
}
```

Se nenhum arquivo global.json for encontrado ou o arquivo global.json não especificar uma versão do SDK, será usada a versão mais recente instalada 

Se no global.json especificar um versão do SDK 

- E a versão do sdk especificada for encontrada na maquina a versão será usada
- Se a versão especificada não for encontrada a versão mais recente será usada
- Caso nenhuma versão for encontrada, será dado uma excessão

Para criar um projeto dotnet com uma versão especifica utiliza-se o comando
```powershell
dotnet new tipodetemplate -o nomediretorio -f net<version>
```
Para saber os tipos de template para projetos pode ser executado o comando 
```powershell
dotnet new --list
```
Passando o parametro abaixo na criação do projeto é criado o mesmo sem o top level statement
```powershell
dotnet new tipodetemplate -o nomediretorio --use-program-main
```
