---
title: '방법: 확장명 메서드 (Visual Basic) 작성'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 00d62d275f7afc06e066a375dc1ffcd74b23c9ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666003"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="8ff0b-102">방법: 확장명 메서드 (Visual Basic) 작성</span><span class="sxs-lookup"><span data-stu-id="8ff0b-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="8ff0b-103">확장 메서드를 사용 하면 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="8ff0b-104">해당 클래스의 인스턴스인 것 처럼 확장 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="8ff0b-105">확장 메서드를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="8ff0b-105">To define an extension method</span></span>  
  
1. <span data-ttu-id="8ff0b-106">Visual Studio에서 새 또는 기존 Visual Basic 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2. <span data-ttu-id="8ff0b-107">확장 메서드를 정의 하려는 파일의 맨 위에 있는 다음 import 문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3. <span data-ttu-id="8ff0b-108">기존 또는 새 응용 프로그램에서 모듈 내에서 확장 특성을 사용 하 여 메서드 정의 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4. <span data-ttu-id="8ff0b-109">일반적인 방법으로 메서드를 선언 합니다 점을 제외 하 고 되는 첫 번째 매개 변수 형식의 확장 하려는 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="8ff0b-110">예제</span><span class="sxs-lookup"><span data-stu-id="8ff0b-110">Example</span></span>  
 <span data-ttu-id="8ff0b-111">다음 예제에서는 모듈의 확장 메서드를 선언 `StringExtensions`합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="8ff0b-112">두 번째 모듈 `Module1`을 가져옵니다 `StringExtensions` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="8ff0b-113">확장 메서드를 호출 했을 때 범위에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="8ff0b-114">확장 메서드 `PrintAndPunctuate` 확장 된 <xref:System.String> 매개 변수로 전송 문장 부호 기호는 문자열 뒤에 문자열 인스턴스를 표시 하는 메서드를 사용 하 여 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
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
  
 <span data-ttu-id="8ff0b-115">메서드 중 하나만 호출 두 개의 매개 변수를 사용 하 여 정의 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="8ff0b-116">첫 번째 매개 변수를 `aString`, 메서드의 정의에 바인딩되어 `example`, 인스턴스의 `String` 메서드를 호출 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="8ff0b-117">예제 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff0b-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="8ff0b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ff0b-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="8ff0b-119">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="8ff0b-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="8ff0b-120">Module 문</span><span class="sxs-lookup"><span data-stu-id="8ff0b-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="8ff0b-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="8ff0b-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="8ff0b-122">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="8ff0b-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
