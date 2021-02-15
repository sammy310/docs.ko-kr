---
description: '자세한 정보: 방법: 확장 메서드 호출 (Visual Basic)'
title: '방법: 확장 메서드 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: ec5217526eb0cb28d172ab917df08a8bfe87fe95
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471385"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="da6f9-103">방법: 확장명 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da6f9-103">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="da6f9-104">확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-104">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="da6f9-105">확장 메서드를 선언 하 고 범위로 가져온 후에는 확장 하는 형식의 인스턴스 메서드와 같이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-105">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="da6f9-106">확장 메서드를 작성 하는 방법에 대 한 자세한 내용은 [방법: 확장 메서드 작성](./how-to-write-an-extension-method.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da6f9-106">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="da6f9-107">다음 지침은 확장 메서드를 참조 합니다 `PrintAndPunctuate` .이 메서드는이 메서드를 호출 하는 문자열 인스턴스를 표시 하 고 두 번째 매개 변수에 대해에서 전송 된 값을 표시 합니다 `punc` .</span><span class="sxs-lookup"><span data-stu-id="da6f9-107">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

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

<span data-ttu-id="da6f9-108">메서드는 호출 될 때 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-108">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="da6f9-109">확장 메서드를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="da6f9-109">To call an extension method</span></span>

1. <span data-ttu-id="da6f9-110">확장 메서드의 첫 번째 매개 변수 데이터 형식이 있는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-110">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="da6f9-111">의 경우 `PrintAndPunctuate` 변수가 필요 합니다 <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="da6f9-111">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="da6f9-112">해당 변수는 확장 메서드를 호출 하 고, 해당 값은 첫 번째 매개 변수에 바인딩됩니다 `aString` .</span><span class="sxs-lookup"><span data-stu-id="da6f9-112">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="da6f9-113">다음 호출 문이 표시 됩니다 `Ready?` .</span><span class="sxs-lookup"><span data-stu-id="da6f9-113">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="da6f9-114">이 확장 메서드에 대 한 호출은 <xref:System.String> 하나의 매개 변수를 필요로 하는 인스턴스 메서드 중 하나를 호출 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-114">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="da6f9-115">다른 문자열 변수를 선언 하 고 메서드를 다시 호출 하 여 문자열에서 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-115">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="da6f9-116">이 시간에 대 한 결과입니다 `or not!!!` .</span><span class="sxs-lookup"><span data-stu-id="da6f9-116">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="da6f9-117">예</span><span class="sxs-lookup"><span data-stu-id="da6f9-117">Example</span></span>

 <span data-ttu-id="da6f9-118">다음 코드는 간단한 확장 메서드를 만들고 사용 하는 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="da6f9-118">The following code is a complete example of the creation and use of a simple extension method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="da6f9-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="da6f9-119">See also</span></span>

- [<span data-ttu-id="da6f9-120">방법: 확장 메서드 쓰기</span><span class="sxs-lookup"><span data-stu-id="da6f9-120">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="da6f9-121">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="da6f9-121">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="da6f9-122">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="da6f9-122">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
