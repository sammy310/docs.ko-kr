---
title: 순수 함수로 리팩터링
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 22b371c6136836d6e0f1281f824b69378c0d3e4a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346517"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Refactoring Into Pure Functions (Visual Basic)

순수 함수 변환의 중요한 측면은 순수 함수를 사용하여 코드를 리팩터링하는 방법을 습득하는 것입니다.

이 단원의 앞 부분에서 설명한 것처럼 순수 함수에는 두 가지 유용한 특징이 있습니다.

- 순수 함수는 의도하지 않은 결과를 발생시키지 않습니다. 함수는 함수 외부에 있는 형식의 데이터나 변수를 변경하지 않습니다.

- 순수 함수는 일관성이 있습니다. 동일한 입력 데이터의 집합이 제공되는 경우 항상 동일한 출력 값을 반환합니다.

 함수형 프로그래밍으로 전환하는 한 가지 방법은 기존 코드를 리팩터링하여 의도하지 않은 불필요한 결과와 외부 종속성을 없애는 것입니다. 이런 식으로 기존 코드의 순수 함수 버전을 만들 수 있습니다.

이 항목에서는 순수 함수의 개념과 순수 함수가 의미하지 않는 것에 대해 설명합니다. The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.

## <a name="eliminating-side-effects-and-external-dependencies"></a>의도하지 않은 결과 및 외부 종속성 제거

다음 예제에서는 두 가지 비순수 함수와 순수 함수를 대조합니다.

### <a name="non-pure-function-that-changes-a-class-member"></a>클래스 멤버를 변경하는 비순수 함수

다음 코드에서 `HyphenatedConcat` 함수는 클래스에서 `aMember` 데이터 멤버를 수정하기 때문에 순수 함수가 아닙니다.

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

이 코드의 결과는 다음과 같습니다.

```console
StringOne-StringTwo
```

Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a  `shared` member or an instance member. 순수 함수는 함수 외부에 있는 데이터를 변경하지 않습니다.

### <a name="non-pure-function-that-changes-an-argument"></a>인수를 변경하는 비순수 함수

또한 이 동일한 함수의 다음 버전은 매개 변수 `sb`의 내용을 수정하기 때문에 순수 함수가 아닙니다.

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

`HyphenatedConcat` 함수가 <xref:System.Text.StringBuilder.Append%2A> 멤버 함수를 호출하여 첫 번째 매개 변수의 값(상태)을 변경했기 때문에 이 프로그램 버전은 첫 번째 버전과 동일한 출력을 생성합니다. 이러한 변경은 `HyphenatedConcat`에서 값에 의한 호출(call-by-value) 매개 변수 전달을 사용함에도 불구하고 발생합니다.

> [!IMPORTANT]
> 참조 형식의 경우 값에 의해 매개 변수를 전달하면 개체에 대한 참조의 복사본이 전달됩니다. 이 복사본은 참조 변수가 새 개체에 할당될 때까지 원래 참조와 동일한 인스턴스 데이터와 연결되어 있습니다. 참조에 의한 호출(call-by-reference)을 사용하는 경우 함수에서 반드시 매개 변수를 수정해야 할 필요가 없습니다.

### <a name="pure-function"></a>순수 함수

이 다음 버전의 프로그램에서는 `HyphenatedConcat` 함수를 순수 함수로 구현하는 방법을 보여 줍니다.

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

이 버전은 동일한 출력 `StringOne-StringTwo`를 생성합니다. 연결된 값을 유지하기 위해 해당 값은 중간 변수 `s2`에 저장됩니다.

매우 유용할 수 있는 한 가지 방법은 로컬로는 순수하지 않지만(즉, 지역 변수를 선언하고 수정함) 전역적으로는 순수한 함수를 작성하는 것입니다. 이러한 함수는 유용한 조합성(composability) 특징을 많이 갖고 있지만 간단한 루프가 동일한 작업을 수행하는 경우 재귀를 사용해야 하는 등의 더욱 꼬인(convoluted) 함수형 프로그래밍 특징을 방지합니다.

## <a name="standard-query-operators"></a>표준 쿼리 연산자

표준 쿼리 연산자의 중요한 특징은 순수 함수로 구현된다는 점입니다.

For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

## <a name="see-also"></a>참조

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
