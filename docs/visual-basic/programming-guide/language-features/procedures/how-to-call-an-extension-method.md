---
title: '방법: 확장명 메서드 (Visual Basic) 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863677"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="69ec0-102">방법: 확장명 메서드 (Visual Basic) 호출</span><span class="sxs-lookup"><span data-stu-id="69ec0-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="69ec0-103">확장 메서드를 사용 하면 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="69ec0-104">확장 메서드는 선언 되 고 범위로, 후 확장 하는 형식의 인스턴스 메서드처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="69ec0-105">확장 메서드를 작성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 확장명 메서드 작성](./how-to-write-an-extension-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="69ec0-106">확장 메서드를 다음 지침을 참조 하세요 `PrintAndPunctuate`, 두 번째 매개 변수에서 보내지는 뒤에 원하는 값으로 호출 하는 문자열 인스턴스가 표시 됩니다 `punc`합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="69ec0-107">메서드 호출 될 때 범위에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="69ec0-108">확장 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-108">To call an extension method</span></span>  
  
1. <span data-ttu-id="69ec0-109">확장 메서드의 첫 번째 매개 변수의 데이터 형식이 있는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="69ec0-110">에 대 한 `PrintAndPunctuate`, 필요한를 <xref:System.String> 변수:</span><span class="sxs-lookup"><span data-stu-id="69ec0-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. <span data-ttu-id="69ec0-111">변수는 확장 메서드를 호출 하 고 해당 값이 첫 번째 매개 변수에 바인딩된 `aString`합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="69ec0-112">다음 호출 문을 표시 됩니다 `Ready?`합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="69ec0-113">이 확장 메서드를 호출 하는 등의 하나를 호출 하 여 <xref:System.String> 인스턴스 매개 변수 하나 필요로 하는 메서드:</span><span class="sxs-lookup"><span data-stu-id="69ec0-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. <span data-ttu-id="69ec0-114">다른 문자열 변수를 선언 하 고 모든 문자열을 사용 하 여 작동 하는지 확인 하려면 다시 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="69ec0-115">결과이 시간은: `or not!!!`합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69ec0-116">예제</span><span class="sxs-lookup"><span data-stu-id="69ec0-116">Example</span></span>  
 <span data-ttu-id="69ec0-117">다음 코드 작성의 전체 예제 이며 간단한 확장 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ec0-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69ec0-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="69ec0-118">See also</span></span>

- [<span data-ttu-id="69ec0-119">방법: 확장명 메서드 작성</span><span class="sxs-lookup"><span data-stu-id="69ec0-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="69ec0-120">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="69ec0-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="69ec0-121">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="69ec0-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
