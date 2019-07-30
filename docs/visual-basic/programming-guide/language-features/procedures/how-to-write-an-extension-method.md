---
title: '방법: 확장 메서드 (Visual Basic)를 작성 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 7a7a9d16d9f69071e9d1dacb0558f7ca92e1d21e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631028"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="6daba-102">방법: 확장 메서드 (Visual Basic)를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="6daba-103">확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="6daba-104">확장 메서드는 해당 클래스의 인스턴스인 것 처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="6daba-105">확장 메서드를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="6daba-105">To define an extension method</span></span>

1. <span data-ttu-id="6daba-106">Visual Studio에서 새 응용 프로그램 또는 기존 Visual Basic 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="6daba-107">확장 메서드를 정의 하려는 파일의 맨 위에 다음 import 문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="6daba-108">새 응용 프로그램 또는 기존 응용 프로그램의 모듈 내에서 확장 특성을 사용 하 여 메서드 정의를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="6daba-109">첫 번째 매개 변수의 형식이 확장 하려는 데이터 형식 이어야 한다는 점만 제외 하 고 메서드를 일반적인 방식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName (ByVal para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="6daba-110">예제</span><span class="sxs-lookup"><span data-stu-id="6daba-110">Example</span></span>
 <span data-ttu-id="6daba-111">다음 예제에서는 모듈 `StringExtensions`의 확장 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="6daba-112">두 번째 모듈인 `Module1`는를 가져오고 `StringExtensions` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="6daba-113">확장 메서드는 호출 될 때 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="6daba-114">확장 메서드 `PrintAndPunctuate` 는 문자열 <xref:System.String> 인스턴스를 표시 하는 메서드를 사용 하 여 클래스를 확장 하 고,로 전달 된 문장 부호 기호 문자열을 매개 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1
  
    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub
    
End Module
```
  
 <span data-ttu-id="6daba-115">메서드는 두 개의 매개 변수로 정의 되며 하나를 사용 하 여 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="6daba-116">메서드 정의의 첫 `aString`번째 매개 변수는 메서드를 호출 하 `example`는의 `String` 인스턴스인에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="6daba-117">예제 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6daba-117">The output of the example is as follows:</span></span>
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="6daba-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="6daba-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="6daba-119">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="6daba-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="6daba-120">Module 문</span><span class="sxs-lookup"><span data-stu-id="6daba-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="6daba-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="6daba-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6daba-122">Visual Basic 범위</span><span class="sxs-lookup"><span data-stu-id="6daba-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
