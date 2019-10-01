---
title: 확장 메서드(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: b5ad066fe9ec40d715702ed99537f45b21c558cf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701048"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="628dc-102">확장 메서드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="628dc-102">Extension Methods (Visual Basic)</span></span>

<span data-ttu-id="628dc-103">개발자는 확장 메서드를 사용 하 여 새 파생 형식을 만들지 않고 이미 정의 된 데이터 형식에 사용자 지정 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="628dc-104">확장 메서드를 사용 하면 기존 형식의 인스턴스 메서드인 것 처럼 호출할 수 있는 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="628dc-105">설명</span><span class="sxs-lookup"><span data-stu-id="628dc-105">Remarks</span></span>

<span data-ttu-id="628dc-106">확장 메서드는 `Sub` 프로시저 또는 `Function` 프로시저만 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="628dc-107">확장 속성, 필드 또는 이벤트를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="628dc-108">모든 확장 메서드는 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임 스페이스의 `<Extension>` 확장 특성으로 표시 되어야 하며 [모듈](../../../language-reference/statements/module-statement.md)에서 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-108">All extension methods must be marked with the extension attribute `<Extension>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace and must be defined in a [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="628dc-109">확장 메서드가 모듈 외부에서 정의 된 경우 Visual Basic 컴파일러는 "모듈 에서만 확장 메서드를 정의할 수 있습니다" 라는 오류 [BC36551](../../../misc/bc36551.md)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-109">If an extension method is defined outside a module, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules".</span></span>

<span data-ttu-id="628dc-110">확장 메서드 정의의 첫 번째 매개 변수는 메서드가 확장 하는 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-110">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="628dc-111">메서드가 실행 될 때 첫 번째 매개 변수는 메서드를 호출 하는 데이터 형식의 인스턴스에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-111">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>

<span data-ttu-id="628dc-112">@No__t-0 특성은 Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md)또는 [`Function`](../../../language-reference/statements/function-statement.md)에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-112">The `Extension` attribute can only be applied to a Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md), or [`Function`](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="628dc-113">@No__t-0 또는 `Structure`에 적용 하는 경우 Visual Basic 컴파일러는 오류 [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md)를 생성 하 고 "Extension ' 특성은 ' Module ', ' Sub ' 또는 ' Function ' 선언에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-113">If you apply it to a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md), "'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations".</span></span>

## <a name="example"></a><span data-ttu-id="628dc-114">예제</span><span class="sxs-lookup"><span data-stu-id="628dc-114">Example</span></span>

<span data-ttu-id="628dc-115">다음 예에서는 <xref:System.String> 데이터 형식에 대 한 `Print` 확장을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-115">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="628dc-116">메서드는 `Console.WriteLine`을 사용 하 여 문자열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-116">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="628dc-117">@No__t-0 메서드의 매개 변수 `aString`은 메서드가 @no__t 2 클래스를 확장 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-117">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>
  
[!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]

<span data-ttu-id="628dc-118">확장 메서드 정의는-0 @no__t 확장 특성으로 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-118">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="628dc-119">메서드가 정의 되는 모듈을 표시 하는 것은 선택 사항 이지만 각 확장 메서드는로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-119">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="628dc-120">확장 특성에 액세스 하려면 <xref:System.Runtime.CompilerServices>을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-120"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>

<span data-ttu-id="628dc-121">확장 메서드는 모듈 내 에서만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-121">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="628dc-122">일반적으로 확장 메서드가 정의 된 모듈은 호출 되는 모듈과 동일한 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-122">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="628dc-123">대신 확장 메서드를 포함 하는 모듈을 가져온 후 범위로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-123">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="628dc-124">@No__t를 포함 하는 모듈이 범위 내에 있는 경우 인수를 사용 하지 않는 일반 인스턴스 메서드인 것 처럼 메서드를 호출할 수 있습니다 (예: `ToUpper`).</span><span class="sxs-lookup"><span data-stu-id="628dc-124">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>

[!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]

<span data-ttu-id="628dc-125">다음 예제 `PrintAndPunctuate`은 2 개의 매개 변수로 정의 된 <xref:System.String>에 대 한 확장 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-125">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="628dc-126">첫 번째 매개 변수인 `aString`은 확장 메서드가 <xref:System.String>을 확장 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-126">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="628dc-127">두 번째 매개 변수인 `punc`은 메서드가 호출 될 때 인수로 전달 되는 문장 부호의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-127">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="628dc-128">메서드는 문자열 뒤에 문장 부호를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-128">The method displays the string followed by the punctuation marks.</span></span>

[!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]

<span data-ttu-id="628dc-129">@No__t-0에 대 한 문자열 인수를 전송 하 여 메서드를 호출 합니다 (`example.PrintAndPunctuate(".")`).</span><span class="sxs-lookup"><span data-stu-id="628dc-129">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>

<span data-ttu-id="628dc-130">다음 예에서는 `Print` 및 `PrintAndPunctuate`을 정의 하 고 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-130">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="628dc-131">확장 특성에 대 한 액세스를 사용 하기 위해 정의 모듈에 <xref:System.Runtime.CompilerServices>을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-131"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>


```vb
Imports System.Runtime.CompilerServices

Module StringExtensions

    <Extension()>
    Public Sub Print(aString As String)
        Console.WriteLine(aString)
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module
```

<span data-ttu-id="628dc-132">그런 다음 확장 메서드를 범위로 가져오고 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-132">Next, the extension methods are brought into scope and called:</span></span>

```vb
Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example As String = "Example string"
        example.Print()

        example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")
    End Sub
End Module
```

<span data-ttu-id="628dc-133">이러한 메서드 또는 유사한 확장 메서드를 실행 하려면 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="628dc-134">확장 메서드를 포함 하는 모듈이 범위에 있으면 IntelliSense에 표시 되 고 일반 인스턴스 메서드인 것 처럼 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>

<span data-ttu-id="628dc-135">메서드가 호출 되 면 첫 번째 매개 변수에 대해 인수가 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="628dc-136">이전 메서드 정의의 매개 변수 `aString`은이를 호출 하는 `String` 인스턴스인 `example`에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="628dc-137">컴파일러는 첫 번째 매개 변수로 전달 된 인수로 `example`을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>

<span data-ttu-id="628dc-138">@No__t로 설정 된 개체에 대해 확장 메서드가 호출 되 면 확장 메서드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="628dc-139">이는 일반 인스턴스 메서드에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="628dc-140">확장 메서드에서 `Nothing`을 명시적으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-140">You can explicitly check for `Nothing` in the extension method.</span></span>

## <a name="types-that-can-be-extended"></a><span data-ttu-id="628dc-141">확장할 수 있는 형식</span><span class="sxs-lookup"><span data-stu-id="628dc-141">Types that can be extended</span></span>

<span data-ttu-id="628dc-142">다음을 포함 하 여 Visual Basic 매개 변수 목록에서 표현할 수 있는 대부분의 형식에 대 한 확장 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>

- <span data-ttu-id="628dc-143">클래스 (참조 형식)</span><span class="sxs-lookup"><span data-stu-id="628dc-143">Classes (reference types)</span></span>
- <span data-ttu-id="628dc-144">구조체 (값 형식)</span><span class="sxs-lookup"><span data-stu-id="628dc-144">Structures (value types)</span></span>
- <span data-ttu-id="628dc-145">인터페이스</span><span class="sxs-lookup"><span data-stu-id="628dc-145">Interfaces</span></span>
- <span data-ttu-id="628dc-146">대리자</span><span class="sxs-lookup"><span data-stu-id="628dc-146">Delegates</span></span>
- <span data-ttu-id="628dc-147">ByRef 및 ByVal 인수</span><span class="sxs-lookup"><span data-stu-id="628dc-147">ByRef and ByVal arguments</span></span>
- <span data-ttu-id="628dc-148">제네릭 메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="628dc-148">Generic method parameters</span></span>
- <span data-ttu-id="628dc-149">배열</span><span class="sxs-lookup"><span data-stu-id="628dc-149">Arrays</span></span>

<span data-ttu-id="628dc-150">첫 번째 매개 변수는 확장 메서드가 확장 하는 데이터 형식을 지정 하므로이 매개 변수는 필수 이며 선택 사항이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="628dc-151">이러한 이유로 `Optional` 매개 변수와 `ParamArray` 매개 변수는 매개 변수 목록의 첫 번째 매개 변수가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>

<span data-ttu-id="628dc-152">확장 메서드는 런타임에 바인딩에서 고려 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="628dc-153">다음 예제에서 `anObject.PrintMe()`은 두 번째 @no__t 2 확장 메서드 정의가 삭제 된 경우와 동일한 예외로 <xref:System.MissingMemberException> 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>

[!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]

## <a name="best-practices"></a><span data-ttu-id="628dc-154">모범 사례</span><span class="sxs-lookup"><span data-stu-id="628dc-154">Best practices</span></span>

<span data-ttu-id="628dc-155">확장 메서드는 기존 형식을 확장 하는 편리 하 고 강력한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="628dc-156">그러나이를 성공적으로 사용 하려면 몇 가지 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="628dc-157">이러한 고려 사항은 주로 클래스 라이브러리의 작성자에 게 적용 되지만 확장 메서드를 사용 하는 모든 응용 프로그램에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>

<span data-ttu-id="628dc-158">일반적으로 사용자가 소유 하지 않은 형식에 추가 하는 확장 메서드는 사용자가 제어 하는 형식에 추가 된 확장 메서드 보다 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="628dc-159">사용자가 소유 하지 않은 클래스에서 다양 한 작업을 수행 하 여 확장 메서드를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>

- <span data-ttu-id="628dc-160">호출 하는 문의 인수와 호환 되는 시그니처를 포함 하는 액세스 가능한 인스턴스 멤버가 있고 인수에서 매개 변수에 대 한 축소 변환이 필요 하지 않은 경우, 인스턴스 메서드가 모든 확장 메서드에 대 한 기본 설정에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="628dc-161">따라서 특정 시점에 적절 한 인스턴스 메서드를 클래스에 추가 하면 사용 하는 기존 확장 멤버에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>

- <span data-ttu-id="628dc-162">확장 메서드 작성자는 다른 프로그래머가 원래 확장 보다 우선 순위가 높은 충돌 하는 확장 메서드를 작성 하는 것을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>

- <span data-ttu-id="628dc-163">고유한 네임 스페이스에 확장 메서드를 추가 하 여 견고성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="628dc-164">라이브러리의 소비자는 네임 스페이스를 포함 하거나 제외할 수 있으며, 라이브러리의 나머지 부분과 별도로 네임 스페이스 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>

- <span data-ttu-id="628dc-165">인터페이스 또는 클래스를 소유 하지 않는 경우에는 클래스를 확장 하는 것 보다 인터페이스를 확장 하는 것이 더 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="628dc-166">인터페이스를 변경 하면 해당 인터페이스를 구현 하는 모든 클래스에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="628dc-167">따라서 작성자는 인터페이스에서 메서드를 추가 하거나 변경할 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="628dc-168">그러나 클래스가 동일한 서명으로 확장 메서드를 사용 하는 두 인터페이스를 구현 하는 경우에는 두 확장 메서드가 모두 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>

- <span data-ttu-id="628dc-169">가능 하면 가장 구체적인 형식을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-169">Extend the most specific type you can.</span></span> <span data-ttu-id="628dc-170">형식 계층에서 다른 많은 형식이 파생 되는 형식을 선택 하는 경우 인스턴스 메서드 또는 다른 확장 메서드를 사용 하 여 사용자가 방해할 수 있는 다른 확장 메서드를 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>

## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="628dc-171">확장 메서드, 인스턴스 메서드 및 속성</span><span class="sxs-lookup"><span data-stu-id="628dc-171">Extension methods, instance methods, and properties</span></span>

<span data-ttu-id="628dc-172">범위 내 인스턴스 메서드에 호출 문의 인수와 호환 되는 시그니처가 있는 경우 해당 인스턴스 메서드는 모든 확장 메서드의 기본 설정에서 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="628dc-173">인스턴스 메서드는 확장 메서드가 더 잘 일치 하는 경우에도 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="628dc-174">다음 예제에서 `ExampleClass`은 `Integer` 형식의 매개 변수 하나를 포함 하는 `ExampleMethod` 이라는 인스턴스 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="628dc-175">확장 메서드 `ExampleMethod` `ExampleClass`을 확장 하 고 `Long` 형식의 매개 변수 하나를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>

[!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]

<span data-ttu-id="628dc-176">@No__t-1은 `Long`이 고 확장 메서드의 `Long` 매개 변수와만 호환 되기 때문에 다음 코드에서 `ExampleMethod`에 대 한 첫 번째 호출은 확장 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="628dc-177">@No__t-0에 대 한 두 번째 호출에는 `Integer` 인수 `arg2`가 있으며 인스턴스 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>

[!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]

<span data-ttu-id="628dc-178">이제 두 가지 방법으로 매개 변수의 데이터 형식을 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-178">Now reverse the data types of the parameters in the two methods:</span></span>

[!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]

<span data-ttu-id="628dc-179">이번에 `Main`의 코드는 인스턴스 메서드를 두 번 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="628dc-180">@No__t-0과 `arg2`은 둘 다 `Long`로 확대 변환 되므로 두 경우 모두 인스턴스 메서드가 확장 메서드 보다 우선적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>

[!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]

<span data-ttu-id="628dc-181">따라서 확장 메서드는 기존 인스턴스 메서드를 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="628dc-182">그러나 확장 메서드의 이름이 인스턴스 메서드와 동일 하지만 서명이 충돌 하지 않는 경우 두 메서드 모두에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="628dc-183">예를 들어, @no__t 클래스에 인수를 사용 하지 않는 `ExampleMethod` 이라는 메서드가 포함 된 경우 다음 코드와 같이 이름이 같지만 시그니처가 다른 확장 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>

[!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]

<span data-ttu-id="628dc-184">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-184">The output from this code is as follows:</span></span>

```console
Extension method
Instance method
```

<span data-ttu-id="628dc-185">속성을 사용 하는 경우 보다 간단 합니다. 확장 메서드가 확장 하는 클래스의 속성과 이름이 같은 경우 확장 메서드는 표시 되지 않으며 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>

## <a name="extension-method-precedence"></a><span data-ttu-id="628dc-186">확장 메서드 우선 순위</span><span class="sxs-lookup"><span data-stu-id="628dc-186">Extension method precedence</span></span>

<span data-ttu-id="628dc-187">시그니처가 동일한 두 확장 메서드가 범위에 있고 액세스할 수 있는 경우 우선 순위가 높은 하나는 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="628dc-188">확장 메서드의 우선 순위는 메서드를 범위로 가져오는 데 사용 되는 메커니즘을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="628dc-189">다음 목록에서는 우선 순위 계층을 최상위에서 최하위로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>

1. <span data-ttu-id="628dc-190">현재 모듈 내에 정의 된 확장 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-190">Extension methods defined inside the current module.</span></span>

2. <span data-ttu-id="628dc-191">현재 네임 스페이스 또는 부모 네임 스페이스의 데이터 형식 내에 정의 된 확장 메서드로, 하위 네임 스페이스가 부모 네임 스페이스 보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>

3. <span data-ttu-id="628dc-192">현재 파일의 모든 형식 가져오기 안에 정의 된 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="628dc-192">Extension methods defined inside any type imports in the current file.</span></span>

4. <span data-ttu-id="628dc-193">현재 파일의 네임 스페이스 가져오기 안에 정의 된 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="628dc-193">Extension methods defined inside any namespace imports in the current file.</span></span>

5. <span data-ttu-id="628dc-194">모든 프로젝트 수준 형식 가져오기 내에 정의 된 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="628dc-194">Extension methods defined inside any project-level type imports.</span></span>

6. <span data-ttu-id="628dc-195">프로젝트 수준 네임 스페이스 가져오기 안에 정의 된 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="628dc-195">Extension methods defined inside any project-level namespace imports.</span></span>

<span data-ttu-id="628dc-196">우선 순위에 의해 모호성을 해결 하지 못하는 경우 정규화 된 이름을 사용 하 여 호출 하는 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="628dc-197">이전 예제의 `Print` 메서드가 `StringExtensions` 이라는 모듈에서 정의 된 경우 정규화 된 이름은 `example.Print()`이 아닌 `StringExtensions.Print(example)`입니다.</span><span class="sxs-lookup"><span data-stu-id="628dc-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>

## <a name="see-also"></a><span data-ttu-id="628dc-198">참조</span><span class="sxs-lookup"><span data-stu-id="628dc-198">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="628dc-199">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="628dc-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="628dc-200">Module 문</span><span class="sxs-lookup"><span data-stu-id="628dc-200">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="628dc-201">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="628dc-201">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="628dc-202">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="628dc-202">Optional Parameters</span></span>](optional-parameters.md)
- [<span data-ttu-id="628dc-203">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="628dc-203">Parameter Arrays</span></span>](parameter-arrays.md)
- [<span data-ttu-id="628dc-204">특성 개요</span><span class="sxs-lookup"><span data-stu-id="628dc-204">Attributes overview</span></span>](../../concepts/attributes/index.md)
- [<span data-ttu-id="628dc-205">Visual Basic 범위</span><span class="sxs-lookup"><span data-stu-id="628dc-205">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
