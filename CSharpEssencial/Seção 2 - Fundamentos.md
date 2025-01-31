# Seção 2 - Fundamentos

### Tipos de Dados

Tipo de dado por referencia → Não armazena os dados diretamente e cada variavel contem uma referencia no local da memoria onde os dados estão armazenados

Contem um ponteiro para outro local na memoria onde está armazenado o valor

São armazenados na memoria Heap

- object
- string
- dynamic
- class

Tipo de dados por valor → Armazena diretamente seus dados e cada variavel tem sua propriea copia dos dados 

Contem os dados na sua propria alocação de memoria

São armazenados na memoria Stack(LIFO)

- bool
- char
- numericos - inteiros - ponto flutuante
- enum
- DateTime

Uma variavel deve ser declarada antes de ser usada

Para declarar uma variavel deve ser definido

O tipo de dado da variavel

O nome da variavel (identificador)

A atribuição de valor (opcional)

```csharp
int valor = 1234;

int valor;

```

OBS:  Quando a variavel é declarada e não inicializada o compilador atribui a ela o valor padrão do tipo definido.

Para a declaração de uma constante é utilizado a palavra reservada const

```csharp
	const int valor = 1234;
```

### Tipo numerico integral

São tipos por valor 

Dão suporte a operadores aritimeticos de comparação - ≥ ≤ ≠ ==

O valor padrão de cada tipo integral é 0 (zero)

| palavra-chave/tipo C# | Intervalo | Tamanho | Tipo .NET |
| --- | --- | --- | --- |
| `sbyte` | -128 a 127 | Inteiro de 8 bits com sinal | [System.SByte](https://learn.microsoft.com/pt-br/dotnet/api/system.sbyte) |
| `byte` | 0 a 255 | Inteiro de 8 bits sem sinal | [System.Byte](https://learn.microsoft.com/pt-br/dotnet/api/system.byte) |
| `short` | -32.768 a 32.767 | Inteiro de 16 bits com sinal | [System.Int16](https://learn.microsoft.com/pt-br/dotnet/api/system.int16) |
| `ushort` | 0 a 65.535 | Inteiro de 16 bits sem sinal | [System.UInt16](https://learn.microsoft.com/pt-br/dotnet/api/system.uint16) |
| `int` | -2.147.483.648 a 2.147.483.647 | Inteiro assinado de 32 bits | [System.Int32](https://learn.microsoft.com/pt-br/dotnet/api/system.int32) |
| `uint` | 0 a 4.294.967.295 | Inteiro de 32 bits sem sinal | [System.UInt32](https://learn.microsoft.com/pt-br/dotnet/api/system.uint32) |
| `long` | -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 | Inteiro assinado de 64 bits | [System.Int64](https://learn.microsoft.com/pt-br/dotnet/api/system.int64) |
| `ulong` | 0 a 18.446.744.073.709.551.615 | Inteiro de 64 bits sem sinal | [System.UInt64](https://learn.microsoft.com/pt-br/dotnet/api/system.uint64) |
| `nint` | Depende da plataforma (computada em runtime) | Inteiro de 32 bits ou de 64 bits com sinal | [System.IntPtr](https://learn.microsoft.com/pt-br/dotnet/api/system.intptr) |
| `nuint` | Depende da plataforma (computada em runtime) | Inteiro de 32 bits ou de 64 bits sem sinal | [System.UIntPtr](https://learn.microsoft.com/pt-br/dotnet/api/system.uintptr) |

Não importa se definir o tipo pela palavra chave ou pelo tipo .NET

### Tipos predefinidos numericos de ponto flutuante

São tipos de valor

O valor padrão é 0 (zero)

Dão suporte a operadores aritimeticos de comparação

O tipo double é usado para calculos cientificos e o decimal para calculos financeiros

Podem ser inicializados utilizando literais

Quando não utiliza o sufixo o compilador infere que o tipo será tratado como double

| palavra-chave/tipo C# | Intervalo aproximado | Precisão | Tamanho | Tipo .NET |
| --- | --- | --- | --- | --- |
| `float` | ±1,5 x 10−45 para ±3,4 x 1038 | ~6 a 9 dígitos | 4 bytes | [System.Single](https://learn.microsoft.com/pt-br/dotnet/api/system.single) |
| `double` | ±5.0 × 10−324 to ±1.7 × 10308 | ~15 a 17 dígitos | 8 bytes | [System.Double](https://learn.microsoft.com/pt-br/dotnet/api/system.double) |
| `decimal` | ±1,0 x 10-28 para ±7,9228 x 1028 | 28 a 29 dígitos | 16 bytes | [System.Decimal](https://learn.microsoft.com/pt-br/dotnet/api/system.decimal) |
- O literal sem sufixo ou com os sufixos `d` ou `D` é do tipo `double`
- O literal com os sufixos `f` ou `F` é do tipo `float`
- O literal com os sufixos `m` ou `M` é do tipo `decimal`

### Tipos predefinidos não numericos bool e char

São tipos de valor 

O tipo bool pode ser obtido como resultado de operações de comparação e de igualdade

O valor padrão do tipo bool é false

O valor padrão do tipo `char` é `\0`, ou seja, U+0000.

| Tipo | Intervalo | Tamanho | Tipo .NET |
| --- | --- | --- | --- |
| `char` | U+0000 a U+FFFF | 16 bits | [System.Char](https://learn.microsoft.com/pt-br/dotnet/api/system.char) |

### Tipos predefinidos por referencia

São tipos de referencia

O valor padrão é null

| Palavra chave | Definição | Tipo .NET |
| --- | --- | --- |
| string | Representa uma sequencia de zeros ou mais caracteres unicode são imutaveis o valor deve ser definido dentor de aspas duplas | System.String |
| object | É o tipo base para todos os outros tipos | System.Object |
| dynamic | São resolvidos em tempo de execução Se comporta como object na maioria dos casos | System.Object |

### Tratamento de Datetime

A struct DateTime representa um momento no tempo geralmente expresso como uma data e hora

É um tipo de valor 

Possui um valor padrão - 01/01/0001 00:00:00

Ao usar um datetime a representação do mesmo é feita no formato que é configurado para data e hora local  como está definido no sistema operacional que é rodado o codigo.

Para obter a data e hora atual é usado a propriedade Now.

```csharp
DateTime data = new DateTime(2022,09,04)
```

Quando não se especifica a hora minuto e segundo são atribuidos com valor 0

Para exepresar a data é a hora é usado (aaaa,mm,dd, hh, mm, ss)

Principais propriedades

| Propriedade | Descrição |
| --- | --- |
| [Date](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.date?view=net-8.0#system-datetime-date) | Obtém o componente de data da instância. |
| [Day](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.day?view=net-8.0#system-datetime-day) | Obtém o dia do mês representado por essa instância. |
| [DayOfWeek](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.dayofweek?view=net-8.0#system-datetime-dayofweek) | Obtém o dia da semana representado por essa instância. |
| [DayOfYear](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.dayofyear?view=net-8.0#system-datetime-dayofyear) | Obtém o dia do ano representado por essa instância. |
| [Hour](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.hour?view=net-8.0#system-datetime-hour) | Obtém o componente de hora da data representada por essa instância. |
| [Kind](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.kind?view=net-8.0#system-datetime-kind) | Obtém um valor que indica se a hora representada por essa instância é baseada na hora local, no UTC (Tempo Universal Coordenado) ou em nenhum dos dois. |
| [Microsecond](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.microsecond?view=net-8.0#system-datetime-microsecond) | O componente microssegundos, expresso como um valor entre 0 e 999. |
| [Millisecond](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.millisecond?view=net-8.0#system-datetime-millisecond) | Obtém o componente de milissegundos da data representada por essa instância. |
| [Minute](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.minute?view=net-8.0#system-datetime-minute) | Obtém o componente de minuto da data representada por essa instância. |
| [Month](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.month?view=net-8.0#system-datetime-month) | Obtém o componente de mês da data representada por essa instância. |
| [Nanosecond](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.nanosecond?view=net-8.0#system-datetime-nanosecond) | O componente nanossegundos, expresso como um valor entre 0 e 900 (em incrementos de 100 nanossegundos). |
| [Now](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.now?view=net-8.0#system-datetime-now) | Obtém um objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) definido como a data e hora atuais neste computador, expressas como a hora local. |
| [Second](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.second?view=net-8.0#system-datetime-second) | Obtém o componente de segundos da data representada por essa instância. |
| [Ticks](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.ticks?view=net-8.0#system-datetime-ticks) | Obtém o número de tiques que representam a data e hora dessa instância. |
| [TimeOfDay](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.timeofday?view=net-8.0#system-datetime-timeofday) | Obtém a hora do dia para esta instância. |
| [Today](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.today?view=net-8.0#system-datetime-today) | Obtém a data atual. |
| [UtcNow](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.utcnow?view=net-8.0#system-datetime-utcnow) | Obtém um objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) definido como a data e hora atual neste computador, expressas como o UTC (Tempo Universal Coordenado). |
| [Year](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.year?view=net-8.0#system-datetime-year) | Obtém o componente de ano da data representada por essa instância. |

Metodos

| Metodo | Descrição |
| --- | --- |
| [Add(TimeSpan)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.add?view=net-8.0#system-datetime-add(system-timespan)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o valor do [TimeSpan](https://learn.microsoft.com/pt-br/dotnet/api/system.timespan?view=net-8.0) especificado ao valor dessa instância. |
| [AddDays(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.adddays?view=net-8.0#system-datetime-adddays(system-double)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de dias ao valor dessa instância. |
| [AddHours(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addhours?view=net-8.0#system-datetime-addhours(system-double)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de horas ao valor dessa instância. |
| [AddMicroseconds(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addmicroseconds?view=net-8.0#system-datetime-addmicroseconds(system-double)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de microssegundos ao valor dessa instância. |
| [AddMilliseconds(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addmilliseconds?view=net-8.0#system-datetime-addmilliseconds(system-double)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de milissegundos ao valor dessa instância. |
| [AddMinutes(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addminutes?view=net-8.0#system-datetime-addminutes(system-double)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de minutos ao valor dessa instância. |
| [AddMonths(Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addmonths?view=net-8.0#system-datetime-addmonths(system-int32)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de meses ao valor dessa instância. |
| [AddSeconds(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addseconds?view=net-8.0#system-datetime-addseconds(system-double)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de segundos ao valor dessa instância. |
| [AddTicks(Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addticks?view=net-8.0#system-datetime-addticks(system-int64)) | Retorna uma nova [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número de tiques especificado no valor dessa instância. |
| [AddYears(Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.addyears?view=net-8.0#system-datetime-addyears(system-int32)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que adiciona o número especificado de anos ao valor dessa instância. |
| [Compare(DateTime, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.compare?view=net-8.0#system-datetime-compare(system-datetime-system-datetime)) | Compara duas instâncias do [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) e retorna um inteiro que indica se a primeira instância é anterior, a mesma ou posterior à segunda instância. |
| [CompareTo(DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.compareto?view=net-8.0#system-datetime-compareto(system-datetime)) | Compara o valor dessa instância com um valor [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) especificado e retorna um inteiro que indica se essa instância é anterior, igual ou posterior ao valor [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) especificado. |
| [CompareTo(Object)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.compareto?view=net-8.0#system-datetime-compareto(system-object)) | Compara o valor dessa instância com um objeto especificado que contém um valor [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) especificado e retorna um inteiro que indica se essa instância é anterior, igual ou posterior ao valor [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) especificado. |
| [DaysInMonth(Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.daysinmonth?view=net-8.0#system-datetime-daysinmonth(system-int32-system-int32)) | Retorna o número de dias no ano e mês especificado. |
| [Deconstruct(DateOnly, TimeOnly)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.deconstruct?view=net-8.0#system-datetime-deconstruct(system-dateonly@-system-timeonly@)) | Desconstrói essa [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) instância por [DateOnly](https://learn.microsoft.com/pt-br/dotnet/api/system.dateonly?view=net-8.0) e [TimeOnly](https://learn.microsoft.com/pt-br/dotnet/api/system.timeonly?view=net-8.0). |
| [Deconstruct(Int32, Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.deconstruct?view=net-8.0#system-datetime-deconstruct(system-int32@-system-int32@-system-int32@)) | Desconstrói essa [DateOnly](https://learn.microsoft.com/pt-br/dotnet/api/system.dateonly?view=net-8.0) instância por [Year](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.year?view=net-8.0#system-datetime-year), [Month](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.month?view=net-8.0#system-datetime-month)e [Day](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.day?view=net-8.0#system-datetime-day). |
| [Equals(DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.equals?view=net-8.0#system-datetime-equals(system-datetime)) | Retorna um valor que indica se o valor dessa instância é igual ao valor da instância [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) especificada. |
| [Equals(DateTime, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.equals?view=net-8.0#system-datetime-equals(system-datetime-system-datetime)) | Retorna um valor que indica se duas [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) instâncias têm o mesmo valor de data e hora. |
| [Equals(Object)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.equals?view=net-8.0#system-datetime-equals(system-object)) | Retorna um valor que indica se a instância é igual a um objeto especificado. |
| [FromBinary(Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.frombinary?view=net-8.0#system-datetime-frombinary(system-int64)) | Desserializa um valor binário de 64 bits e recria um objeto de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) original serializado. |
| [FromFileTime(Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.fromfiletime?view=net-8.0#system-datetime-fromfiletime(system-int64)) | Converte a hora de arquivo do Windows especificada em uma hora local equivalente. |
| [FromFileTimeUtc(Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.fromfiletimeutc?view=net-8.0#system-datetime-fromfiletimeutc(system-int64)) | Converte a hora de arquivo Windows especificada em uma hora UTC equivalente. |
| [FromOADate(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.fromoadate?view=net-8.0#system-datetime-fromoadate(system-double)) | Retorna um [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) equivalente à Data de Automação OLE especificada. |
| [GetDateTimeFormats()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.getdatetimeformats?view=net-8.0#system-datetime-getdatetimeformats) | Converte o valor dessa instância em todas as representações de cadeia de caracteres com suporte nos especificadores de formato de data e hora padrão. |
| [GetDateTimeFormats(Char)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.getdatetimeformats?view=net-8.0#system-datetime-getdatetimeformats(system-char)) | Converte o valor dessa instância em todas as representações de cadeia de caracteres com suporte no especificador de formato de data e hora padrão especificado. |
| [GetDateTimeFormats(Char, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.getdatetimeformats?view=net-8.0#system-datetime-getdatetimeformats(system-char-system-iformatprovider)) | Converte o valor dessa instância para todas as representações de cadeia de caracteres com suporte pelos especificadores de formato de data e hora e as informações de formatação específicas da cultura especificadas. |
| [GetDateTimeFormats(IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.getdatetimeformats?view=net-8.0#system-datetime-getdatetimeformats(system-iformatprovider)) | Converte o valor dessa instância para todas as representações de cadeia de caracteres com suporte pelos especificadores de formato de data e hora padrão e as informações de formatação específicas da cultura especificadas. |
| [GetHashCode()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.gethashcode?view=net-8.0#system-datetime-gethashcode) | Retorna o código hash para a instância. |
| [GetTypeCode()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.gettypecode?view=net-8.0#system-datetime-gettypecode) | Retorna o [TypeCode](https://learn.microsoft.com/pt-br/dotnet/api/system.typecode?view=net-8.0) para tipo de valor [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0). |
| [IsDaylightSavingTime()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.isdaylightsavingtime?view=net-8.0#system-datetime-isdaylightsavingtime) | Indica se esta instância do [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) está dentro do intervalo de horário de verão para o fuso horário atual. |
| [IsLeapYear(Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.isleapyear?view=net-8.0#system-datetime-isleapyear(system-int32)) | Retorna uma indicação se o ano especificado é um ano bissexto. |
| [Parse(ReadOnlySpan<Char>, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parse?view=net-8.0#system-datetime-parse(system-readonlyspan((system-char))-system-iformatprovider)) | Analisa um intervalo de caracteres em um valor. |
| [Parse(ReadOnlySpan<Char>, IFormatProvider, DateTimeStyles)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parse?view=net-8.0#system-datetime-parse(system-readonlyspan((system-char))-system-iformatprovider-system-globalization-datetimestyles)) | Converte um intervalo de memória que contém uma representação de cadeia de caracteres de uma data e hora em seu [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) equivalente usando as informações de formato e um estilo de formatação específicos da cultura. |
| [Parse(String)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parse?view=net-8.0#system-datetime-parse(system-string)) | Converte a representação de cadeia de caracteres de uma data e hora em seu [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) equivalente usando as convenções da cultura atual. |
| [Parse(String, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parse?view=net-8.0#system-datetime-parse(system-string-system-iformatprovider)) | Converte a representação da cadeia de caracteres de uma data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando as informações de formato específicas da cultura. |
| [Parse(String, IFormatProvider, DateTimeStyles)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parse?view=net-8.0#system-datetime-parse(system-string-system-iformatprovider-system-globalization-datetimestyles)) | Converte a representação de cadeia de caracteres de uma data e hora em seu [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) equivalente usando as informações de formato e um estilo de formatação específicos da cultura. |
| [ParseExact(ReadOnlySpan<Char>, ReadOnlySpan<Char>, IFormatProvider, DateTimeStyles)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parseexact?view=net-8.0#system-datetime-parseexact(system-readonlyspan((system-char))-system-readonlyspan((system-char))-system-iformatprovider-system-globalization-datetimestyles)) | Converte a representação de intervalo especificada de data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando o formato especificado, as informações de formato específicas da cultura e o estilo. O formato da representação de cadeia de caracteres deverá corresponder exatamente ao formato especificado ou uma exceção será gerada. |
| [ParseExact(ReadOnlySpan<Char>, String[], IFormatProvider, DateTimeStyles)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parseexact?view=net-8.0#system-datetime-parseexact(system-readonlyspan((system-char))-system-string()-system-iformatprovider-system-globalization-datetimestyles)) | Converte a representação de intervalo especificada de data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando a matriz de formatos especificada, as informações de formato específicas da cultura e o estilo. O formato da representação de cadeia de caracteres deverá corresponder a, pelo menos, um dos formatos especificados exatamente ou uma exceção será gerada. |
| [ParseExact(String, String, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parseexact?view=net-8.0#system-datetime-parseexact(system-string-system-string-system-iformatprovider)) | Converte a representação de cadeia de caracteres especificada de data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando o formato especificado e as informações de formato específicas da cultura. O formato de representação da cadeia de caracteres deve corresponder exatamente ao formato especificado. |
| [ParseExact(String, String, IFormatProvider, DateTimeStyles)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parseexact?view=net-8.0#system-datetime-parseexact(system-string-system-string-system-iformatprovider-system-globalization-datetimestyles)) | Converte a representação de cadeia de caracteres especificada de data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando o formato especificado, as informações de formato específicas da cultura e o estilo. O formato da representação de cadeia de caracteres deverá corresponder exatamente ao formato especificado ou uma exceção será gerada. |
| [ParseExact(String, String[], IFormatProvider, DateTimeStyles)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.parseexact?view=net-8.0#system-datetime-parseexact(system-string-system-string()-system-iformatprovider-system-globalization-datetimestyles)) | Converte a representação de cadeia de caracteres especificada de um data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando a matriz de formatos, informações de formato específicas da cultura e estilo especificados. O formato da representação de cadeia de caracteres deverá corresponder a, pelo menos, um dos formatos especificados exatamente ou uma exceção será gerada. |
| [SpecifyKind(DateTime, DateTimeKind)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.specifykind?view=net-8.0#system-datetime-specifykind(system-datetime-system-datetimekind)) | Cria um novo objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que tem o mesmo número de tiques que o [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) especificado, mas é designado como hora local, UTC (Tempo Universal Coordenado) ou nenhum dos dois, conforme indicado pelo valor [DateTimeKind](https://learn.microsoft.com/pt-br/dotnet/api/system.datetimekind?view=net-8.0) especificado. |
| [Subtract(DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.subtract?view=net-8.0#system-datetime-subtract(system-datetime)) | Retorna um novo [TimeSpan](https://learn.microsoft.com/pt-br/dotnet/api/system.timespan?view=net-8.0) que subtrai a data e hora especificados do valor dessa instância. |
| [Subtract(TimeSpan)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.subtract?view=net-8.0#system-datetime-subtract(system-timespan)) | Retorna um novo [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) que subtrai a duração especificada do valor dessa instância. |
| [ToBinary()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tobinary?view=net-8.0#system-datetime-tobinary) | Serializa o objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) atual como um valor binário de 64 bits que posteriormente pode ser usado para recriar o objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0). |
| [ToFileTime()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tofiletime?view=net-8.0#system-datetime-tofiletime) | Converte o valor do objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) atual para uma hora de arquivo do Windows. |
| [ToFileTimeUtc()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tofiletimeutc?view=net-8.0#system-datetime-tofiletimeutc) | Converte o valor do objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) atual para uma hora de arquivo do Windows. |
| [ToLocalTime()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tolocaltime?view=net-8.0#system-datetime-tolocaltime) | Converte o valor do objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) atual para a hora local. |
| [ToLongDateString()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tolongdatestring?view=net-8.0#system-datetime-tolongdatestring) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) na representação de cadeia de caracteres de data completa equivalente. |
| [ToLongTimeString()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tolongtimestring?view=net-8.0#system-datetime-tolongtimestring) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) na representação de cadeia de caracteres de hora completa equivalente. |
| [ToOADate()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tooadate?view=net-8.0#system-datetime-tooadate) | Converte o valor dessa instância na data de Automação OLE equivalente. |
| [ToShortDateString()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.toshortdatestring?view=net-8.0#system-datetime-toshortdatestring) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) na representação de cadeia de caracteres de data abreviada equivalente. |
| [ToShortTimeString()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.toshorttimestring?view=net-8.0#system-datetime-toshorttimestring) | Converte o valor do objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) atual na representação de cadeia de caracteres de hora abreviada equivalente. |
| [ToString()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tostring?view=net-8.0#system-datetime-tostring) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) na representação de cadeia de caracteres equivalente usando as convenções de formatação da cultura atual. |
| [ToString(IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tostring?view=net-8.0#system-datetime-tostring(system-iformatprovider)) | Converte o valor do objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) atual para sua representação de cadeia de caracteres equivalente usando as informações de formato específicas da cultura especificada. |
| [ToString(String)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tostring?view=net-8.0#system-datetime-tostring(system-string)) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) na representação de cadeia de caracteres equivalente usando o formato especificado e as convenções de formatação da cultura atual. |
| [ToString(String, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tostring?view=net-8.0#system-datetime-tostring(system-string-system-iformatprovider)) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) na representação de cadeia de caracteres equivalente usando o formato especificado e as informações de formato específicas da cultura. |
| [ToUniversalTime()](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.touniversaltime?view=net-8.0#system-datetime-touniversaltime) | Converte o valor do atual objeto [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) em UTC (Tempo Universal Coordenado). |
| [TryFormat(Span<Byte>, Int32, ReadOnlySpan<Char>, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryformat?view=net-8.0#system-datetime-tryformat(system-span((system-byte))-system-int32@-system-readonlyspan((system-char))-system-iformatprovider)) | Tenta formatar o valor da instância atual como UTF-8 no intervalo de bytes fornecido. |
| [TryFormat(Span<Char>, Int32, ReadOnlySpan<Char>, IFormatProvider)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryformat?view=net-8.0#system-datetime-tryformat(system-span((system-char))-system-int32@-system-readonlyspan((system-char))-system-iformatprovider)) | Tenta formatar o valor da instância de datetime atual para o intervalo de caracteres fornecido. |
| [TryParse(ReadOnlySpan<Char>, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparse?view=net-8.0#system-datetime-tryparse(system-readonlyspan((system-char))-system-datetime@)) | Converte o intervalo de caracteres especificado de uma data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) e retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParse(ReadOnlySpan<Char>, IFormatProvider, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparse?view=net-8.0#system-datetime-tryparse(system-readonlyspan((system-char))-system-iformatprovider-system-datetime@)) | Tenta analisar um intervalo de caracteres em um valor. |
| [TryParse(ReadOnlySpan<Char>, IFormatProvider, DateTimeStyles, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparse?view=net-8.0#system-datetime-tryparse(system-readonlyspan((system-char))-system-iformatprovider-system-globalization-datetimestyles-system-datetime@)) | Converte a representação de intervalo de uma data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando as informações de formato específicas da cultura e o estilo de formatação especificados e retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParse(String, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparse?view=net-8.0#system-datetime-tryparse(system-string-system-datetime@)) | Converte a representação de cadeia de caracteres especificada de uma data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) e retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParse(String, IFormatProvider, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparse?view=net-8.0#system-datetime-tryparse(system-string-system-iformatprovider-system-datetime@)) | Tenta analisar uma cadeia de caracteres em um valor. |
| [TryParse(String, IFormatProvider, DateTimeStyles, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparse?view=net-8.0#system-datetime-tryparse(system-string-system-iformatprovider-system-globalization-datetimestyles-system-datetime@)) | Converte a representação de cadeia de caracteres especificada de uma data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando as informações de formato específicas da cultura e estilo de formatação especificados e retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParseExact(ReadOnlySpan<Char>, ReadOnlySpan<Char>, IFormatProvider, DateTimeStyles, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparseexact?view=net-8.0#system-datetime-tryparseexact(system-readonlyspan((system-char))-system-readonlyspan((system-char))-system-iformatprovider-system-globalization-datetimestyles-system-datetime@)) | Converte a representação de intervalo especificada de data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando o formato especificado, as informações de formato específicas da cultura e o estilo. O formato de representação da cadeia de caracteres deve corresponder exatamente ao formato especificado. O método retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParseExact(ReadOnlySpan<Char>, String[], IFormatProvider, DateTimeStyles, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparseexact?view=net-8.0#system-datetime-tryparseexact(system-readonlyspan((system-char))-system-string()-system-iformatprovider-system-globalization-datetimestyles-system-datetime@)) | Converte o intervalo de caracteres especificado de uma data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) e retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParseExact(String, String, IFormatProvider, DateTimeStyles, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparseexact?view=net-8.0#system-datetime-tryparseexact(system-string-system-string-system-iformatprovider-system-globalization-datetimestyles-system-datetime@)) | Converte a representação de cadeia de caracteres especificada de data e hora em seu equivalente [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando o formato especificado, as informações de formato específicas da cultura e o estilo. O formato de representação da cadeia de caracteres deve corresponder exatamente ao formato especificado. O método retorna um valor que indica se a conversão foi bem-sucedida. |
| [TryParseExact(String, String[], IFormatProvider, DateTimeStyles, DateTime)](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime.tryparseexact?view=net-8.0#system-datetime-tryparseexact(system-string-system-string()-system-iformatprovider-system-globalization-datetimestyles-system-datetime@)) | Converte a representação de cadeia de caracteres especificada de um data e hora no equivalente de [DateTime](https://learn.microsoft.com/pt-br/dotnet/api/system.datetime?view=net-8.0) usando a matriz de formatos, informações de formato específicas da cultura e estilo especificados. O formato da representação da cadeia de caracteres deve corresponder exatamente a um dos formatos especificados pelo menos. O método retorna um valor que indica se a conversão foi bem-sucedida. |

OBS: struct é um tipo parecido com uma classe que é composto por outros tipos e metodos

### Nullable Types

Se tentar atribuir null para uma variavel do tipo de valor o compilador emitirá um erro

A partir da versão 2.0 da linguagem C# foi introduzido o tipo Nullable Type

Nullable Type → É um tipo de valor que pode receber um valor null sendo assim, permitem atribuir o valor null a variaveis que são do tipo por valor

Suportam os valores do tipo definido e o valor null

```csharp
Nullable<T> variavel = null;
```

Para simplificar a declaração é possivel utilizar o operador ?

Exemplo de declaração simplificada

```csharp
int? variavel = null;
```

OBS: os Nullable Types são diferentes do tipo por valor

porque os tipos por valor são tipos não anulaveis e os NullableTypes são tipos anulaveis 

É possivel atribuir o valor de uma variavel de um tipo de valor para um Nullable Type mas não é possivel fazer o contrario.

Para realizar o processo de atribuir um tipo anulavel a um tipo não anulavel utiliza-se o ??

?? → Operador de coalecencia nula retorna o valor do operador esquerdo se ele não for null caso o contrario é avaliado o operando direito e retorna seu resultado

?? não avalia o operando do lado direito se o operando esquerdo for avaliado como não nulo

Propriedades somente leitura HasValue e Value

São usadas para examinar e obter um valor de uma variavel NullableType

HasValue  →  Retorna true se a variavel tiver um valor e false caso o valor seja null

Value → Exibe o valor atribuido

### Formatar Saida de dados

WriteLine() → Metodo que escreve em uma linha e posiciona o cursor na linha de baixo em aplicações do tipo console.

Write() → Escreve no console e permanece como cursor na mesma linha

Concatenação → Utiliza o operador + para concatenar strings 

Interpolação → maneira mais eficiente de concatenar strings e variaveis , atreves do sinal de $ e entre os {} inserir a variavel.

placeholders → usava uma numeração com inicio em 0 e substituia a numeração pelas variaves (não mais utilizado)

Exemplo Interpolação:

```csharp
Console.WriteLine($"Essa eh uma interpolacao de {variavel}");
```

Exemplo de uso de placeholders

```csharp
Console.WriteLine("Esse é o {0} que sera exibido com a idade {1}", nome, idade);
```

### Saida de dados Formatação

Concatenação → É o processo de acrescentar uma cadeia de caracteres no final de outra cadeia de caracteres Para isso é usado o operador +

Exemplo

Interpolação → Usa objetos e expressões para realizar uma interpolação de strings Para isso usa-se o operador $ para indicar a interpolação e {} para conter as variaveis a serem substituidas 

Place Holders → Realiza a concatenação de expressões usando objetos. Para isso usa-se {} e uma numeração iniciada com 0 zero para indicar a ordem de substituição das variaveis que devem ser informadas na ordem a serem exibidas

Exemplo

OBS: A barra invertida é considerado um escape invalido assim como as aspas duplas não podem ser representadas diretamente dentro de uma string.

Sequencia de escape

São combinações de caracteres constituindo de uma barra invertida (\) seguida por uma letra ou por uma combinação de digitos.

| Sequencia Escape | Definição |
| --- | --- |
| \a | Sinal sonoro alerta |
| \b | backspace |
| \f | alimentação de formulario |
| \n | Nova Linha |
| \r | carriage return |
| \t | tabulação horizontal - 5 espaços |
| \v | tabulação vertical |
| \’ | Aspas simples |
| \” | Aspas duplas |
| \\ | barra invertida |
| \? | interrogração |
| \u ooo | Caractere ascii na notação unicode |
| \x hh | Caractere ascii na notação hexagonal |

### Conversão de tipos

A linguagem C# é estaticamente tipada em tempo de compilação 

Após uma variavel ser declarada ela não pode ser declarada novamente

E não pode ser usada para armazenar valores de outro tipo 

A menos que seja feito uma conversão de tipo de dados

O processo de converter um valor de um tipo de dados para outro tipo de dado é chamado de conversão de tipos - Casting

Conversão implicita → O compilador C# converte automaticamente um tipo de dado em outro tipo (Quando a conversãr entre os tipos for compativel)

int → double = prossivel → int usa 4 bytes double usa 8 bytes

byte → 1 byte

short  → 2 bytes

int  → 4 bytes 

long → 8 bytes 

float → 4 bytes

double  → 8 bytes

decimal  → 16 bytes

Toda vez que for converter uma variavel de menor valor de armazenamento para uma de maior valor em bytes é possivel realizar a conversão implicita.

Tipos de conversões implicitas possiveis

| De | Para |
| --- | --- |
| [sbyte](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `short`, `int`, `long`, `float`, `double`, `decimal` ou `nint` |
| [byte](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `nint` ou `nuint` |
| [short](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `int`, `long`, `float`, `double`, ou `decimal` ou `nint` |
| [ushort](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `int`, `uint`, `long`, `ulong`, `float`, `double` or `decimal`, `nint` ou `nuint` |
| [int](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `long`, `float`, `double` ou `decimal`, `nint` |
| [uint](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `long`, `ulong`, `float`, `double` or `decimal`, ou `nuint` |
| [longo](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `float`, `double` ou `decimal` |
| [ulong](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `float`, `double` ou `decimal` |
| [float](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/floating-point-numeric-types) | `double` |
| [nint](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `long`, `float`, `double` ou `decimal` |
| [nuint](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | `ulong`, `float`, `double` ou `decimal` |

Conversão explicita → A conversão tem que ser expressada manualmente de forma explicita no codigo

Exemplo

```csharp
int varInt = (int)varDouble;
```

### O metodo ToString

O metodo ToString() da classe Object retorna uma string que representa o objeto atual

Converte um objeto em sua representação de cadeia de caracteres para exibição

### A classe Convert

Fornece diversos metodos para converter um tipo de dado em outro tipo de dado pertence ao namespace System

Exemplo de utilização 

```csharp
int valorInt = 10

Console.WriteLine(Convert.ToString(valorInt));
```

As conversões de ampliação ou estreitamento entre dois tipos de dados que não resultam em perda de dados terão exito e o metodo retornará um valor do tipo de destino

Quando uma conversão de estreitamento de dados resultar em perda de dados vai ocorrer uma OverFlowException em tempo de exxecução

### Operadores aritimeticos e a classe Math

| Operação | Operador |
| --- | --- |
| Adicao | + |
| Subtracao | - |
| Multimplicação | * |
| Divisao | / |
| Modulo(*) → Retorna o resto de uma divisao | % |

Campos classe Math

| [E](https://learn.microsoft.com/pt-br/dotnet/api/system.math.e?view=net-8.0#system-math-e) | Representa a base logarítmica natural, especificada pela constante, `e`. |
| --- | --- |
| [PI](https://learn.microsoft.com/pt-br/dotnet/api/system.math.pi?view=net-8.0#system-math-pi) | Representa a proporção da circunferência de um círculo ao seu diâmetro, especificada pela constante, π. |
| [Tau](https://learn.microsoft.com/pt-br/dotnet/api/system.math.tau?view=net-8.0#system-math-tau) | Representa o número de radianos em um turno, especificado pela constante, τ. |

Metodos da classe Math

| [Abs(Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-decimal)) | Retorna o valor absoluto de um número de [Decimal](https://learn.microsoft.com/pt-br/dotnet/api/system.decimal?view=net-8.0). |
| --- | --- |
| [Abs(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-double)) | Retorna o valor absoluto de um número de ponto flutuante de precisão dupla. |
| [Abs(Int16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-int16)) | Retorna o valor absoluto de um inteiro com sinal de 16 bits. |
| [Abs(Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-int32)) | Retorna o valor absoluto de um inteiro com sinal de 32 bits. |
| [Abs(Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-int64)) | Retorna o valor absoluto de um inteiro com sinal de 64 bits. |
| [Abs(IntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-intptr)) | Retorna o valor absoluto de um inteiro com sinal nativo. |
| [Abs(SByte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-sbyte)) | Retorna o valor absoluto de um inteiro com sinal de 8 bits. |
| [Abs(Single)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.abs?view=net-8.0#system-math-abs(system-single)) | Retorna o valor absoluto de um número de ponto flutuante de precisão única. |
| [Acos(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.acos?view=net-8.0#system-math-acos(system-double)) | Retorna o ângulo cujo cosseno é o número especificado. |
| [Acosh(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.acosh?view=net-8.0#system-math-acosh(system-double)) | Retorna o ângulo cujo cosseno hiperbólico é o número especificado. |
| [Asin(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.asin?view=net-8.0#system-math-asin(system-double)) | Retorna o ângulo cujo seno é o número especificado. |
| [Asinh(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.asinh?view=net-8.0#system-math-asinh(system-double)) | Retorna o ângulo cujo seno hiperbólico é o número especificado. |
| [Atan(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.atan?view=net-8.0#system-math-atan(system-double)) | Retorna o ângulo cuja tangente é o número especificado. |
| [Atan2(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.atan2?view=net-8.0#system-math-atan2(system-double-system-double)) | Retorna o ângulo cuja tangente é o quociente de dois números especificados. |
| [Atanh(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.atanh?view=net-8.0#system-math-atanh(system-double)) | Retorna o ângulo cuja tangente hiperbólica é o número especificado. |
| [BigMul(Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.bigmul?view=net-8.0#system-math-bigmul(system-int32-system-int32)) | Produz o produto completo de dois números de 32 bits. |
| [BigMul(Int64, Int64, Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.bigmul?view=net-8.0#system-math-bigmul(system-int64-system-int64-system-int64@)) | Produz o produto completo de dois números de 64 bits. |
| [BigMul(UInt64, UInt64, UInt64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.bigmul?view=net-8.0#system-math-bigmul(system-uint64-system-uint64-system-uint64@)) | Produz o produto completo de dois números de 64 bits sem sinal. |
| [BitDecrement(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.bitdecrement?view=net-8.0#system-math-bitdecrement(system-double)) | Retorna o maior valor que compara menos do que um valor especificado. |
| [BitIncrement(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.bitincrement?view=net-8.0#system-math-bitincrement(system-double)) | Retorna o menor valor que compara maior que um valor especificado. |
| [Cbrt(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.cbrt?view=net-8.0#system-math-cbrt(system-double)) | Retorna a raiz do cubo de um número especificado. |
| [Ceiling(Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.ceiling?view=net-8.0#system-math-ceiling(system-decimal)) | Retorna o menor valor integral maior ou igual ao número decimal especificado. |
| [Ceiling(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.ceiling?view=net-8.0#system-math-ceiling(system-double)) | Retorna o menor valor integral maior ou igual ao número de ponto flutuante de precisão dupla especificado. |
| [Clamp(Byte, Byte, Byte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-byte-system-byte-system-byte)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(Decimal, Decimal, Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-decimal-system-decimal-system-decimal)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(Double, Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-double-system-double-system-double)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(Int16, Int16, Int16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-int16-system-int16-system-int16)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(Int32, Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-int32-system-int32-system-int32)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(Int64, Int64, Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-int64-system-int64-system-int64)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(IntPtr, IntPtr, IntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-intptr-system-intptr-system-intptr)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(SByte, SByte, SByte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-sbyte-system-sbyte-system-sbyte)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(Single, Single, Single)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-single-system-single-system-single)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(UInt16, UInt16, UInt16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-uint16-system-uint16-system-uint16)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(UInt32, UInt32, UInt32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-uint32-system-uint32-system-uint32)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(UInt64, UInt64, UInt64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-uint64-system-uint64-system-uint64)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [Clamp(UIntPtr, UIntPtr, UIntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.clamp?view=net-8.0#system-math-clamp(system-uintptr-system-uintptr-system-uintptr)) | Retorna `value` fixado ao intervalo inclusivo de `min` e `max`. |
| [CopySign(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.copysign?view=net-8.0#system-math-copysign(system-double-system-double)) | Retorna um valor com a magnitude de `x` e o sinal de `y`. |
| [Cos(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.cos?view=net-8.0#system-math-cos(system-double)) | Retorna o cosseno do ângulo especificado. |
| [Cosh(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.cosh?view=net-8.0#system-math-cosh(system-double)) | Retorna o cosseno hiperbólico do ângulo especificado. |
| [DivRem(Byte, Byte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-byte-system-byte)) | Produz o quociente e o restante de dois números de 8 bits não assinados. |
| [DivRem(Int16, Int16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-int16-system-int16)) | Produz o quociente e o restante de dois números assinados de 16 bits. |
| [DivRem(Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-int32-system-int32)) | Produz o quociente e o restante de dois números assinados de 32 bits. |
| [DivRem(Int32, Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-int32-system-int32-system-int32@)) | Calcula o quociente de dois inteiros com sinal de 32 bits e também retorna o restante em um parâmetro de saída. |
| [DivRem(Int64, Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-int64-system-int64)) | Produz o quociente e o restante de dois números assinados de 64 bits. |
| [DivRem(Int64, Int64, Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-int64-system-int64-system-int64@)) | Calcula o quociente de dois inteiros com sinal de 64 bits e também retorna o restante em um parâmetro de saída. |
| [DivRem(IntPtr, IntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-intptr-system-intptr)) | Produz o quociente e o restante de dois números de tamanho nativo assinados. |
| [DivRem(SByte, SByte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-sbyte-system-sbyte)) | Produz o quociente e o restante de dois números assinados de 8 bits. |
| [DivRem(UInt16, UInt16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-uint16-system-uint16)) | Produz o quociente e o restante de dois números de 16 bits não assinados. |
| [DivRem(UInt32, UInt32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-uint32-system-uint32)) | Produz o quociente e o restante de dois números de 32 bits não assinados. |
| [DivRem(UInt64, UInt64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-uint64-system-uint64)) | Produz o quociente e o restante de dois números de 64 bits não assinados. |
| [DivRem(UIntPtr, UIntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.divrem?view=net-8.0#system-math-divrem(system-uintptr-system-uintptr)) | Produz o quociente e o restante de dois números de tamanho nativo não assinados. |
| [Exp(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.exp?view=net-8.0#system-math-exp(system-double)) | Retorna `e` gerados para a potência especificada. |
| [Floor(Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.floor?view=net-8.0#system-math-floor(system-decimal)) | Retorna o maior valor integral menor ou igual ao número decimal especificado. |
| [Floor(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.floor?view=net-8.0#system-math-floor(system-double)) | Retorna o maior valor integral menor ou igual ao número de ponto flutuante de precisão dupla especificado. |
| [FusedMultiplyAdd(Double, Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.fusedmultiplyadd?view=net-8.0#system-math-fusedmultiplyadd(system-double-system-double-system-double)) | Retorna (x * y) + z, arredondado como uma operação ternária. |
| [IEEERemainder(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.ieeeremainder?view=net-8.0#system-math-ieeeremainder(system-double-system-double)) | Retorna o restante resultante da divisão de um número especificado por outro número especificado. |
| [ILogB(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.ilogb?view=net-8.0#system-math-ilogb(system-double)) | Retorna o logaritmo inteiro base 2 de um número especificado. |
| [Log(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.log?view=net-8.0#system-math-log(system-double)) | Retorna o logaritmo natural (`e`base) de um número especificado. |
| [Log(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.log?view=net-8.0#system-math-log(system-double-system-double)) | Retorna o logaritmo de um número especificado em uma base especificada. |
| [Log10(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.log10?view=net-8.0#system-math-log10(system-double)) | Retorna o logaritmo base 10 de um número especificado. |
| [Log2(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.log2?view=net-8.0#system-math-log2(system-double)) | Retorna o logaritmo base 2 de um número especificado. |
| [Max(Byte, Byte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-byte-system-byte)) | Retorna o maior de dois inteiros sem sinal de 8 bits. |
| [Max(Decimal, Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-decimal-system-decimal)) | Retorna o maior de dois números decimais. |
| [Max(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-double-system-double)) | Retorna o maior de dois números de ponto flutuante de precisão dupla. |
| [Max(Int16, Int16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-int16-system-int16)) | Retorna o maior de dois inteiros com sinal de 16 bits. |
| [Max(Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-int32-system-int32)) | Retorna o maior de dois inteiros com sinal de 32 bits. |
| [Max(Int64, Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-int64-system-int64)) | Retorna o maior de dois inteiros com sinal de 64 bits. |
| [Max(IntPtr, IntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-intptr-system-intptr)) | Retorna o maior de dois inteiros com sinal nativo. |
| [Max(SByte, SByte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-sbyte-system-sbyte)) | Retorna o maior de dois inteiros com sinal de 8 bits. |
| [Max(Single, Single)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-single-system-single)) | Retorna o maior de dois números de ponto flutuante de precisão única. |
| [Max(UInt16, UInt16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-uint16-system-uint16)) | Retorna o maior de dois inteiros sem sinal de 16 bits. |
| [Max(UInt32, UInt32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-uint32-system-uint32)) | Retorna o maior de dois inteiros sem sinal de 32 bits. |
| [Max(UInt64, UInt64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-uint64-system-uint64)) | Retorna o maior de dois inteiros sem sinal de 64 bits. |
| [Max(UIntPtr, UIntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.max?view=net-8.0#system-math-max(system-uintptr-system-uintptr)) | Retorna o maior de dois inteiros não assinados nativos. |
| [MaxMagnitude(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.maxmagnitude?view=net-8.0#system-math-maxmagnitude(system-double-system-double)) | Retorna a magnitude maior de dois números de ponto flutuante de precisão dupla. |
| [Min(Byte, Byte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-byte-system-byte)) | Retorna o menor de dois inteiros sem sinal de 8 bits. |
| [Min(Decimal, Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-decimal-system-decimal)) | Retorna o menor de dois números decimais. |
| [Min(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-double-system-double)) | Retorna o menor de dois números de ponto flutuante de precisão dupla. |
| [Min(Int16, Int16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-int16-system-int16)) | Retorna o menor de dois inteiros com sinal de 16 bits. |
| [Min(Int32, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-int32-system-int32)) | Retorna o menor de dois inteiros com sinal de 32 bits. |
| [Min(Int64, Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-int64-system-int64)) | Retorna o menor de dois inteiros com sinal de 64 bits. |
| [Min(IntPtr, IntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-intptr-system-intptr)) | Retorna o menor de dois inteiros com sinal nativo. |
| [Min(SByte, SByte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-sbyte-system-sbyte)) | Retorna o menor de dois inteiros com sinal de 8 bits. |
| [Min(Single, Single)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-single-system-single)) | Retorna o menor de dois números de ponto flutuante de precisão única. |
| [Min(UInt16, UInt16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-uint16-system-uint16)) | Retorna o menor de dois inteiros sem sinal de 16 bits. |
| [Min(UInt32, UInt32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-uint32-system-uint32)) | Retorna o menor de dois inteiros sem sinal de 32 bits. |
| [Min(UInt64, UInt64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-uint64-system-uint64)) | Retorna o menor de dois inteiros sem sinal de 64 bits. |
| [Min(UIntPtr, UIntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.min?view=net-8.0#system-math-min(system-uintptr-system-uintptr)) | Retorna o menor de dois inteiros não assinados nativos. |
| [MinMagnitude(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.minmagnitude?view=net-8.0#system-math-minmagnitude(system-double-system-double)) | Retorna a magnitude menor de dois números de ponto flutuante de precisão dupla. |
| [Pow(Double, Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.pow?view=net-8.0#system-math-pow(system-double-system-double)) | Retorna um número especificado gerado para a potência especificada. |
| [ReciprocalEstimate(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.reciprocalestimate?view=net-8.0#system-math-reciprocalestimate(system-double)) | Retorna uma estimativa da recíproca de um número especificado. |
| [ReciprocalSqrtEstimate(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.reciprocalsqrtestimate?view=net-8.0#system-math-reciprocalsqrtestimate(system-double)) | Retorna uma estimativa da raiz quadrada recíproca de um número especificado. |
| [Round(Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-decimal)) | Arredonda um valor decimal para o valor integral mais próximo e arredonda valores de ponto médio para o número par mais próximo. |
| [Round(Decimal, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-decimal-system-int32)) | Arredonda um valor decimal para um número especificado de dígitos fracionários e arredonda valores de ponto médio para o número par mais próximo. |
| [Round(Decimal, Int32, MidpointRounding)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-decimal-system-int32-system-midpointrounding)) | Arredonda um valor decimal para um número especificado de dígitos fracionários usando a convenção de arredondamento especificada. |
| [Round(Decimal, MidpointRounding)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-decimal-system-midpointrounding)) | Arredonda um valor decimal de um inteiro usando a convenção de arredondamento especificada. |
| [Round(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-double)) | Arredonda um valor de ponto flutuante de precisão dupla para o valor integral mais próximo e arredonda valores de ponto médio para o número par mais próximo. |
| [Round(Double, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-double-system-int32)) | Arredonda um valor de ponto flutuante de precisão dupla para um número especificado de dígitos fracionários e arredonda valores de ponto médio para o número par mais próximo. |
| [Round(Double, Int32, MidpointRounding)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-double-system-int32-system-midpointrounding)) | Arredonda um valor de ponto flutuante de precisão dupla para um número especificado de dígitos fracionários usando a convenção de arredondamento especificada. |
| [Round(Double, MidpointRounding)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.round?view=net-8.0#system-math-round(system-double-system-midpointrounding)) | Arredonda um valor de ponto flutuante de precisão dupla para um inteiro usando a convenção de arredondamento especificada. |
| [ScaleB(Double, Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.scaleb?view=net-8.0#system-math-scaleb(system-double-system-int32)) | Retorna x * 2^n computado com eficiência. |
| [Sign(Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-decimal)) | Retorna um inteiro que indica o sinal de um número decimal. |
| [Sign(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-double)) | Retorna um inteiro que indica o sinal de um número de ponto flutuante de precisão dupla. |
| [Sign(Int16)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-int16)) | Retorna um inteiro que indica o sinal de um inteiro com sinal de 16 bits. |
| [Sign(Int32)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-int32)) | Retorna um inteiro que indica o sinal de um inteiro com sinal de 32 bits. |
| [Sign(Int64)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-int64)) | Retorna um inteiro que indica o sinal de um inteiro com sinal de 64 bits. |
| [Sign(IntPtr)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-intptr)) | Retorna um inteiro que indica o sinal de um inteiro com sinal de tamanho nativo. |
| [Sign(SByte)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-sbyte)) | Retorna um inteiro que indica o sinal de um inteiro com sinal de 8 bits. |
| [Sign(Single)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sign?view=net-8.0#system-math-sign(system-single)) | Retorna um inteiro que indica o sinal de um número de ponto flutuante de precisão única. |
| [Sin(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sin?view=net-8.0#system-math-sin(system-double)) | Retorna o seno do ângulo especificado. |
| [SinCos(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sincos?view=net-8.0#system-math-sincos(system-double)) | Retorna o seno e o cosseno do ângulo especificado. |
| [Sinh(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sinh?view=net-8.0#system-math-sinh(system-double)) | Retorna o seno hiperbólico do ângulo especificado. |
| [Sqrt(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.sqrt?view=net-8.0#system-math-sqrt(system-double)) | Retorna a raiz quadrada de um número especificado. |
| [Tan(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.tan?view=net-8.0#system-math-tan(system-double)) | Retorna a tangente do ângulo especificado. |
| [Tanh(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.tanh?view=net-8.0#system-math-tanh(system-double)) | Retorna a tangente hiperbólica do ângulo especificado. |
| [Truncate(Decimal)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.truncate?view=net-8.0#system-math-truncate(system-decimal)) | Calcula a parte integral de um número decimal especificado. |
| [Truncate(Double)](https://learn.microsoft.com/pt-br/dotnet/api/system.math.truncate?view=net-8.0#system-math-truncate(system-double)) | Calcula a parte integral de um número de ponto flutuante de precisão dupla especificado. |

### Inferencia de tipos

A partir da versão 3.0 da linguagem C# as variaveis que forem declaradas no escopo do metodo podem possuir um tipo implicito 

Usar a palavra chave var para instruir o compilador a deduzir o tipo da variavel da expressão a partir do lado direito da instrução de inicialização

O tipo inferido pode ser um tipo interno um tipo anonimo um tipo definido pelo desenvolvedor ou um tipo definido na biblioteca de classe da plataforma .NET

OBS: Variaveis declaradas com var devem ser sempre inicializadas

não é possivel inicializar uma variavel var como null

Multiplas variaveis de tipo implicito não podem ser inicializadas na mesma instrução

Não é possivel alterar o tipo da variavel var depois de incializada

### Constantes

Constantes são valores imutaveis que são conhecidas em tempo de compilação e não mudam durante a vida util do programa

As constantes são declaradas usando o modificador const e devem ser inicializadas no ato da declaração

Como recomendação de nomeclatura definir os nomes das constantes em caixa alta

É possivel declarar mais de uma constante na mesma linha Se os tipos forem os mesmos

### Operadores incremento e decremento

incremento → ++

Decremento →  - -

### Operadores relacionais

A caracteristica dos operadores relacionais é que o resultado de uma operação relacional terá como resultado true ou false

OBS: O metodo Equals() para string determina se duas strings possuem o mesmo valor e o comportamento é identico a utilização do operador de igualdade

### Operadores logicos

São usados em expressões logicas e trabalham com operadores booleanos e seu resultado será true ou false

| Operador | Significado | Comportamento |
| --- | --- | --- |
| && | And | Retorna false se penas uma das condições for false |
| || | Or | retorna true se apenas uma das condições for true |
| ! | Not | inverte o resultado → retorna false se o resultado for true e retorna true se o resultado for false |

### Precedencia e assossiatividade

A precedencia é um conjunto de regras que define como a expressão é avaliada

No C# cada operador tem uma prioridade atribuida e com base nessa prioridade a expressão é avaliada

As expressões com operadores de maior precedencia são avaliadas primeiro

Quando dois operadores tiverem a mesma precedencia eles são avaliados com base na assossiatividade do operador que pode ser da direita pra esquerda ou esquerda para direita

Operadores aritimeticos 

*  maior precedencia

/

%

+

 -

Opeeradores Logicos 

! 

&&

||

### Nullable Reference Type

Um tipo de referencia pode não ter nenhuma referencia 

Isso é expresso com o valor null

Se uma variavel de um tipo de referencia for igual a null ela não tem nenhuma referencia a um valor na memoria heap

Isso ocorre tambem quando declaramos uma variavel de tipo de referencia e não atribuimos o seu valor

O valor padrão de qualquer variavel de tipo por referencia é null

Com isso o compilador emite um alerta → Converting null literal or possible null value to ***non***-nullable type

Ao tentar acessar qualquer propriedade ou metodo do tipo definido e este estiver nulo no momento do acesso

Será levantado o seguinte erro em tempo de execução → System.NullReferenceException: Object reference not set to an instance of an object

Por esse motivo é que a partir da versão 8 da lingaugem C# foram introduzidos os Nullable Reference Types 

Nullable Reference Types  → São recursos de tempo de compilação onde o compilador usa uma analise estatica e emite avisos quando o codigo tem construções que podem levar a exceções de referencias nullas

o compilador alerta sobre a possibilidade de ocorrer um erro envolvendo a manipulação de uma referencia nula 

A finalidade dos tipos de referencia anulaveis é minimizar a chance da aplicação lançar um System.NullAlbleReference Exception quando executado

Esse alerta é ativado quando o elemento <Nullable><Nullable> é definido como enable no arquivo csproj 

Evitar o alerta NullableReferenceException

Pode ser usado o tipo nullable(?) ao atribuir o valor null 

E empregar o nullcondicional operator (?.) ao acessar a referencia

Exemplo

```csharp
string? nome = null; // momento da definição e atribuição
Console.WriteLine(nome?.ToUpper()); // momento de acessar metodos 
```

Uma outra forma de evitar é inicializar as variaveis dos tipos de referencia corretamenta 

Exemplo

```csharp
string nome = "";
Console.WriteLine(nome?.ToUpper());
```

### Operador Ternario

é representado pelo operador ? :

Avalia uma expressão booleana e retorna o resultado de uma das duas expressões dependendo se a expressão booleana é avaliada como true ou false 

Exemplo:

```csharp
condicao_expressao_booleana ? resultado_se_true : resultado_se_false
```
