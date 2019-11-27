---
title: '방법: 확장 메서드 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: a19705a8f90833d48869df26a18d19b0ad1488e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340401"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="c9b71-102">방법: 확장명 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9b71-102">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="c9b71-103">확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="c9b71-104">확장 메서드를 선언 하 고 범위로 가져온 후에는 확장 하는 형식의 인스턴스 메서드와 같이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="c9b71-105">확장 메서드를 작성 하는 방법에 대 한 자세한 내용은 [방법: 확장 메서드 작성](./how-to-write-an-extension-method.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9b71-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="c9b71-106">다음 지침은 `PrintAndPunctuate`확장 메서드를 참조 합니다 .이 메서드는이를 호출 하는 문자열 인스턴스를 표시 하 고 두 번째 매개 변수에 대해 전송 되는 값을 `punc`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

<span data-ttu-id="c9b71-107">메서드는 호출 될 때 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-107">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="c9b71-108">확장 메서드를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="c9b71-108">To call an extension method</span></span>

1. <span data-ttu-id="c9b71-109">확장 메서드의 첫 번째 매개 변수 데이터 형식이 있는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="c9b71-110">`PrintAndPunctuate`의 경우 <xref:System.String> 변수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="c9b71-111">해당 변수는 확장 메서드를 호출 하 고, 해당 값은 첫 번째 매개 변수 `aString`에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="c9b71-112">다음 호출 문은 `Ready?`를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-112">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="c9b71-113">이 확장 메서드를 호출 하는 것은 하나의 매개 변수를 필요로 하는 <xref:System.String> 인스턴스 메서드 중 하나를 호출 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="c9b71-114">다른 문자열 변수를 선언 하 고 메서드를 다시 호출 하 여 문자열에서 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-114">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="c9b71-115">이 시간에 대 한 결과는 `or not!!!`입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-115">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="c9b71-116">예제</span><span class="sxs-lookup"><span data-stu-id="c9b71-116">Example</span></span>
 <span data-ttu-id="c9b71-117">다음 코드는 간단한 확장 메서드를 만들고 사용 하는 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b71-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a><span data-ttu-id="c9b71-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="c9b71-118">See also</span></span>

- [<span data-ttu-id="c9b71-119">방법: 확장명 메서드 작성</span><span class="sxs-lookup"><span data-stu-id="c9b71-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="c9b71-120">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="c9b71-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="c9b71-121">Visual Basic 범위</span><span class="sxs-lookup"><span data-stu-id="c9b71-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
