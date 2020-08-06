---
title: '연습: 동적 개체 만들기 및 사용(C# 및 Visual Basic)'
description: 이 연습에서는 동적 개체를 만들고 사용하는 방법을 알아봅니다. 사용자 지정 동적 개체를 만들고 'IronPython' 라이브러리를 사용하는 프로젝트를 만듭니다.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dynamic objects [Visual Basic]
- dynamic objects
- dynamic objects [C#]
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
ms.openlocfilehash: 144651d3b14f6f6093ab07f1df7be10e6d05ae89
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381257"
---
# <a name="walkthrough-creating-and-using-dynamic-objects-c-and-visual-basic"></a><span data-ttu-id="01d31-104">연습: 동적 개체 만들기 및 사용(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01d31-104">Walkthrough: Creating and Using Dynamic Objects (C# and Visual Basic)</span></span>

<span data-ttu-id="01d31-105">동적 개체는 컴파일 시간이 아닌 런타임에 속성 및 메서드와 같은 멤버를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-105">Dynamic objects expose members such as properties and methods at run time, instead of at compile time.</span></span> <span data-ttu-id="01d31-106">이를 통해 형식 또는 정적 형식과 일치하지 않는 구조와 작동할 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-106">This enables you to create objects to work with structures that do not match a static type or format.</span></span> <span data-ttu-id="01d31-107">예를 들어 동적 개체를 사용하여 DOM(문서 개체 모델)을 참조할 수 있습니다. DOM에는 유효한 HTML 마크업 요소 및 특성의 조합을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-107">For example, you can use a dynamic object to reference the HTML Document Object Model (DOM), which can contain any combination of valid HTML markup elements and attributes.</span></span> <span data-ttu-id="01d31-108">각 HTML 문서는 고유하므로, 특정 HTML 문서에 대한 멤버는 런타임에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-108">Because each HTML document is unique, the members for a particular HTML document are determined at run time.</span></span> <span data-ttu-id="01d31-109">HTML 요소의 특성을 참조하는 일반적인 방법은 요소의 `GetProperty` 메서드에 특성의 이름을 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-109">A common method to reference an attribute of an HTML element is to pass the name of the attribute to the `GetProperty` method of the element.</span></span> <span data-ttu-id="01d31-110">HTML 요소 `<div id="Div1">`의 `id` 특성을 참조하려면 먼저 `<div>` 요소에 대한 참조를 가져온 다음 `divElement.GetProperty("id")`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-110">To reference the `id` attribute of the HTML element `<div id="Div1">`, you first obtain a reference to the `<div>` element, and then use `divElement.GetProperty("id")`.</span></span> <span data-ttu-id="01d31-111">동적 개체를 사용하는 경우 `id` 특성을 `divElement.id`로서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-111">If you use a dynamic object, you can reference the `id` attribute as `divElement.id`.</span></span>  
  
 <span data-ttu-id="01d31-112">동적 개체를 사용하면 IronPython 및 IronRuby와 같은 동적 언어에 편리하게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-112">Dynamic objects also provide convenient access to dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="01d31-113">동적 개체를 사용하면 런타임에 해석되는 동적 스크립트를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-113">You can use a dynamic object to refer to a dynamic script that is interpreted at run time.</span></span>  
  
 <span data-ttu-id="01d31-114">런타임에 바인딩을 사용하여 동적 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-114">You reference a dynamic object by using late binding.</span></span> <span data-ttu-id="01d31-115">C#에서는 런타임에 바인딩된 개체의 형식을 `dynamic`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-115">In C#, you specify the type of a late-bound object as `dynamic`.</span></span> <span data-ttu-id="01d31-116">Visual Basic에서는 런타임에 바인딩된 개체의 형식을 `Object`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-116">In Visual Basic, you specify the type of a late-bound object as `Object`.</span></span> <span data-ttu-id="01d31-117">자세한 내용은 [dynamic](../../language-reference/builtin-types/reference-types.md) 및 [초기 바인딩 및 런타임에 바인딩](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01d31-117">For more information, see [dynamic](../../language-reference/builtin-types/reference-types.md) and [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).</span></span>  
  
 <span data-ttu-id="01d31-118"><xref:System.Dynamic?displayProperty=nameWithType> 네임스페이스의 클래스를 사용하여 사용자 지정 동적 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-118">You can create custom dynamic objects by using the classes in the <xref:System.Dynamic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="01d31-119">예를 들어 <xref:System.Dynamic.ExpandoObject>를 만들고 해당 개체의 멤버를 런타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-119">For example, you can create an <xref:System.Dynamic.ExpandoObject> and specify the members of that object at run time.</span></span> <span data-ttu-id="01d31-120"><xref:System.Dynamic.DynamicObject> 클래스를 상속하는 고유한 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-120">You can also create your own type that inherits the <xref:System.Dynamic.DynamicObject> class.</span></span> <span data-ttu-id="01d31-121">그런 다음 런타임 동적 기능을 제공하도록 <xref:System.Dynamic.DynamicObject> 클래스의 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-121">You can then override the members of the <xref:System.Dynamic.DynamicObject> class to provide run-time dynamic functionality.</span></span>  
  
 <span data-ttu-id="01d31-122">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-122">In this walkthrough you will perform the following tasks:</span></span>  
  
- <span data-ttu-id="01d31-123">텍스트 파일의 내용을 개체의 속성으로서 동적으로 노출하는 사용자 지정 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-123">Create a custom object that dynamically exposes the contents of a text file as properties of an object.</span></span>  
  
- <span data-ttu-id="01d31-124">`IronPython` 라이브러리를 사용하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-124">Create a project that uses an `IronPython` library.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01d31-125">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="01d31-125">Prerequisites</span></span>  

<span data-ttu-id="01d31-126">이 연습을 완료하려면 .NET용 [IronPython](https://ironpython.net/)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-126">You need [IronPython](https://ironpython.net/) for .NET to complete this walkthrough.</span></span> <span data-ttu-id="01d31-127">[다운로드 페이지](https://ironpython.net/download/)로 이동하여 최신 버전을 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="01d31-127">Go to their [Download page](https://ironpython.net/download/) to obtain the latest version.</span></span>
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-custom-dynamic-object"></a><span data-ttu-id="01d31-128">사용자 지정 동적 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="01d31-128">Creating a Custom Dynamic Object</span></span>

<span data-ttu-id="01d31-129">이 연습에서 만드는 첫 번째 프로젝트는 텍스트 파일의 내용을 검색하는 사용자 지정 동적 개체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-129">The first project that you create in this walkthrough defines a custom dynamic object that searches the contents of a text file.</span></span> <span data-ttu-id="01d31-130">검색할 텍스트는 동적 속성의 이름으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-130">Text to search for is specified by the name of a dynamic property.</span></span> <span data-ttu-id="01d31-131">예를 들어, 호출 코드가 `dynamicFile.Sample`을 지정하면 동적 클래스는 "Sample"로 시작하는 파일의 모든 줄을 포함하는 문자열의 제네릭 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-131">For example, if calling code specifies `dynamicFile.Sample`, the dynamic class returns a generic list of strings that contains all of the lines from the file that begin with "Sample".</span></span> <span data-ttu-id="01d31-132">검색은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-132">The search is case-insensitive.</span></span> <span data-ttu-id="01d31-133">동적 클래스는 또한 두 개의 선택적 인수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-133">The dynamic class also supports two optional arguments.</span></span> <span data-ttu-id="01d31-134">첫 번째 인수는 동적 클래스가 행의 시작, 행의 끝 또는 행의 어디에서나 일치를 검색하도록 지정하는 검색 옵션 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-134">The first argument is a search option enum value that specifies that the dynamic class should search for matches at the start of the line, the end of the line, or anywhere in the line.</span></span> <span data-ttu-id="01d31-135">두 번째 인수는 동적 클래스가 검색 전에 각 행의 선행 및 후행 공백을 잘라내야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-135">The second argument specifies that the dynamic class should trim leading and trailing spaces from each line before searching.</span></span> <span data-ttu-id="01d31-136">예를 들어 호출 코드가 `dynamicFile.Sample(StringSearchOption.Contains)`을 지정하면 동적 클래스는 한 줄의 어디에서나 "Sample"을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-136">For example, if calling code specifies `dynamicFile.Sample(StringSearchOption.Contains)`, the dynamic class searches for "Sample" anywhere in a line.</span></span> <span data-ttu-id="01d31-137">호출 코드가 `dynamicFile.Sample(StringSearchOption.StartsWith, false)`을 지정하면 동적 클래스는 각 줄의 시작 부분에서 "Sample"을 검색하고, 선행 및 후행 공백을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-137">If calling code specifies `dynamicFile.Sample(StringSearchOption.StartsWith, false)`, the dynamic class searches for "Sample" at the start of each line, and does not remove leading and trailing spaces.</span></span> <span data-ttu-id="01d31-138">동적 클래스의 기본 동작은 각 줄의 시작 부분에서 일치를 검색하고 선행 및 후행 공백을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-138">The default behavior of the dynamic class is to search for a match at the start of each line and to remove leading and trailing spaces.</span></span>  
  
### <a name="to-create-a-custom-dynamic-class"></a><span data-ttu-id="01d31-139">사용자 지정 동적 클래스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="01d31-139">To create a custom dynamic class</span></span>  
  
1. <span data-ttu-id="01d31-140">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-140">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="01d31-141">**파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-141">On the **File** menu, point to **New** and then click **Project**.</span></span>  
  
3. <span data-ttu-id="01d31-142">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-142">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="01d31-143">**템플릿** 창에서 **콘솔 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-143">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="01d31-144">**이름** 상자에 `DynamicSample`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-144">In the **Name** box, type `DynamicSample`, and then click **OK**.</span></span> <span data-ttu-id="01d31-145">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-145">The new project is created.</span></span>  
  
4. <span data-ttu-id="01d31-146">DynamicSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **클래스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-146">Right-click the DynamicSample project and point to **Add**, and then click **Class**.</span></span> <span data-ttu-id="01d31-147">**이름** 상자에 `ReadOnlyFile`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-147">In the **Name** box, type `ReadOnlyFile`, and then click **OK**.</span></span> <span data-ttu-id="01d31-148">ReadOnlyFile 클래스가 포함된 새 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-148">A new file is added that contains the ReadOnlyFile class.</span></span>  
  
5. <span data-ttu-id="01d31-149">ReadOnlyFile.cs 또는 ReadOnlyFile.vb 파일 맨 위에 다음 코드를 추가하여 <xref:System.IO?displayProperty=nameWithType> 및 <xref:System.Dynamic?displayProperty=nameWithType> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-149">At the top of the ReadOnlyFile.cs or ReadOnlyFile.vb file, add the following code to import the <xref:System.IO?displayProperty=nameWithType> and <xref:System.Dynamic?displayProperty=nameWithType> namespaces.</span></span>  

    [!code-csharp[VbDynamicWalkthrough#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#1)]
    [!code-vb[VbDynamicWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#1)]  

6. <span data-ttu-id="01d31-150">사용자 지정 동적 개체는 열거형을 사용하여 검색 기준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-150">The custom dynamic object uses an enum to determine the search criteria.</span></span> <span data-ttu-id="01d31-151">Class 문 앞에 다음 열거형 정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-151">Before the class statement, add the following enum definition.</span></span>  
  
    [!code-csharp[VbDynamicWalkthrough#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#2)]
    [!code-vb[VbDynamicWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#2)]
  
7. <span data-ttu-id="01d31-152">다음 코드 예제와 같이, `DynamicObject` 클래스를 상속하도록 class 문을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-152">Update the class statement to inherit the `DynamicObject` class, as shown in the following code example.</span></span>  
  
    [!code-csharp[VbDynamicWalkthrough#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#3)]
    [!code-vb[VbDynamicWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#3)]

8. <span data-ttu-id="01d31-153">다음 코드를 `ReadOnlyFile` 클래스에 추가하여 파일 경로의 전용 필드 및 `ReadOnlyFile` 클래스의 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-153">Add the following code to the `ReadOnlyFile` class to define a private field for the file path and a constructor for the `ReadOnlyFile` class.</span></span>  
  
    [!code-csharp[VbDynamicWalkthrough#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#4)]
    [!code-vb[VbDynamicWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#4)]
  
9. <span data-ttu-id="01d31-154">다음 `GetPropertyValue` 메서드를 `ReadOnlyFile` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-154">Add the following `GetPropertyValue` method to the `ReadOnlyFile` class.</span></span> <span data-ttu-id="01d31-155">`GetPropertyValue` 메서드는 검색 기준을 입력으로 가져오고 해당 검색 기준과 일치하는 텍스트 파일로부터 줄을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-155">The `GetPropertyValue` method takes, as input, search criteria and returns the lines from a text file that match that search criteria.</span></span> <span data-ttu-id="01d31-156">`ReadOnlyFile` 클래스가 제공하는 동적 메서드는 `GetPropertyValue` 메서드를 호출하여 각 결과를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-156">The dynamic methods provided by the `ReadOnlyFile` class call the `GetPropertyValue` method to retrieve their respective results.</span></span>  
  
    [!code-csharp[VbDynamicWalkthrough#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#5)]
    [!code-vb[VbDynamicWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#5)]  
  
10. <span data-ttu-id="01d31-157">`GetPropertyValue` 메서드 뒤에 다음 코드를 추가하여 <xref:System.Dynamic.DynamicObject> 클래스의 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-157">After the `GetPropertyValue` method, add the following code to override the <xref:System.Dynamic.DynamicObject.TryGetMember%2A> method of the <xref:System.Dynamic.DynamicObject> class.</span></span> <span data-ttu-id="01d31-158">동적 클래스의 멤버를 요청했는데 지정된 인수가 없는 경우 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-158">The <xref:System.Dynamic.DynamicObject.TryGetMember%2A> method is called when a member of a dynamic class is requested and no arguments are specified.</span></span> <span data-ttu-id="01d31-159">`binder` 인수는 참조된 멤버에 대한 정보를 포함하며, `result` 인수는 지정된 멤버에 대해 반환된 결과를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-159">The `binder` argument contains information about the referenced member, and the `result` argument references the result returned for the specified member.</span></span> <span data-ttu-id="01d31-160"><xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드는 요청한 멤버가 있는 경우 `true`, 없는 경우 `false`를 반환하는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-160">The <xref:System.Dynamic.DynamicObject.TryGetMember%2A> method returns a Boolean value that returns `true` if the requested member exists; otherwise it returns `false`.</span></span>  
  
    [!code-csharp[VbDynamicWalkthrough#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#6)]
    [!code-vb[VbDynamicWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#6)]
  
11. <span data-ttu-id="01d31-161">`TryGetMember` 메서드 뒤에 다음 코드를 추가하여 <xref:System.Dynamic.DynamicObject> 클래스의 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-161">After the `TryGetMember` method, add the following code to override the <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> method of the <xref:System.Dynamic.DynamicObject> class.</span></span> <span data-ttu-id="01d31-162">인수를 사용하여 동적 클래스의 멤버를 요청하면 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-162">The <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> method is called when a member of a dynamic class is requested with arguments.</span></span> <span data-ttu-id="01d31-163">`binder` 인수는 참조된 멤버에 대한 정보를 포함하며, `result` 인수는 지정된 멤버에 대해 반환된 결과를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-163">The `binder` argument contains information about the referenced member, and the `result` argument references the result returned for the specified member.</span></span> <span data-ttu-id="01d31-164">`args` 인수는 멤버에 전달되는 인수의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-164">The `args` argument contains an array of the arguments that are passed to the member.</span></span> <span data-ttu-id="01d31-165"><xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드는 요청한 멤버가 있는 경우 `true`, 없는 경우 `false`를 반환하는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-165">The <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> method returns a Boolean value that returns `true` if the requested member exists; otherwise it returns `false`.</span></span>  
  
    <span data-ttu-id="01d31-166">`TryInvokeMember` 메서드의 사용자 지정 버전은 첫 번째 인수로 이전 단계에서 정의한 `StringSearchOption` 열거형의 값을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-166">The custom version of the `TryInvokeMember` method expects the first argument to be a value from the `StringSearchOption` enum that you defined in a previous step.</span></span> <span data-ttu-id="01d31-167">`TryInvokeMember` 메서드는 두 번째 인수로 부울 값을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-167">The `TryInvokeMember` method expects the second argument to be a Boolean value.</span></span> <span data-ttu-id="01d31-168">하나 또는 두 인수가 유효한 값인 경우 결과를 검색할 수 있도록 `GetPropertyValue` 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-168">If one or both arguments are valid values, they are passed to the `GetPropertyValue` method to retrieve the results.</span></span>  
  
    [!code-csharp[VbDynamicWalkthrough#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#7)]
    [!code-vb[VbDynamicWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#7)]
  
12. <span data-ttu-id="01d31-169">파일을 저장한 후 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-169">Save and close the file.</span></span>  
  
#### <a name="to-create-a-sample-text-file"></a><span data-ttu-id="01d31-170">샘플 텍스트 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="01d31-170">To create a sample text file</span></span>  
  
1. <span data-ttu-id="01d31-171">DynamicSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-171">Right-click the DynamicSample project and point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="01d31-172">**설치된 템플릿** 창에서 **일반**을 선택한 다음 **텍스트 파일** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-172">In the **Installed Templates** pane, select **General**, and then select the **Text File** template.</span></span> <span data-ttu-id="01d31-173">**이름** 상자에 있는 기본 이름 TextFile1.txt를 그대로 두고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-173">Leave the default name of TextFile1.txt in the **Name** box, and then click **Add**.</span></span> <span data-ttu-id="01d31-174">새 텍스트 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-174">A new text file is added to the project.</span></span>  
  
2. <span data-ttu-id="01d31-175">TextFile1.txt 파일에 다음 텍스트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-175">Copy the following text to the TextFile1.txt file.</span></span>  
  
    ```text  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (https://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (https://www.graphicdesigninstitute.com/)
    Supplier: Fabrikam, Inc. (https://www.fabrikam.com/)
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3. <span data-ttu-id="01d31-176">파일을 저장한 후 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-176">Save and close the file.</span></span>  
  
#### <a name="to-create-a-sample-application-that-uses-the-custom-dynamic-object"></a><span data-ttu-id="01d31-177">사용자 지정 동적 개체를 사용하는 샘플 애플리케이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="01d31-177">To create a sample application that uses the custom dynamic object</span></span>  
  
1. <span data-ttu-id="01d31-178">**솔루션 탐색기**에서, Visual Basic을 사용 중인 경우 Module1.vb 파일, Visual C#을 사용 중인 경우 Program.cs 파일을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-178">In **Solution Explorer**, double-click the Module1.vb file if you are using Visual Basic or the Program.cs file if you are using Visual C#.</span></span>  
  
2. <span data-ttu-id="01d31-179">Main 프로시저에 다음 코드를 추가하여 TextFile1.txt 파일에 대한 `ReadOnlyFile` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-179">Add the following code to the Main procedure to create an instance of the `ReadOnlyFile` class for the TextFile1.txt file.</span></span> <span data-ttu-id="01d31-180">코드는 런타임에 바인딩을 사용하여 동적 멤버를 호출하고 "Customer" 문자열이 포함된 텍스트의 줄을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-180">The code uses late binding to call dynamic members and retrieve lines of text that contain the string "Customer".</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/program.cs#8)]
     [!code-vb[VbDynamicWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/module1.vb#8)]
  
3. <span data-ttu-id="01d31-181">파일을 저장한 다음 Ctrl+F5를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-181">Save the file and press CTRL+F5 to build and run the application.</span></span>  
  
## <a name="calling-a-dynamic-language-library"></a><span data-ttu-id="01d31-182">동적 언어 라이브러리 호출</span><span class="sxs-lookup"><span data-stu-id="01d31-182">Calling a Dynamic Language Library</span></span>  

<span data-ttu-id="01d31-183">이 연습에서 만드는 새 프로젝트는 동적 언어 IronPython에서 작성된 라이브러리에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-183">The next project that you create in this walkthrough accesses a library that is written in the dynamic language IronPython.</span></span>
  
### <a name="to-create-a-custom-dynamic-class"></a><span data-ttu-id="01d31-184">사용자 지정 동적 클래스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="01d31-184">To create a custom dynamic class</span></span>
  
1. <span data-ttu-id="01d31-185">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-185">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2. <span data-ttu-id="01d31-186">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-186">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="01d31-187">**템플릿** 창에서 **콘솔 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-187">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="01d31-188">**이름** 상자에 `DynamicIronPythonSample`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-188">In the **Name** box, type `DynamicIronPythonSample`, and then click **OK**.</span></span> <span data-ttu-id="01d31-189">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-189">The new project is created.</span></span>  
  
3. <span data-ttu-id="01d31-190">Visual Basic을 사용 중인 경우 DynamicIronPythonSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-190">If you are using Visual Basic, right-click the DynamicIronPythonSample project and then click **Properties**.</span></span> <span data-ttu-id="01d31-191">**참조** 탭을 클릭합니다. **추가** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-191">Click the **References** tab. Click the **Add** button.</span></span> <span data-ttu-id="01d31-192">Visual C#을 사용 중인 경우 **솔루션 탐색기**에서 **References** 폴더를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-192">If you are using Visual C#, in **Solution Explorer**, right-click the **References** folder and then click **Add Reference**.</span></span>  
  
4. <span data-ttu-id="01d31-193">**찾아보기** 탭에서 IronPython 라이브러리가 설치된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-193">On the **Browse** tab, browse to the folder where the IronPython libraries are installed.</span></span> <span data-ttu-id="01d31-194">예를 들어 .NET 4.0의 경우 C:\Program Files\IronPython 2.6입니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-194">For example, C:\Program Files\IronPython 2.6 for .NET 4.0.</span></span> <span data-ttu-id="01d31-195">**IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** 및 **Microsoft.Dynamic.dll** 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-195">Select the **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll**, and **Microsoft.Dynamic.dll** libraries.</span></span> <span data-ttu-id="01d31-196">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-196">Click **OK**.</span></span>  
  
5. <span data-ttu-id="01d31-197">Visual Basic을 사용 중인 경우 Module1.vb 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-197">If you are using Visual Basic, edit the Module1.vb file.</span></span> <span data-ttu-id="01d31-198">Visual C#을 사용 중인 경우 Program.cs 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-198">If you are using Visual C#, edit the Program.cs file.</span></span>  
  
6. <span data-ttu-id="01d31-199">파일 맨 위에 다음 코드를 추가하여 IronPython 라이브러리에서 `Microsoft.Scripting.Hosting` 및 `IronPython.Hosting` 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-199">At the top of the file, add the following code to import the `Microsoft.Scripting.Hosting` and `IronPython.Hosting` namespaces from the IronPython libraries.</span></span>  
  
    [!code-csharp[VbDynamicWalkthroughIronPython#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#1)]
    [!code-vb[VbDynamicWalkthroughIronPython#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#1)]
  
7. <span data-ttu-id="01d31-200">Main 메서드에서 다음 코드를 추가하여 IronPython 라이브러리를 호스트하기 위한 새 `Microsoft.Scripting.Hosting.ScriptRuntime` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-200">In the Main method, add the following code to create a new `Microsoft.Scripting.Hosting.ScriptRuntime` object to host the IronPython libraries.</span></span> <span data-ttu-id="01d31-201">`ScriptRuntime` 개체는 IronPython 라이브러리 모듈 random.py를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-201">The `ScriptRuntime` object loads the IronPython library module random.py.</span></span>  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#2)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#2)]
  
8. <span data-ttu-id="01d31-202">random.py 모듈을 로드할 코드 뒤에 다음 코드를 추가하여 정수 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-202">After the code to load the random.py module, add the following code to create an array of integers.</span></span> <span data-ttu-id="01d31-203">배열은 random.py 모듈의 `shuffle` 메서드로 전달되며, 이 모듈은 배열의 값을 임의로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-203">The array is passed to the `shuffle` method of the random.py module, which randomly sorts the values in the array.</span></span>  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#3)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#3)]
  
9. <span data-ttu-id="01d31-204">파일을 저장한 다음 Ctrl+F5를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01d31-204">Save the file and press CTRL+F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d31-205">참조</span><span class="sxs-lookup"><span data-stu-id="01d31-205">See also</span></span>

- <xref:System.Dynamic?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [<span data-ttu-id="01d31-206">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="01d31-206">Using Type dynamic</span></span>](./using-type-dynamic.md)
- [<span data-ttu-id="01d31-207">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="01d31-207">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="01d31-208">dynamic</span><span class="sxs-lookup"><span data-stu-id="01d31-208">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="01d31-209">동적 인터페이스 구현(Microsoft TechNet에서 다운로드 가능한 PDF)</span><span class="sxs-lookup"><span data-stu-id="01d31-209">Implementing Dynamic Interfaces (downloadable PDF from Microsoft TechNet)</span></span>](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/implementing-dynamic-interfaces.pdf)
