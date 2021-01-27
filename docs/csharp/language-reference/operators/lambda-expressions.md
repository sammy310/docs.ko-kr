---
title: 람다 식 - C# 참조
description: 람다 식에 대해 알아봅니다. 식이 본문으로 포함된 식 람다 또는 문 블록이 본문으로 포함된 문 람다가 있습니다.
ms.date: 09/25/2020
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 2ae63396c0b1bb0bf1fe5c33b1103f69f6dcf664
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615869"
---
# <a name="lambda-expressions-c-reference"></a>람다 식(C# 참조)

‘람다 식’을 사용하여 익명 함수를 만듭니다. [람다 선언 연산자`=>`](lambda-operator.md)를 사용하여 본문에서 람다의 매개 변수 목록을 구분합니다. 람다 식은 다음과 같은 두 가지 형식 중 하나일 수 있습니다.

- 식이 본문으로 포함된 [식 람다](#expression-lambdas):

  ```csharp
  (input-parameters) => expression
  ```

- 문 블록이 본문으로 포함된 [문 람다](#statement-lambdas):

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

람다 식을 만들려면 람다 연산자 왼쪽에 입력 매개 변수를 지정하고(있는 경우) 다른 쪽에 식이나 문 블록을 지정합니다.

람다 식은 [대리자](../builtin-types/reference-types.md#the-delegate-type) 형식으로 변환할 수 있습니다. 람다 식을 변환할 수 있는 대리자 형식은 해당 매개 변수 및 반환 값의 형식에 따라 정의됩니다. 람다 식에서 값을 반환하지 않는 경우 `Action` 대리자 형식 중 하나로 변환할 수 있습니다. 값을 반환하는 경우 `Func` 대리자 형식으로 변환할 수 있습니다. 예를 들어 매개 변수는 두 개지만 값을 반환하지 않는 람다 식은 <xref:System.Action%602> 대리자로 변환할 수 있습니다. 매개 변수가 하나이고 값을 반환하는 람다 식은 <xref:System.Func%602> 대리자로 변환할 수 있습니다. 다음 예제에서는 `x`라고 이름이 지정되고 `x` 제곱 값을 반환하는 매개 변수를 지정하는 람다 식 `x => x * x`는 대리자 형식의 변수에 할당됩니다.

[!code-csharp-interactive[lambda is delegate](snippets/lambda-expressions/Introduction.cs#Delegate)]

다음 예제에 표시된 대로 식 람다는 [식 트리](../../programming-guide/concepts/expression-trees/index.md) 형식으로 변환할 수도 있습니다.

[!code-csharp-interactive[lambda is expression tree](snippets/lambda-expressions/Introduction.cs#ExpressionTree)]

대리자 형식이나 식 트리의 인스턴스가 필요한 코드에서 람다 식을 백그라운드에서 실행해야 하는 코드를 전달하는 <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> 메서드의 인수 등으로 사용할 수 있습니다. 다음 예제에 표시된 대로 [C#에 LINQ](../../linq/index.md)를 작성할 때 람다 식을 사용할 수도 있습니다.

[!code-csharp-interactive[lambda is argument in LINQ](snippets/lambda-expressions/Introduction.cs#Argument)]

예를 들어 LINQ to Objects 및 LINQ to XML에서 메서드 기반 구문을 사용하여 <xref:System.Linq.Enumerable?displayProperty=nameWithType> 클래스에서 <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> 메서드를 호출하는 경우 매개 변수는 대리자 형식 <xref:System.Func%602?displayProperty=nameWithType>입니다. 예를 들어 LINQ to SQL에서 <xref:System.Linq.Queryable?displayProperty=nameWithType> 클래스에서 <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> 메서드를 호출하는 경우 매개 변수 형식은 식 트리 형식 [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>)입니다. 두 경우 모두 동일한 람다 식을 사용하여 매개 변수 값을 지정할 수 있습니다. 그러면 두 `Select` 호출이 비슷하게 보일 수 있지만 실제로 람다 식을 통해 생성되는 개체 형식은 다릅니다.
  
## <a name="expression-lambdas"></a>식 람다

`=>` 연산자의 오른쪽에 식이 있는 람다 식을 식 람다라고 합니다. 식 람다는 식의 결과를 반환하며 기본 형식은 다음과 같습니다.

```csharp
(input-parameters) => expression
```

식 람다의 본문은 메서드 호출로 구성될 수 있습니다. 하지만 SQL Server에서처럼 .NET CLR(공용 언어 런타임)의 컨텍스트 외부에서 평가되는 [식 트리](../../programming-guide/concepts/expression-trees/index.md)를 만드는 경우에는 람다 식에서 메서드 호출을 사용하면 안 됩니다. 메서드는 .NET CLR(공용 언어 런타임)의 컨텍스트 내에서만 의미가 있습니다.

## <a name="statement-lambdas"></a>문 람다

문 람다는 다음과 같이 중괄호 안에 문을 지정한다는 점을 제외하면 식 람다와 비슷합니다.

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

문 람다의 본문에 지정할 수 있는 문의 개수에는 제한이 없지만 일반적으로 2-3개 정도만 지정합니다.

:::code language="csharp" interactive="try-dotnet-method" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatementLambda":::

문 람다를 사용하여 식 트리를 만들 수는 없습니다.

## <a name="input-parameters-of-a-lambda-expression"></a>람다 식 입력 매개 변수

람다 식의 입력 매개 변수는 괄호로 묶습니다. 입력 매개 변수가 0개이면 다음과 같이 빈 괄호를 지정합니다.  

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetZeroParameters":::

람다 식에 입력 매개 변수가 하나만 있는 경우 괄호는 선택 사항입니다.

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetOneParameter":::

두 개 이상의 입력 매개 변수는 쉼표로 구분합니다.

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetTwoParameters":::

컴파일러가 입력 매개 변수의 형식을 유추할 수 없는 경우도 있습니다. 다음 예제와 같이 형식을 명시적으로 지정할 수 있습니다.

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetExplicitlyTypedParameters":::

입력 매개 변수 형식은 모두 명시적이거나 암시적이어야 합니다. 그렇지 않으면 [CS0748](../../misc/cs0748.md) 컴파일러 오류가 발생합니다.

C# 9.0부터 [무시 항목](../../discards.md)을 사용하여 람다 식에서 사용하지 않는 입력 매개 변수를 두 개 이상 지정할 수 있습니다.

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetDiscards":::

람다 무시 항목 매개 변수는 람다 식을 사용하여 [이벤트 처리기를 제공](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)하는 경우에 유용할 수 있습니다.

> [!NOTE]
> 이전 버전과의 호환성을 위해 단일 입력 매개 변수만 `_`로 명명된 경우 람다 식 내에서 `_`가 해당 매개 변수의 이름으로 처리됩니다.

## <a name="async-lambdas"></a>비동기 람다

[async](../keywords/async.md) 및 [await](await.md) 키워드를 사용하여 비동기 처리를 통합하는 람다 식과 문을 쉽게 만들 수 있습니다. 예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

비동기 람다를 사용하여 동일한 이벤트 처리기를 추가할 수 있습니다. 이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `async` 한정자를 추가합니다.

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

비동기 메서드를 만들고 사용하는 방법에 대한 자세한 내용은 [Async 및 Await를 사용한 비동기 프로그래밍](../../programming-guide/concepts/async/index.md)을 참조하세요.

## <a name="lambda-expressions-and-tuples"></a>람다 식 및 튜플

C# 7.0부터 C# 언어에서 [튜플](../builtin-types/value-tuples.md)을 기본적으로 지원합니다. 람다 식에 인수로 튜플을 제공할 수 있으며 람다 식에서 튜플을 반환할 수도 있습니다. 경우에 따라 C# 컴파일러는 형식 유추를 사용하여 튜플 구성 요소의 형식을 확인할 수 있습니다.

쉼표로 구분된 해당 구성 요소 목록을 괄호로 묶어 튜플을 정의합니다. 다음 예제에서는 3개 구성 요소가 있는 튜플을 사용하여 숫자 시퀀스를 람다 식에 전달하고 각 값을 두 배로 늘린 후 곱하기의 결과가 포함된, 3개 구성 요소가 있는 튜플을 반환합니다.

[!code-csharp-interactive[lambda and tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

일반적으로 튜플 필드의 이름은 `Item1`, `Item2` 등입니다. 그러나 다음 예제에서처럼 명명된 구성 요소가 있는 튜플을 정의할 수 있습니다.

[!code-csharp-interactive[lambda and named tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

C# 튜플에 관한 자세한 내용은 [튜플 형식](../../language-reference/builtin-types/value-tuples.md)을 참조하세요.

## <a name="lambdas-with-the-standard-query-operators"></a>표준 쿼리 연산자와 람다 식

다른 구현 중에 LINQ to Objects는 형식이 제네릭 대리자의 <xref:System.Func%601> 패밀리 중 하나인 입력 매개 변수를 사용합니다. 이러한 대리자는 형식 매개 변수를 사용하여 입력 매개 변수의 수와 형식 및 대리자의 반환 형식을 정의합니다. `Func` 대리자는 소스 데이터 집합에 있는 각 요소에 적용할 사용자 정의 식을 캡슐화하는 데 매우 유용합니다. 예를 들어 <xref:System.Func%602> 대리자 형식을 고려합니다.  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

이 경우 대리자를 `Func<int, bool>` 인스턴스로 인스턴스화할 수 있습니다. 여기서 `int`는 입력 매개 변수이고, `bool`은 반환 값입니다. 반환 값은 항상 마지막 형식 매개 변수에 지정됩니다. 예를 들어 `Func<int, string, bool>`은 두 입력 매개 변수 `int` 및 `string`과 반환 형식 `bool`을 사용하여 대리자를 정의합니다. 다음 `Func` 대리자를 호출하면 입력 매개 변수가 5인지 여부를 나타내는 부울 값이 반환됩니다.

[!code-csharp-interactive[Func example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<xref:System.Linq.Queryable> 형식에 정의되어 있는 표준 쿼리 연산자의 경우와 같이 인수 형식이 <xref:System.Linq.Expressions.Expression%601>인 경우에도 람다 식을 사용할 수 있습니다. <xref:System.Linq.Expressions.Expression%601> 인수를 지정하면 람다 식이 식 트리로 컴파일됩니다.
  
이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 표준 쿼리 연산자를 사용합니다.

[!code-csharp-interactive[Count example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

컴파일러에서 입력 매개 변수의 형식을 유추하거나 사용자가 형식을 명시적으로 지정할 수 있습니다. 이 람다 식은 2로 나누었을 때 나머지가 1인 정수(`n`)의 수를 계산합니다.

다음 예제에서는 숫자 시퀀스에서 조건을 만족하지 않는 첫 번째 숫자가 9이기 때문에 `numbers` 배열에서 9 앞에 오는 모든 요소가 포함된 시퀀스를 생성합니다.

[!code-csharp-interactive[TakeWhile example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

다음 예제에서는 입력 매개 변수를 괄호로 묶어 여러 개 지정합니다. 이 메서드는 값이 배열의 서수 위치보다 작은 숫자가 나타날 때까지 `numbers` 배열의 모든 요소를 반환합니다.

[!code-csharp-interactive[TakeWhile example 2](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a>람다 식에서의 형식 유추

컴파일러에서는 람다 식 본문, 매개 변수 형식 및 C# 언어 사양에 설명되어 있는 기타 요소를 기준으로 형식을 유추할 수 있기 때문에 대부분의 경우에는 람다 식을 작성할 때 입력 매개 변수의 형식을 지정하지 않아도 됩니다. 대부분의 표준 쿼리 연산자에서 첫 번째 입력 형식은 소스 시퀀스 요소의 형식입니다. `IEnumerable<Customer>`를 쿼리할 경우 입력 변수가 `Customer` 개체로 유추됩니다. 이는 이 개체의 메서드와 속성에 액세스할 수 있음을 의미합니다.  

```csharp
customers.Where(c => c.City == "London");
```

람다 식의 형식 유추에 대한 일반적인 규칙은 다음과 같습니다.

- 람다 식과 대리자 형식에 포함된 매개 변수 수가 같아야 합니다.

- 람다 식의 각 입력 매개 변수는 해당되는 대리자 매개 변수로 암시적으로 변환될 수 있어야 합니다.

- 람다 식의 반환 값(있는 경우)은 대리자의 반환 형식으로 암시적으로 변환될 수 있어야 합니다.
  
공용 형식 시스템에는 “람다 식”이라는 개념이 기본적으로 포함되어 있지 않기 때문에 람다 식 자체에는 형식이 없습니다. 그러나 람다 식의 “형식”을 비공식적으로 언급해야 할 경우도 있는데 이 경우 형식은 대리자 형식 또는 람다 식이 변환되는 <xref:System.Linq.Expressions.Expression> 형식을 의미합니다.

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a>람다 식에서 외부 변수 및 변수 범위 캡처

람다는 *외부 변수* 를 참조할 수 있습니다. 이러한 변수는 람다 식을 정의하는 메서드 범위 내에 있거나 람다 식을 포함하는 형식 범위 내에 있는 변수입니다. 이러한 방식으로 캡처되는 변수는 변수가 범위를 벗어나 가비지 수집되는 경우에도 람다 식에 사용할 수 있도록 저장됩니다. 외부 변수는 명확하게 할당해야만 람다 식에 사용할 수 있습니다. 다음 예제에서는 이러한 규칙을 보여 줍니다.

[!code-csharp[variable scope](snippets/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

람다 식의 변수 범위에는 다음과 같은 규칙이 적용됩니다.  

- 캡처된 변수는 해당 변수를 참조하는 대리자가 가비지 수집 대상이 될 때까지 가비지 수집되지 않습니다.

- 람다 식에 사용된 변수는 바깥쪽 메서드에 표시되지 않습니다.

- 람다 식은 바깥쪽 메서드에서 [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md) 또는 [out](../keywords/out-parameter-modifier.md) 매개 변수를 직접 캡처할 수 없습니다.

- 람다 식의 [return](../keywords/return.md) 문에 의해서는 바깥쪽 메서드가 반환되지 않습니다.

- 해당 점프 문의 대상이 람다 식 블록을 벗어나는 경우 람다 식에는 [goto](../keywords/goto.md), [break](../keywords/break.md) 또는 [continue](../keywords/continue.md) 문을 포함할 수 없습니다. 대상이 블록 내에 있는 경우 람다 식 블록 외부에 점프 문을 사용해도 오류가 발생합니다.

C# 9.0부터 람다 식에 `static` 한정자를 적용하여 의도치 않게 람다가 지역 변수 또는 인스턴스 상태를 캡처하는 것을 방지할 수 있습니다.

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatic":::

정적 람다는 바깥쪽 범위에서 지역 변수 또는 인스턴스 상태를 캡처할 수 없지만 정적 멤버와 상수 정의를 참조할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.

C# 9.0에 추가된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.

- [람다 무시 항목 매개 변수](~/_csharplang/proposals/csharp-9.0/lambda-discard-parameters.md)
- [정적 무명 함수](~/_csharplang/proposals/csharp-9.0/static-anonymous-functions.md)

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
- [LINQ(Language-Integrated Query)](../../programming-guide/concepts/linq/index.md)
- [식 트리](../../programming-guide/concepts/expression-trees/index.md)
- [로컬 함수 및 람다 식](../../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)
- [Visual Studio 2008 C# 샘플(LINQ 샘플 쿼리 파일 및 XQuery 프로그램 참조)](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
