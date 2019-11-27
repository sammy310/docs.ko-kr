---
title: 배열
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: 9dfe7814b00b4d060fa4ab9aa594faa948217d8d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351861"
---
# <a name="arrays-in-visual-basic"></a>Visual Basic의 배열

배열은 *요소로*표현 되는 값 집합으로, 논리적으로 서로 관련 되어 있습니다. 예를 들어 배열은 문법 학교에서 각 학년의 학생 수로 구성 될 수 있습니다. 배열의 각 요소는 단일 등급의 학생 수입니다. 마찬가지로, 배열은 클래스에 대 한 학생의 등급으로 구성 될 수 있습니다. 배열의 각 요소는 단일 등급입니다.

각 데이터 항목을 저장 하는 개별 변수가 있을 수 있습니다. 예를 들어 응용 프로그램에서 학생 성적을 분석 하는 경우 `englishGrade1`, `englishGrade2`등의 각 학생 등급에 대해 별도의 변수를 사용할 수 있습니다. 이 방법에는 세 가지 주요 제한 사항이 있습니다.

- 디자인 타임에는 처리 해야 하는 등급의 수를 정확 하 게 알아야 합니다.
- 많은 수의 등급을 신속 하 게 처리 하는 것은 어렵습니다. 이렇게 하면 응용 프로그램에 심각한 버그가 발생할 가능성이 훨씬 높아집니다.
- 유지 관리 하기가 어렵습니다. 추가 하는 각 새로운 등급에는 응용 프로그램을 수정, 다시 컴파일 및 다시 배포 해야 합니다.

배열을 사용 하면 이러한 관련 값을 동일한 이름으로 참조 하 고 *인덱스* 또는 *아래 첨자* 라는 숫자를 사용 하 여 배열에서의 위치를 기준으로 개별 요소를 식별할 수 있습니다. 배열의 인덱스 범위는 0에서 배열에 있는 요소의 총 수보다 1 개 미만입니다. Visual Basic 구문을 사용 하 여 배열의 크기를 정의 하는 경우 배열의 전체 요소 수가 아니라 가장 높은 인덱스를 지정 합니다. 배열을 하나의 단위로 사용할 수 있으며, 요소를 반복 하는 기능을 사용 하면 디자인 타임에 포함 된 요소 수를 정확 하 게 알 필요가 없습니다.

설명하기 전에 몇 가지 빠른 예제는 다음과 같습니다.

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

' Declare a single-dimension array and set its 4 values.
Dim numbers = New Integer() {1, 2, 4, 8}

' Change the size of an existing array to 16 elements and retain the current values.
ReDim Preserve numbers(15)

' Redefine the size of an existing array and reset the values.
ReDim numbers(15)

' Declare a 6 x 6 multidimensional array.
Dim matrix(5, 5) As Double

' Declare a 4 x 3 multidimensional array and set array element values.
Dim matrix = New Integer(3, 2) {{1, 2, 3}, {2, 3, 4}, {3, 4, 5}, {4, 5, 6}}

' Declare a jagged array
Dim sales()() As Double = New Double(11)() {}
```

## <a name="array-elements-in-a-simple-array"></a>단순 배열의 배열 요소

문법 학교에서 각 학년의 학생 수를 저장 하는 `students` 이라는 배열을 만들어 보겠습니다. 요소의 인덱스 범위는 0부터 6까지입니다. 이 배열을 사용 하는 것이 7 개의 변수를 선언 하는 것 보다 간단 합니다.

다음 그림에서는 `students` 배열을 보여 줍니다. 각 배열 요소에서

- 요소의 인덱스는 학년을 나타냅니다(인덱스 0은 유치원을 나타냄).

- 요소에 포함된 값은 해당 학년의 학생 수를 나타냅니다.

![학생 수의 배열을 보여 주는 다이어그램](./media/index/students-array-elements.gif)

다음 예제는 배열을 만들고 사용 하는 Visual Basic 코드를 포함 합니다.

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

이 예제에서는 다음 세 가지 작업을 수행 합니다.

- 7 개 요소를 사용 하 여 `students` 배열을 선언 합니다. 배열 선언의 숫자 `6`은 배열의 마지막 인덱스를 나타냅니다. 배열의 요소 수보다 하나 작은 수입니다.
- 배열의 각 요소에 값을 할당 합니다. 배열 요소는 배열 이름을 사용 하 고 개별 요소의 인덱스를 괄호 안에 포함 하 여 액세스할 수 있습니다.
- 배열의 각 값을 나열 합니다. 이 예제에서는 [`For`](../../../language-reference/statements/for-next-statement.md) 문을 사용 하 여 인덱스 번호로 배열의 각 요소에 액세스 합니다.

앞의 예제에서 `students` 배열은 하나의 인덱스를 사용 하기 때문에 1 차원 배열입니다. 둘 이상의 인덱스나 첨자를 사용 하는 배열을 *다차원*이라고 합니다. 자세한 내용은이 문서의 나머지 부분과 [Visual Basic의 배열 차원](../../language-features/arrays/array-dimensions.md)을 참조 하세요.

## <a name="creating-an-array"></a>배열 만들기

여러 가지 방법으로 배열의 크기를 정의할 수 있습니다.

- 배열을 선언할 때 크기를 지정할 수 있습니다.

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- `New` 절을 사용 하 여 배열을 만들 때 배열의 크기를 제공할 수 있습니다.

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

기존 배열이 있는 경우 [`ReDim`](../../../language-reference/statements/redim-statement.md) 문을 사용 하 여 크기를 다시 정의할 수 있습니다. `ReDim` 문이 배열에 있는 값을 유지 하도록 지정 하거나 빈 배열을 만들도록 지정할 수 있습니다. 다음 예제에서는 `ReDim` 문을 사용하여 기존 배열의 크기를 수정하는 여러 가지 방법을 보여 줍니다.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

자세한 내용은 [ReDim 문](../../../language-reference/statements/redim-statement.md)을 참조 하세요.

## <a name="storing-values-in-an-array"></a>배열에 값 저장

`Integer`형식의 인덱스를 사용하여 배열의 각 위치에 액세스할 수 있습니다. 괄호로 묶인 해당 인덱스를 통해 각 배열 위치를 참조하여 배열에 값을 저장하고 검색할 수 있습니다. 다차원 배열의 인덱스는 쉼표 (,)로 구분 됩니다. 각 배열 차원에 대해 하나의 인덱스가 필요합니다.

다음 예제에서는 배열에 값을 저장 하 고 검색 하는 몇 가지 문을 보여 줍니다.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>배열 리터럴을 사용 하 여 배열 채우기

배열 리터럴을 사용 하 여 배열을 만들 때 값의 초기 집합으로 배열을 채울 수 있습니다. 배열 리터럴은 중괄호(`{}`)로 묶인 쉼표로 구분된 값 목록으로 구성됩니다.

배열 리터럴을 사용하여 배열을 만드는 경우 배열 형식을 제공하거나 형식 유추를 사용하여 배열 형식을 결정할 수 있습니다. 다음 예에서는 두 옵션을 모두 보여 줍니다.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

형식 유추를 사용 하는 경우 배열 형식은 리터럴 값 목록의 *기준 형식* 에 의해 결정 됩니다. 기준 형식은 배열의 다른 모든 형식이 확장 될 수 있는 형식입니다. 이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식이 축소될 수 있는 고유 형식입니다. 이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다. 예를 들어 배열 리터럴에 제공된 값 목록이 `Integer`, `Long`및 `Double`형식의 값을 포함하는 경우 결과 배열은 `Double`형식입니다. `Integer` 및 `Long`는 `Double`으로만 확장 되기 때문에 `Double`는 기준 유형입니다. 자세한 내용은 [Widening and Narrowing Conversions](../../language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.

> [!NOTE]
> 형식 멤버에서 지역 변수로 정의 된 배열에만 형식 유추를 사용할 수 있습니다. 명시적 형식 정의가 없으면 클래스 수준에서 배열 리터럴을 사용 하 여 정의 된 배열은 `Object[]`형식입니다. 자세한 내용은 [지역 형식 유추](../variables/local-type-inference.md)를 참조 하세요.

앞의 예제에서는 모든 배열 리터럴이 `Integer`형식 이더라도 `Double` 형식의 배열로 `values`를 정의 합니다. 배열 리터럴의 값을 `Double` 값으로 확장할 수 있으므로이 배열을 만들 수 있습니다.

*중첩 된 배열 리터럴을*사용 하 여 다차원 배열을 만들고 채울 수도 있습니다. 중첩 된 배열 리터럴에는 결과 배열과 일치 하는 여러 차원이 있어야 합니다. 다음 예제에서는 중첩 된 배열 리터럴을 사용 하 여 정수의 2 차원 배열을 만듭니다.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

중첩 된 배열 리터럴을 사용 하 여 배열을 만들고 채우면 중첩 된 배열 리터럴의 요소 수가 일치 하지 않으면 오류가 발생 합니다. 배열 변수가 배열 리터럴과 다른 수의 차원을 갖도록 명시적으로 선언 하는 경우에도 오류가 발생 합니다.

1 차원 배열에 사용할 수 있는 것 처럼 중첩 된 배열 리터럴을 사용 하 여 다차원 배열을 만들 때 형식 유추를 사용할 수 있습니다. 유추 된 형식은 모든 중첩 수준의 모든 배열 리터럴에 있는 모든 값의 기준 형식입니다. 다음 예제에서는 `Integer` 형식의 값에서 `Double[,]` 형식의 2 차원 배열을 만들고 `Double`합니다.

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

추가 예제를 보려면 [방법: Visual Basic에서 배열 변수 초기화](../../language-features/arrays/how-to-initialize-an-array-variable.md)를 참조하세요.

## <a name="iterating-through-an-array"></a>배열 반복

배열을 반복 하는 경우에는 가장 낮은 인덱스부터 가장 높은 인덱스까지 배열의 각 요소에 액세스 합니다. 일반적으로 다음 중 하나를 사용 [합니다. 다음 문](../../../language-reference/statements/for-next-statement.md) 또는 [For Each ... ](../../../language-reference/statements/for-each-next-statement.md)배열의 요소를 반복 하는 다음 문입니다. 배열의 상한을 모를 경우 <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> 메서드를 호출 하 여 인덱스의 가장 높은 값을 가져올 수 있습니다. 가장 낮은 인덱스 값은 거의 항상 0 이지만 <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> 메서드를 호출 하 여 인덱스의 가장 낮은 값을 가져올 수 있습니다.

다음 예제에서는 [`For...Next`](../../../language-reference/statements/for-next-statement.md) 문을 사용 하 여 1 차원 배열을 반복 합니다.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

다음 예에서는 [`For...Next`](../../../language-reference/statements/for-next-statement.md) 문을 사용 하 여 다차원 배열을 반복 합니다. <xref:System.Array.GetUpperBound%2A> 메서드에는 차원을 지정하는 매개 변수가 있습니다. `GetUpperBound(0)`는 첫 번째 차원의 가장 높은 인덱스를 반환 하 고 `GetUpperBound(1)`는 두 번째 차원의 가장 큰 인덱스를 반환 합니다.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

다음 예제에서는 [각각에 대해를 사용 합니다. ](../../../language-reference/statements/for-each-next-statement.md)1 차원 배열 및 2 차원 배열을 반복 하는 다음 문입니다.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>배열 크기

배열 크기는 모든 차원의 길이 곱입니다. 현재 배열에 포함된 요소의 총 수를 나타냅니다.  예를 들어 다음 예제에서는 각 차원에서 4 개의 요소를 포함 하는 2 차원 배열을 선언 합니다. 예제의 출력에서 볼 수 있듯이, 배열의 크기는 16 (또는 (3 + 1) * (3 + 1)입니다.

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> 배열 크기에 대 한 논의는 가변 배열에는 적용 되지 않습니다. 가변 배열 및 가변 배열의 크기를 결정 하는 방법에 대 한 자세한 내용은 [가변](#jagged-arrays) 배열 섹션을 참조 하세요.

<xref:System.Array.Length%2A?displayProperty=nameWithType> 속성을 사용하여 배열의 크기를 찾을 수 있습니다. <xref:System.Array.GetLength%2A?displayProperty=nameWithType> 메서드를 사용 하 여 다차원 배열의 각 차원 길이를 찾을 수 있습니다.

새 배열 개체를 할당 하거나 [`ReDim` statement](../../../language-reference/statements/redim-statement.md) 문을 사용 하 여 배열 변수의 크기를 조정할 수 있습니다. 다음 예제에서는 `ReDim` 문을 사용 하 여 100 요소 배열을 51 요소 배열로 변경 합니다.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

배열의 크기를 처리할 때 유의해야 하는 여러 가지 사항이 있습니다.

|||
|---|---|
|차원 길이|각 차원의 인덱스는 0부터 시작 합니다. 즉, 0부터 상한 까지의 범위입니다. 따라서 지정 된 차원의 길이는 해당 차원의 선언 된 상한 보다 하나 큽니다.|
|길이 제한|배열의 모든 차원 길이는 `Integer` 데이터 형식의 최대값으로 제한 됩니다 .이 값은 <xref:System.Int32.MaxValue?displayProperty=nameWithType> 또는 (2 ^ 31)-1입니다. 그러나 배열의 총 크기는 시스템에서 사용 가능한 메모리에 의해서도 제한됩니다. 사용 가능한 메모리 크기를 초과 하는 배열을 초기화 하려고 하면 런타임에서 <xref:System.OutOfMemoryException>을 throw 합니다.|
|크기 및 요소 크기|배열의 크기는 해당 요소의 데이터 형식과 독립적입니다. 크기는 항상 메모리에 사용 되는 바이트 수가 아니라 요소의 총 수를 나타냅니다.|
|메모리 소비|배열이 메모리에 저장되는 방법에 대해서는 어떠한 가정도 하지 않는 것이 좋습니다. 스토리지는 각 데이터 너비의 플랫폼마다 달라지므로 동일한 배열이 32비트 시스템보다 64비트 시스템에서 더 많은 메모리를 사용할 수 있습니다. 시스템 구성에 따라 배열을 초기화할 때 CLR(공용 언어 런타임)에서 스토리지를 할당하여 요소를 최대한 가깝게 압축하거나 모두 일반적인 하드웨어 경계에 맞출 수 있습니다. 또한 배열의 제어 정보로 인해 스토리지 오버헤드가 필요하며, 차원이 추가될 때마다 이 오버헤드가 증가합니다.|

## <a name="the-array-type"></a>배열 형식입니다.

모든 배열에는 해당 요소의 데이터 형식과 다른 데이터 형식이 있습니다. 모든 배열에 대한 단일 데이터 형식은 없습니다. 대신, 배열의 데이터 형식은 배열의 차원 수 또는 *차수*와 배열에 있는 요소의 데이터 형식에 의해 결정됩니다. 두 배열 변수는 차수가 동일 하 고 해당 요소의 데이터 형식이 동일한 경우에만 동일한 데이터 형식입니다. 배열 차원의 길이는 배열 데이터 형식에 영향을 주지 않습니다.

모든 배열은 <xref:System.Array?displayProperty=nameWithType> 클래스에서 상속되며, `Array`형식으로 변수를 선언할 수 있지만 `Array`형식의 배열을 만들 수는 없습니다. 예를 들어 다음 코드는 `arr` 변수를 `Array` 형식으로 선언 하 고 배열을 인스턴스화하기 위해 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> 메서드를 호출 하지만 배열의 형식은 Object []로 증명 됩니다.

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

또한 [ReDim 문](../../../language-reference/statements/redim-statement.md)은 `Array` 형식으로 선언된 변수에 대해 작업할 수 없습니다. 이러한 이유 및 형식 안전성을 위해 모든 배열을 특정 형식으로 선언 하는 것이 좋습니다.

배열이나 해당 요소의 데이터 형식을 여러 가지 방법으로 확인할 수 있습니다.

- 변수에 대 한 <xref:System.Object.GetType%2A> 메서드를 호출 하 여 변수의 런타임 형식을 나타내는 <xref:System.Type> 개체를 가져올 수 있습니다. <xref:System.Type> 개체는 해당 속성과 메서드에 광범위한 정보를 보유합니다.
- 변수를 <xref:Microsoft.VisualBasic.Information.TypeName%2A> 함수에 전달 하 여 런타임 형식의 이름으로 `String`를 가져올 수 있습니다.

다음 예제에서는 `GetType` 메서드와 `TypeName` 함수를 모두 호출 하 여 배열의 형식을 확인 합니다. 배열 형식이 `Byte(,)`입니다. 또한 <xref:System.Type.BaseType%2A?displayProperty=nameWithType> 속성은 바이트 배열의 기본 형식이 <xref:System.Array> 클래스 임을 나타냅니다.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>반환 값 및 매개 변수로 서의 배열

`Function` 프로시저에서 배열을 반환하려면 배열 데이터 형식 및 차원 수를 [Function 문](../../../language-reference/statements/function-statement.md)의 반환 형식으로 지정합니다. 함수 내에서 동일한 데이터 형식 및 차원 수의 지역 배열 변수를 선언합니다. [Return 문](../../../language-reference/statements/return-statement.md)에 지역 배열 변수를 괄호 없이 포함합니다.

`Sub` 또는 `Function` 프로시저에 대한 매개 변수로 배열을 지정하려면 지정된 데이터 형식 및 차원 수의 배열로 매개 변수를 정의합니다. 프로시저 호출에서 동일한 데이터 형식 및 차원 수를 사용 하 여 배열 변수를 전달 합니다.

다음 예제에서 `GetNumbers` 함수는 `Integer`형식의 1 차원 배열 `Integer()`을 반환 합니다. `ShowNumbers` 프로시저는 `Integer()` 인수를 사용합니다.

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

다음 예제에서 `GetNumbersMultiDim` 함수는 `Integer`형식의 2 차원 배열인 `Integer(,)`를 반환 합니다.  `ShowNumbersMultiDim` 프로시저는 `Integer(,)` 인수를 사용합니다.

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>가변 배열

애플리케이션의 데이터 구조가 2차원 배열이지만 사각형이 아닌 경우도 있습니다. 예를 들어 배열을 사용 하 여 해당 월의 각 날짜에 대 한 높은 온도에 대 한 데이터를 저장할 수 있습니다. 배열의 첫 번째 차원은 월을 나타내지만, 두 번째 차원은 일 수를 나타내고, 한 달의 일 수는 균일 하지 않습니다. 배열의 *배열*라고도 하는 *가변 배열은*이러한 시나리오를 위해 설계 되었습니다. 가변 배열은 요소가 배열인 배열입니다. 가변 배열 및 가변 배열의 각 요소에는 하나 이상의 차원이 있을 수 있습니다.

다음 예제에서는 월 배열을 사용 합니다. 각 요소는 일의 배열입니다. 다른 월의 일 수가 서로 다르므로이 예제에서는 가변 배열을 사용 합니다.  이 예제에서는 가변 배열을 만들고, 값을 할당 하 고, 값을 검색 및 표시 하는 방법을 보여 줍니다.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

이전 예제에서는 `For...Next` 루프를 사용 하 여 요소 별로 가변 배열에 값을 할당 합니다. 중첩 된 배열 리터럴을 사용 하 여 가변 배열의 요소에 값을 할당할 수도 있습니다. 그러나 중첩 된 배열 리터럴 (예: `Dim valuesjagged = {{1, 2}, {2, 3, 4}}`)을 사용 하려고 하면 컴파일러 오류 [BC30568](../../../,,/../misc/bc30568.md)생성 됩니다. 오류를 수정 하려면 내부 배열 리터럴을 괄호로 묶습니다. 다음 예제와 같이 괄호는 배열 리터럴 식이 계산 되도록 하 고 결과 값이 외부 배열 리터럴과 함께 사용 됩니다.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

가변 배열은 해당 요소가 배열을 포함 하는 1 차원 배열입니다. 따라서 <xref:System.Array.Length%2A?displayProperty=nameWithType> 속성 및 `Array.GetLength(0)` 메서드는 1 차원 배열의 요소 수를 반환 하 고, 가변 배열이 다차원이 아니기 때문에 `Array.GetLength(1)` <xref:System.IndexOutOfRangeException>을 throw 합니다. 각 하위 배열의 <xref:System.Array.Length%2A?displayProperty=nameWithType> 속성 값을 검색 하 여 각 하위 배열의 요소 수를 확인 합니다. 다음 예제에서는 가변 배열의 요소 수를 확인 하는 방법을 보여 줍니다.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>길이가 0 인 배열

Visual Basic 초기화 되지 않은 배열 (값이 `Nothing`인 배열) 및 *길이가 0 인 배열* 또는 빈 배열 (요소가 없는 배열)을 구분 합니다. 초기화 되지 않은 배열은 차원이 아니거나 할당 된 값을가지고 있지 않습니다. 예를 들면 다음과 같습니다.

```vb
Dim arr() As String
```

길이가 0 인 배열은-1의 차원으로 선언 됩니다. 예를 들면 다음과 같습니다.

```vb
Dim arrZ(-1) As String
```

다음과 같은 경우 길이가 0인 배열을 만들어야 할 수도 있습니다.

- <xref:System.NullReferenceException> 예외를 발생 시 키 지 않고 코드에서 <xref:System.Array.Length%2A> 또는 <xref:System.Array.Rank%2A>같은 <xref:System.Array> 클래스의 멤버에 액세스 하거나 Visual Basic와 같은 <xref:Microsoft.VisualBasic.Information.UBound%2A>함수를 호출 해야 합니다.

- 특수 한 경우에 `Nothing`를 확인 하지 않아도 되도록 코드를 단순하게 유지 하려고 합니다.

- 코드가 하나 이상의 프로시저에 길이가 0인 배열을 전달해야 하거나 하나 이상의 프로시저에서 길이가 0인 배열을 반환하는 API(애플리케이션 프로그래밍 인터페이스)와 상호 작용하는 경우

## <a name="splitting-an-array"></a>배열 분할

경우에 따라 단일 배열을 여러 배열로 분할 해야 할 수도 있습니다. 여기에는 배열을 분할할 지점 또는 지점을 식별 한 다음 배열을 두 개 이상의 개별 배열로 spitting 하는 작업이 포함 됩니다.

> [!NOTE]
> 이 섹션에서는 일부 구분 기호를 기반으로 단일 문자열을 문자열 배열로 분할 하는 방법에 대해 설명 하지 않습니다. 문자열 분할에 대 한 자세한 내용은 <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드를 참조 하세요.

배열을 분할 하는 가장 일반적인 기준은 다음과 같습니다.

- 배열의 요소 수입니다. 예를 들어, 지정 된 수의 요소 보다 많은 배열을 거의 같은 부분으로 분할할 수 있습니다. 이러한 목적을 위해 <xref:System.Array.Length%2A?displayProperty=nameWithType> 또는 <xref:System.Array.GetLength%2A?displayProperty=nameWithType> 메서드에서 반환 된 값을 사용할 수 있습니다.

- 배열의 분할 위치를 나타내는 구분 기호로 사용 되는 요소의 값입니다. <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> 및 <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> 메서드를 호출 하 여 특정 값을 검색할 수 있습니다.

배열이 분할 되어야 하는 인덱스를 결정 한 후에는 <xref:System.Array.Copy%2A?displayProperty=nameWithType> 메서드를 호출 하 여 개별 배열을 만들 수 있습니다.

다음 예제에서는 배열을 약 동일한 크기의 두 배열로 분할 합니다. 배열 요소의 총 수가 홀수 이면 첫 번째 배열의 요소는 두 번째 보다 하나 더 더 있습니다.

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

다음 예제에서는 배열 구분 기호 역할을 하는 값이 "zzz" 인 요소가 있는지 여부에 따라 문자열 배열을 두 배열로 분할 합니다. 새 배열은 구분 기호를 포함 하는 요소를 포함 하지 않습니다.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>배열 조인

여러 배열을 한 개의 큰 배열로 결합할 수도 있습니다. 이렇게 하려면 <xref:System.Array.Copy%2A?displayProperty=nameWithType> 메서드도 사용 합니다.

> [!NOTE]
> 이 단원에서는 문자열 배열을 단일 문자열로 조인 하는 방법에 대해 설명 하지 않습니다. 문자열 배열을 조인 하는 방법에 대 한 자세한 내용은 <xref:System.String.Join%2A?displayProperty=nameWithType> 메서드를 참조 하세요.

각 배열의 요소를 새 배열에 복사 하기 전에 먼저 새 배열을 수용할 수 있을 만큼 충분히 큰지 배열을 초기화 해야 합니다. 이 작업은 다음 두 가지 방법 중 하나로 수행할 수 있습니다.

- 새 요소를 추가 하기 전에 [`ReDim Preserve`](../../../language-reference/statements/redim-statement.md) 문을 사용 하 여 배열을 동적으로 확장 합니다. 가장 쉬운 방법 이지만, 많은 배열을 복사할 때 성능이 저하 되 고 메모리 소비가 과도 해질 수 있습니다.
- 새 큼 배열에 필요한 총 요소 수를 계산 하 고 각 소스 배열의 요소를 추가 합니다.

다음 예제에서는 두 번째 방법을 사용 하 여 10 개의 요소가 포함 된 네 개의 배열을 단일 배열에 추가 합니다.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

이 경우 소스 배열이 모두 작기 때문에 각 새 배열의 요소를 추가할 때 배열을 동적으로 확장할 수도 있습니다. 다음 예제에서는 해당 작업을 수행합니다.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>배열의 대 안으로 사용할 컬렉션

배열은 고정된 개수의 강력한 형식 개체를 만들고 작업하는 데 가장 유용합니다. 컬렉션은 개체 그룹에 대해 작업하는 보다 유연한 방법을 제공합니다. [`ReDim` 문으로](../../../language-reference/statements/redim-statement.md)배열의 크기를 명시적으로 변경 해야 하는 배열과 달리 컬렉션은 응용 프로그램의 요구가 변경 됨에 따라 동적으로 확장 및 축소 됩니다.

`ReDim`를 사용 하 여 배열에 대 한 차원을 변경한 경우 Visual Basic 새 배열을 만들고 이전 배열을 해제 합니다. 이 경우 실행 시간이 걸립니다. 따라서 작업 중인 항목 수가 자주 변경 되거나 필요한 항목의 최대 수를 예측할 수 없는 경우 일반적으로 컬렉션을 사용 하 여 더 나은 성능을 얻을 수 있습니다.

일부 컬렉션의 경우 키를 사용하여 개체를 신속하게 검색할 수 있도록 컬렉션에 추가하는 모든 개체에 키를 할당할 수 있습니다.

컬렉션에 단일 데이터 형식의 요소만 포함된 경우 <xref:System.Collections.Generic?displayProperty=nameWithType> 네임스페이스의 클래스 중 하나를 사용할 수 있습니다. 제네릭 컬렉션은 다른 데이터 형식을 추가할 수 없도록 형식 안전성을 적용합니다.

항목 컬렉션에 대한 자세한 내용은 [컬렉션](../../concepts/collections.md)을 참조하세요.

## <a name="related-topics"></a>관련 항목

|용어|정의|
|----------|----------------|
|[Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md)|배열의 차수 및 차원을 설명합니다.|
|[방법: Visual Basic에서 배열 변수 초기화](../../language-features/arrays/how-to-initialize-an-array-variable.md)|배열에 초기 값을 채우는 방법을 설명합니다.|
|[방법: Visual Basic에서 배열 정렬](../../language-features/arrays/how-to-sort-an-array.md)|배열의 요소를 사전순으로 정렬하는 방법을 보여 줍니다.|
|[방법: 한 배열에 다른 배열 할당](../../language-features/arrays/how-to-assign-one-array-to-another-array.md)|다른 배열 변수에 배열을 할당하는 규칙 및 단계를 설명합니다.|
|[배열 문제 해결](../../language-features/arrays/troubleshooting-arrays.md)|배열에서 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 설명합니다.|

## <a name="see-also"></a>참고 항목

- <xref:System.Array?displayProperty=nameWithType>
- [Dim 문](../../../language-reference/statements/dim-statement.md)
- [ReDim 문](../../../language-reference/statements/redim-statement.md)
