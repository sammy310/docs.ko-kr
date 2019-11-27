---
title: '방법: 확장 메서드 작성'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 697508f86ff4ff0a89150b65782121395d0fed12
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346008"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="0f13b-102">방법: 확장 메서드 작성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f13b-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="0f13b-103">확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="0f13b-104">확장 메서드는 해당 클래스의 인스턴스인 것 처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="0f13b-105">확장 메서드를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="0f13b-105">To define an extension method</span></span>

1. <span data-ttu-id="0f13b-106">Visual Studio에서 새 응용 프로그램 또는 기존 Visual Basic 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="0f13b-107">확장 메서드를 정의 하려는 파일의 맨 위에 다음 import 문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="0f13b-108">새 응용 프로그램 또는 기존 응용 프로그램의 모듈 내에서 [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) 특성을 사용 하 여 메서드 정의를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="0f13b-109">`Extension` 특성은 Visual Basic [모듈](../../../language-reference/statements/module-statement.md)의 메서드 (`Sub` 또는 `Function` 프로시저)에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="0f13b-110">`Class` 또는 `Structure`의 메서드에 적용 하는 경우 Visual Basic 컴파일러는 "모듈 에서만 확장 메서드를 정의할 수 있습니다." 라는 오류 [BC36551](../../../misc/bc36551.md)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="0f13b-111">첫 번째 매개 변수의 형식이 확장 하려는 데이터 형식 이어야 한다는 점만 제외 하 고 메서드를 일반적인 방식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="0f13b-112">예제</span><span class="sxs-lookup"><span data-stu-id="0f13b-112">Example</span></span>

<span data-ttu-id="0f13b-113">다음 예제에서는 모듈 `StringExtensions`에서 확장 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="0f13b-114">두 번째 모듈 `Module1`는 `StringExtensions`를 가져오고 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="0f13b-115">확장 메서드는 호출 될 때 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="0f13b-116">확장 메서드 `PrintAndPunctuate`는 문자열 인스턴스를 표시 하는 메서드를 사용 하 여 <xref:System.String> 클래스를 확장 한 다음 매개 변수로 전달 되는 문장 부호 기호의 문자열 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
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

<span data-ttu-id="0f13b-117">메서드는 두 개의 매개 변수로 정의 되며 하나를 사용 하 여 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="0f13b-118">메서드 정의의 첫 번째 매개 변수 `aString`은 메서드를 호출 하는 `String` 인스턴스인 `example`에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="0f13b-119">예제 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f13b-119">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="0f13b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f13b-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="0f13b-121">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="0f13b-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="0f13b-122">Module 문</span><span class="sxs-lookup"><span data-stu-id="0f13b-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="0f13b-123">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="0f13b-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0f13b-124">Visual Basic 범위</span><span class="sxs-lookup"><span data-stu-id="0f13b-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
