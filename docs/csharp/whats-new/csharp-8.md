---
title: C# 8.0의 새로운 기능 - C# 가이드
description: C# 8.0의 새로운 기능을 살펴봅니다. 이 문서는 미리 보기 2가 반영된 최신 내용을 담고 있습니다.
ms.date: 02/12/2019
ms.openlocfilehash: 3a19cc7ffae706769cf1b1a19fdaff7c7cdc07fc
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674447"
---
# <a name="whats-new-in-c-80"></a>C# 8.0의 새로운 기능

C# 언어에는 여러 개선된 기능이 포함되어 있습니다. 이러한 기능은 미리 보기 2에서 직접 사용해 볼 수 있습니다. 미리 보기 2에 추가된 새로운 기능은 다음과 같습니다.

- [패턴 일치 개선 사항](#more-patterns-in-more-places):
  * [Switch 식](#switch-expressions)
  * [속성 패턴](#property-patterns)
  * [튜플 패턴](#tuple-patterns)
  * [위치 패턴](#positional-patterns)
- [using 선언](#using-declarations)
- [정적 로컬 함수](#static-local-functions)
- [삭제 가능한 ref struct](#disposable-ref-structs)

다음은 C# 8.0 미리 보기 1부터 적용된 언어 기능입니다.

- [nullable 참조 형식](#nullable-reference-types)
- [비동기 스트림](#asynchronous-streams)
- [인덱스 및 범위](#indices-and-ranges)

> [!NOTE]
> 이 문서는 C# 8.0 미리 보기 2를 반영하여 업데이트되었습니다.

이 문서의 나머지 부분에서는 이러한 기능에 대해 간략하게 설명합니다. 심화 문서가 공개되면 해당 자습서에 대한 링크 및 개요가 제공됩니다.

## <a name="more-patterns-in-more-places"></a>더 많은 곳에서 더 많은 패턴 사용

**패턴 일치**는 관련이 있으나 유형이 다른 데이터에서 셰이프 종속 기능을 사용할 수 있도록 지원하는 도구를 제공합니다. C# 7.0부터 [`is`](../language-reference/keywords/is.md) 식과 [`switch`](../language-reference/keywords/switch.md) 문을 사용하는 형식 패턴 및 상수 패턴을 위한 구문이 추가되었습니다. 이 기능은 데이터와 기능을 각각 별도로 구분하는 프로그래밍 패러다임을 지원하기 위한 조심스러운 첫 번째 단계입니다. 업계에서 마이크로 서비스와 기타 클라우드 기반 아키텍처를 도입하는 사례가 늘어남에 따라 다른 언어 도구에 대한 요구가 높아졌습니다.

C# 8.0은 코드의 더 많은 곳에서 더 많은 패턴 식을 사용할 수 있도록 이 용어를 확대합니다. 데이터와 기능을 각각 별도로 구분하는 경우 이러한 기능을 고려해 보시기 바랍니다. 알고리즘이 개체의 런타임 형식이 아닌 다른 요소에 종속되는 경우 패턴 일치를 고려해 보시기 바랍니다. 이러한 기법은 디자인을 표현할 추가적인 방법을 제공합니다.

C# 8.0에는 더 많은 곳에서 패턴을 사용할 수 있도록 지원하는 기능에 더해 **재귀 패턴**도 추가되었습니다. 패턴 식의 결과는 식입니다. 재귀 패턴은 다른 패턴 식의 출력에 적용된 패턴 식입니다.

### <a name="switch-expressions"></a>Switch 식

[`switch`](../language-reference/keywords/switch.md) 문의 결과 각각의 `case` 블록에서 값이 생성되는 경우가 종종 있습니다. **Switch 식**을 사용하면 더욱더 간결한 식 구문을 사용할 수 있습니다. `case` 및 `break` 키워드를 반복적으로 사용하고 중괄호를 적용해야 하는 경우가 줄어듭니다.  다음과 같이 무지개의 색을 나열하는 enum 예를 살펴보겠습니다.

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Blue,
    Indigo,
    Violet
}
```

다음과 같이 switch 식을 포함하는 메서드를 사용하여 `Rainbow` 값을 RGB 값으로 변환할 수 있습니다.

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

여기에서 몇 가지 구문 개선 사항을 확인할 수 있습니다.

- 변수가 `switch` 키워드 앞에 옵니다. 이처럼 순서가 변경된 결과 switch 식과 switch 문을 눈으로 구분하기가 쉬워졌습니다.
- `case` 및 `:` 요소가 `=>`으로 대체되어 간결성과 직관성이 향상되었습니다.
- `default` 케이스가 `_` 무시 항목으로 대체되었습니다.
- 본문이 문이 아닌 식입니다.

기존의 `switch` 문을 사용하는 동일한 코드와 비교해 보세요.

```csharp
public static RGBColor fromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a>속성 패턴

**속성 패턴**을 사용하면 검사 대상 개체의 속성을 일치시킬 수 있습니다. 구매자의 주소를 기준으로 판매세를 계산하는 전자상거래 사이트를 예로 들어 보겠습니다. 판매세 계산은 `Address` 클래스의 주요 임무가 아닙니다. 판매세는 시간이 흐름에 따라 주소 형식이 변경되는 빈도보다 자주 변경될 가능성이 큽니다. 판매세의 금액은 주소의 `State` 속성에 종속됩니다. 다음 메서드는 속성 패턴을 사용하여 주소 및 가격으로부터 판매세를 계산합니다.

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

패턴 일치는 이 알고리즘을 표현하기 위한 더 간결한 구문을 만듭니다.

### <a name="tuple-patterns"></a>튜플 패턴

일부 알고리즘은 여러 입력을 사용합니다. **튜플 패턴**을 사용하면 [튜플](../tuples.md)로 표현되는 여러 값에 따라 전환할 수 있습니다.  다음 코드는 게임 ‘가위, 바위, 보’에 대한 전환 식을 보여 줍니다.

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

메시지는 승자를 나타냅니다. 버리기 사례는 동률의 세 가지 조합 또는 기타 텍스트 입력을 나타냅니다.

### <a name="positional-patterns"></a>위치 패턴

일부 형식에는 해당 속성을 불연속 변수로 분해하는 `Deconstruct` 메서드가 포함됩니다. `Deconstruct` 메서드에 액세스할 수 있는 경우 **위치 패턴**을 사용하여 개체의 속성을 검사하고 패턴에 해당 속성을 사용할 수 있습니다.  `X` 및 `Y`의 불연속 변수를 만들려면 `Deconstruct` 메서드를 포함하는 다음 `Point` 클래스를 사용하는 것이 좋습니다.

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

다음 메서드는 **위치 패턴**을 사용하여 `x`와 `y`의 값을 추출합니다. 그런 다음, `when` 절을 사용하여 점의 사분면을 확인합니다.

```csharp
static string Quadrant(Point p) => p switch
{
    (0, 0) => "origin",
    (var x, var y) when x > 0 && y > 0 => "Quadrant 1",
    (var x, var y) when x < 0 && y > 0 => "Quadrant 2",
    (var x, var y) when x < 0 && y < 0 => "Quadrant 3",
    (var x, var y) when x > 0 && y < 0 => "Quadrant 4",
    (var x, var y) => "on a border",
    _ => "unknown"
};
```

switch의 무시 패턴은 `x`나 `y` 둘 중 하나만 0인 경우에 일치합니다. expression 식은 항상 값을 생성하거나 예외를 throw해야 합니다. 일치하는 케이스가 없으면 switch 식이 예외를 throw합니다. switch 식이 가능한 모든 케이스를 포함하지 않으면 컴파일러에서 경고가 생성됩니다.

## <a name="using-declarations"></a>using 선언

**using 선언**은 `using` 키워드 뒤에 오는 변수 선언입니다. using 선언은 선언되는 변수를 바깥쪽 범위의 끝에서 삭제하라고 컴파일러에 알립니다. 텍스트 파일을 쓰는 다음 코드를 예로 들어 보겠습니다.

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

위 예에서 메서드의 닫는 중괄호에 도달하면 파일이 삭제됩니다. 이 지점이 바로 `file`이 선언된 범위의 끝입니다. 위 코드는 기존의 [using 문](../language-reference/keywords/using-statement.md) 문을 사용하는 다음 코드와 동일합니다.


```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

위 예에서 `using` 문의 닫는 중괄호에 도달하면 파일이 삭제됩니다.

두 경우 모두 컴파일러가 `Dispose()`를 호출합니다. using 문의 식을 삭제할 수 없는 경우 컴파일러에서 오류를 생성합니다.

## <a name="static-local-functions"></a>정적 로컬 함수

이제 로컬 함수가 바깥쪽 범위의 변수를 참조하는 경우가 없도록 로컬 함수에 `static` 한정자를 추가할 수 있습니다. 이렇게 하면 `CS8421`, “A static local function can't contain a reference to <variable>”(정적 로컬 함수는 <variable> 참조를 포함할 수 없습니다.)이(가) 생성됩니다. 

다음과 같은 코드를 생각해 볼 수 있습니다. 여기서 로컬 함수 `LocalFunction`은 바깥쪽 범위(메서드 `M`)에서 선언된 변수 `y`에 액세스합니다. 따라서 `LocalFunction`을 `static` 한정자와 함께 선언할 수 없습니다.

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

다음 코드에는 정적 로컬 함수가 포함되어 있습니다. 여기서 로컬 함수는 바깥쪽 범위의 변수에 액세스하지 않으므로 정적이 될 수 있습니다.

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a>삭제 가능한 ref struct

`ref` 한정자와 함께 선언된 `struct`는 인터페이스를 구현할 수 없으므로 <xref:System.IDisposable>을 구현할 수 없습니다. 따라서 `ref struct`가 삭제 가능해지려면 액세스 가능한 `void Dispose()` 메서드를 가져야 합니다. 이것은 `readonly ref struct` 선언에도 적용됩니다.

## <a name="nullable-reference-types"></a>nullable 참조 형식

nullable 주석 컨텍스트에서 참조 형식의 변수는 모두 **nullable이 아닌 참조 형식**으로 간주됩니다. 변수가 null이 될 수 있음을 나타내려면 형식 이름 뒤에 `?`를 추가하여 해당 변수를 **nullable 참조 형식**으로 선언해야 합니다.

nullable이 아닌 참조 형식의 경우, 로컬 변수가 선언될 때 null이 아닌 값으로 초기화되도록 컴파일러가 흐름 분석을 사용합니다. 필드는 생성 시점에 초기화되어야 합니다. 생성자(있는 경우)를 호출함으로써 또는 이니셜라이저에 의해 변수가 설정되지 않으면 컴파일러에서 경고를 생성합니다. 또한, nullable이 아닌 참조 형식은 null이 될 수 있는 값에 할당할 수 없습니다.

nullable 참조 형식은 할당되지 않았는지 또는 null로 초기화되었는지 검사되지 않습니다. 단, nullable 참조 형식의 변수가 액세스되거나 nullable이 아닌 참조 형식에 할당되기 전에 null에 대해 검사되도록 컴파일러가 흐름 분석을 사용합니다.

[nullable 참조 형식](../nullable-references.md) 개요에서 이 기능에 대해 자세히 알아볼 수 있습니다. [nullable 참조 형식 자습서](../tutorials/nullable-reference-types.md)를 활용하여 새 애플리케이션에서 직접 사용해 보세요. [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md)(nullable 참조 형식을 사용할 수 있도록 애플리케이션 마이그레이션 자습서)에서는 nullable 참조 형식을 사용할 수 있도록 기존 코드베이스를 마이그레이션하는 방법을 알아볼 수 있습니다.

## <a name="asynchronous-streams"></a>비동기 스트림

C# 8.0부터 스트림을 비동기식으로 만들고 사용할 수 있습니다. 비동기 스트림을 반환하는 메서드는 다음과 같은 세 가지 속성을 갖습니다.

1. `async` 한정자를 사용하여 선언되었습니다.
1. <xref:System.Collections.Generic.IAsyncEnumerable%601>를 반환합니다.
1. 비동기 스트림의 연속적인 요소를 반환하기 위해 메서드가 `yield return` 문을 포함합니다.

비동기 스트림을 사용하려면 스트림의 요소를 열거할 때 `foreach` 키워드 앞에 `await` 키워드를 사용해야 합니다. `await` 키워드를 추가하려면 비동기 스트림을 열거하는 메서드가 `async` 한정자와 함께 선언되어야 하며, 이 메서드가 `async` 메서드를 허용하는 형식을 반환해야 합니다. 일반적으로 이는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 형식을 반환해야 함을 의미합니다. <xref:System.Threading.Tasks.ValueTask> 또는 <xref:System.Threading.Tasks.ValueTask%601> 형식도 가능합니다. 메서드는 비동기 스트림을 사용할 수도 있고 생성할 수 있습니다. 비동기 스트림을 생성한다는 것은 메서드가 <xref:System.Collections.Generic.IAsyncEnumerable%601>를 반환한다는 것을 의미합니다. 다음 코드는 0에서 19까지의 시퀀스를 생성합니다. 숫자가 생성되는 각 시점 사이에는 100ms의 대기 시간이 있습니다.

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

`await foreach` 문을 사용하여 시퀀스를 열거합니다.

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

[비동기 스트림 생성 및 사용](../tutorials/generate-consume-asynchronous-stream.md) 자습서에서 직접 비동기 스트림을 사용해 볼 수 있습니다.

## <a name="indices-and-ranges"></a>인덱스 및 범위

범위와 인덱스는 배열, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>에서 하위 범위를 지정하는 간결한 구문을 제공합니다.

인덱스를 **뒤에서부터** 지정할 수 있습니다. **뒤에서부터** 지정하려면 `^` 연산자를 사용합니다. `array[2]`가 “앞에서부터 2번째” 요소를 의미한다는 것은 이미 잘 알고 계실 것입니다. `array[^2]`는 “뒤에서부터 2번째” 요소를 의미합니다. 인덱스 `^0`은 “끝”, 즉 마지막 요소 뒤에 오는 인덱스를 의미합니다.

**범위**는 **범위 연산자** `..`를 사용하여 지정할 수 있습니다. 예를 들어, `0..^0`은 배열의 전체 범위를 지정하는데, 앞에서부터 인덱스 0에서 뒤에서부터 인덱스 1까지(즉, ^0 인덱스는 은 포함되지 않음)를 의미합니다. 피연산자 둘 다 “앞에서부터” 또는 “뒤에서부터”를 사용할 수 있습니다. 피연산자 둘 다 생략하는 것도 가능합니다. 시작 인덱스의 기본값은 `0`, 끝 인덱스의 기본값은 `^0`입니다.

몇 가지 예를 살펴보겠습니다. 다음과 같은 배열이 있습니다. 앞에서부터의 인덱스와 뒤에서부터의 인덱스가 주석으로 처리되어 있습니다.

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};
```

각 요소의 인덱스는 “앞에서부터”라는 개념과 “뒤에서부터”라는 개념과 범위에는 해당 범위의 끝은 포함되지 않음을 보여줍니다. 전체 배열의 “시작”은 첫 번째 요소입니다. 전체 배열의 “끝”은 마지막 요소의 “뒤”에 있습니다.

다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다.

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다. 이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며, `words[4]` 요소는 포함되지 않습니다.

```csharp
var quickBrownFox = words[1..4];
```

다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다. 이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며. 끝 인덱스 `words[^0]`는 포함되지 않습니다.

```csharp
var lazyDog = words[^2..^0];
```

다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

범위를 변수로 선언할 수도 있습니다.

```csharp
Range phrase = 1..4;
```

이렇게 변수로 선언된 범위는 `[` 문자와 `]` 문자 사이에 사용할 수 있습니다.

```csharp
var text = words[phrase];
```
