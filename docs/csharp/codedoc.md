---
title: XML 주석을 사용하여 코드 문서화
description: XML 문서 주석을 사용하여 코드를 문서화하고 컴파일 시간에 XML 문서 파일을 생성하는 방법을 알아봅니다.
ms.date: 01/21/2020
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 91de11c610ea17999dabff6d0552de9440f532e6
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465301"
---
# <a name="document-your-code-with-xml-comments"></a><span data-ttu-id="930e7-103">XML 주석을 사용하여 코드 문서화</span><span class="sxs-lookup"><span data-stu-id="930e7-103">Document your code with XML comments</span></span>

<span data-ttu-id="930e7-104">XML 문서 주석은 사용자 정의 형식이나 멤버의 정의 위에 추가되는 특수 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="930e7-105">컴파일 시간에 XML 문서 파일을 생성하기 위해 컴파일러에서 처리될 수 있으므로 특별합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="930e7-106">Visual Studio 및 기타 IDE가 IntelliSense를 사용하여 형식이나 멤버에 대한 빠른 정보를 표시할 수 있도록 컴파일러에서 생성된 XML 파일은 .NET 어셈블리와 함께 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-106">The compiler-generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="930e7-107">또한 [DocFX](https://dotnet.github.io/docfx/) 및 [Sandcastle](https://github.com/EWSoftware/SHFB) 같은 도구를 통해 XML 파일을 실행하여 API 참조 웹 사이트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="930e7-108">XML 문서 주석은 모든 다른 주석처럼 컴파일러에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="930e7-109">다음 중 하나를 수행하여 컴파일 시간에 XML 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="930e7-110">명령줄에서 .NET Core를 사용하여 애플리케이션을 개발할 경우 .csproj 프로젝트 파일의 `<PropertyGroup>` 섹션에 `GenerateDocumentationFile` 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-110">If you are developing an application with .NET Core from the command line, you can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="930e7-111">[`DocumentationFile` 요소](/visualstudio/msbuild/common-msbuild-project-properties)를 사용하여 문서 파일의 경로를 직접 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-111">You can also specify the path to the documentation file directly using [`DocumentationFile` element](/visualstudio/msbuild/common-msbuild-project-properties).</span></span> <span data-ttu-id="930e7-112">다음 예제에서는 프로젝트 디렉터리에 어셈블리와 같은 루트 파일 이름을 가진 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-112">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

   <span data-ttu-id="930e7-113">이 식은 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-113">This is equivalent to the following:</span></span>

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- <span data-ttu-id="930e7-114">Visual Studio를 사용하여 애플리케이션을 개발할 경우 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="930e7-115">[속성] 대화 상자에서 **빌드** 탭을 선택하고 **XML 문서 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="930e7-116">컴파일러가 파일을 쓰는 위치를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="930e7-117">명령줄에서 .NET 애플리케이션을 컴파일할 경우 컴파일 시 [-doc 컴파일러 옵션](language-reference/compiler-options/doc-compiler-option.md)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-117">If you are compiling a .NET application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="930e7-118">XML 문서 주석에는 삼중 슬래시(`///`) 및 XML 형식의 주석 본문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="930e7-119">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="930e7-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="930e7-120">연습</span><span class="sxs-lookup"><span data-stu-id="930e7-120">Walkthrough</span></span>

<span data-ttu-id="930e7-121">새로운 개발자가 이해/사용하고 타사 개발자가 사용하기 쉬운 매우 기본적인 수학 라이브러리를 문서화하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third-party developers to use.</span></span>

<span data-ttu-id="930e7-122">다음은 간단한 수학 라이브러리에 대한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="930e7-123">샘플 라이브러리는 `int` 및 `double` 데이터 형식에서 네 가지 주요 산술 연산인 `add`, `subtract`, `multiply` 및 `divide`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-123">The sample library supports four major arithmetic operations (`add`, `subtract`, `multiply`, and `divide`) on `int` and `double` data types.</span></span>

<span data-ttu-id="930e7-124">이제 라이브러리를 사용하지만 소스 코드에 대한 액세스 권한이 없는 타사 개발자를 위해 코드에서 API 참조 문서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-124">Now you want to be able to create an API reference document from your code for third-party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="930e7-125">앞에서 언급한 대로 XML 문서 태그를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="930e7-126">이제 C# 컴파일러가 지원하는 표준 XML 태그를 소개하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## \<summary>

<span data-ttu-id="930e7-127">`<summary>` 태그는 형식 또는 멤버에 대한 간단한 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-127">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="930e7-128">`Math` 클래스 정의 및 첫 번째 `Add` 메서드에 태그를 추가하여 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-128">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="930e7-129">나머지 코드에 자유롭게 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="930e7-129">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="930e7-130">`<summary>` 태그는 중요하며, 태그 내용은 IntelliSense 또는 API 참조 문서에서 형식 또는 멤버 정보의 기본 소스이므로 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-130">The `<summary>` tag is important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## \<remarks>

<span data-ttu-id="930e7-131">`<remarks>` 태그는 `<summary>` 태그가 제공하는 형식 또는 멤버에 대한 정보를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-131">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="930e7-132">이 예제에서는 클래스에 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-132">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## \<returns>

<span data-ttu-id="930e7-133">`<returns>` 태그는 메서드 선언의 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-133">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="930e7-134">이전과 같이 다음 예제에서는 첫 번째 `Add` 메서드에 대한 `<returns>` 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-134">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="930e7-135">다른 메서드에 대해 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-135">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## \<value>

<span data-ttu-id="930e7-136">`<value>` 태그는 속성에 사용한다는 점을 제외하고 `<returns>` 태그와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-136">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="930e7-137">`Math` 라이브러리에 `PI`라는 정적 속성이 있다고 가정할 경우 이 태그를 사용하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-137">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## \<example>

<span data-ttu-id="930e7-138">`<example>` 태그를 사용하여 XML 문서에 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-138">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="930e7-139">이 과정에는 자식 `<code>` 태그 사용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-139">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="930e7-140">`code` 태그는 더 긴 예제에 대한 줄 바꿈 및 들여쓰기를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-140">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## \<para>

<span data-ttu-id="930e7-141">`<para>` 태그를 사용하여 부모 태그 내에서 내용의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-141">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="930e7-142">`<para>`는 대개 `<remarks>` 또는 `<returns>`와 같은 태그 내부에서 텍스트를 단락으로 나누는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-142">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="930e7-143">클래스 정의에 대한 `<remarks>` 태그의 내용에 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-143">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## \<c>

<span data-ttu-id="930e7-144">서식 지정 항목에서 텍스트 부분을 코드로 표시하는 데 `<c>` 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-144">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="930e7-145">`<code>` 태그와 비슷하지만 인라인입니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-145">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="930e7-146">태그 내용의 일부로 빠른 코드 예제를 표시하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-146">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="930e7-147">`Math` 클래스에 대한 문서를 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-147">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## \<exception>

<span data-ttu-id="930e7-148">`<exception>` 태그를 사용하여 메서드가 특정 예외를 throw할 수 있음을 개발자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-148">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="930e7-149">`Math` 라이브러리를 살펴보면 특정 조건에 해당할 경우 두 `Add` 메서드가 모두 예외를 throw함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-149">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="930e7-150">`b` 매개 변수가 0인 경우 정수 `Divide` 메서드도 throw하는지는 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-150">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="930e7-151">이제 이 메서드에 예외 문서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-151">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="930e7-152">`cref` 특성은 현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-152">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="930e7-153">이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-153">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="930e7-154">해당 값을 확인할 수 없는 경우 컴파일러에서 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-154">The compiler will issue a warning if its value cannot be resolved.</span></span>

## \<see>

<span data-ttu-id="930e7-155">`<see>` 태그를 사용하여 다른 코드 요소에 대한 문서 페이지의 클릭 가능한 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-155">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="930e7-156">다음 예제에서는 두 `Add` 메서드 간의 클릭 가능한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-156">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="930e7-157">`cref`는 현재 컴파일 환경에서 사용할 수 있는 형식 또는 멤버에 대한 참조를 나타내는 **required** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-157">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="930e7-158">이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-158">This can be any type defined in the project or a referenced assembly.</span></span>

## \<seealso>

<span data-ttu-id="930e7-159">`<seealso>` 태그는 `<see>` 태그와 같은 방법으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-159">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="930e7-160">유일한 차이점은 내용이 일반적으로 "참고 항목" 섹션에 배치된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-160">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="930e7-161">이제 정수 `Add` 메서드에 대해 `seealso` 태그를 추가하여 클래스에서 정수 매개 변수를 허용하는 다른 메서드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-161">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="930e7-162">`cref`는 현재 컴파일 환경에서 사용할 수 있는 형식 또는 멤버에 대한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-162">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="930e7-163">이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-163">This can be any type defined in the project or a referenced assembly.</span></span>

## \<param>

<span data-ttu-id="930e7-164">`<param>` 태그를 사용하여 메서드의 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-164">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="930e7-165">다음은 double `Add` 메서드에 대한 예제입니다. 태그가 설명하는 매개 변수는 **required** `name` 특성에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-165">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## \<typeparam>

<span data-ttu-id="930e7-166">`<typeparam>` 태그는 `<param>` 태그처럼 사용하지만 제네릭 매개 변수를 설명하는 제네릭 형식 또는 메서드 선언에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-166">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="930e7-167">`Math` 클래스에 빠른 제네릭 메서드를 추가하여 한 수량이 다른 수량보다 큰지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-167">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## \<paramref>

<span data-ttu-id="930e7-168">`<summary>` 태그와 같은 태그에서 메서드가 수행하는 작업을 설명하는 동안 매개 변수에 대한 참조를 만들려는 경우</span><span class="sxs-lookup"><span data-stu-id="930e7-168">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="930e7-169">`<paramref>` 태그를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-169">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="930e7-170">double 기반 `Add` 메서드의 요약을 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-170">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="930e7-171">`<param>` 태그처럼 매개 변수 이름은 **required** `name` 특성에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-171">Like the `<param>` tag, the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## \<typeparamref>

<span data-ttu-id="930e7-172">`<typeparamref>` 태그는 `<paramref>` 태그처럼 사용하지만 제네릭 매개 변수를 설명하는 제네릭 형식 또는 메서드 선언에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-172">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="930e7-173">이전에 만든 것과 같은 제네릭 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-173">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## \<list>

<span data-ttu-id="930e7-174">`<list>` 태그를 사용하여 문서 정보의 서식을 순서가 지정된 목록, 순서가 지정되지 않은 목록 또는 표로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-174">You use the `<list>` tag to format documentation information as an ordered list, unordered list, or table.</span></span> <span data-ttu-id="930e7-175">`Math` 라이브러리에서 지원하는 모든 수학 연산의 순서가 지정되지 않은 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-175">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="930e7-176">`type` 특성을 각각 `number` 또는 `table`로 변경하여 순서가 지정된 목록 또는 표를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-176">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

## \<inheritdoc>

<span data-ttu-id="930e7-177">`<inheritdoc>` 태그를 사용하여 기본 클래스, 인터페이스 및 유사한 메서드에서 XML 주석을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-177">You can use the `<inheritdoc>` tag to inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="930e7-178">이렇게 하면 중복 XML 주석을 복사하여 붙여 넣을 필요가 없으며 XML 주석이 자동으로 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-178">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>

[!code-csharp-interactive[InheritDoc Tag](~/samples/snippets/csharp/concepts/codedoc/inheritdoc-tag.cs)]

### <a name="put-it-all-together"></a><span data-ttu-id="930e7-179">모든 요소 결합</span><span class="sxs-lookup"><span data-stu-id="930e7-179">Put it all together</span></span>

<span data-ttu-id="930e7-180">이 자습서에 따라 필요한 경우 코드에 태그를 적용했습니다. 이제 코드는 다음과 같이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-180">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="930e7-181">코드에서 클릭 가능한 상호 참조가 포함된 자세한 문서 웹 사이트를 생성할 수 있지만</span><span class="sxs-lookup"><span data-stu-id="930e7-181">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="930e7-182">코드를 읽기 어렵게 되는 다른 문제에 직면할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-182">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="930e7-183">자세히 살펴볼 정보가 너무 많으므로 이 코드에 참여하려는 개발자에게는 큰 문제일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-183">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="930e7-184">다행히도 이 문제를 처리할 수 있는 XML 태그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-184">Thankfully there's an XML tag that can help you deal with this:</span></span>

## \<include>

<span data-ttu-id="930e7-185">소스 코드 파일에 직접 문서 주석을 배치하는 것과 달리 `<include>` 태그를 사용하면 소스 코드에서 형식과 멤버를 설명하는 주석을 개별 XML 파일에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-185">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="930e7-186">이제 모든 XML 태그를 `docs.xml`이라는 개별 XML 파일로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-186">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="930e7-187">원하는 대로 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-187">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="930e7-188">위 XML에서 각 멤버의 문서 주석은 멤버가 수행하는 작업과 같은 이름이 지정된 태그 내부에 직접 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-188">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="930e7-189">자신만의 전략을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-189">You can choose your own strategy.</span></span>
<span data-ttu-id="930e7-190">이제 XML 주석이 개별 파일에 있으므로 `<include>` 태그를 사용하여 코드를 더 읽기 좋게 만드는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-190">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="930e7-191">해냈습니다. 코드를 다시 읽을 수 있고 문서 정보가 손실되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-191">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="930e7-192">`file` 특성은 문서가 포함된 XML 파일의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-192">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="930e7-193">`path` 특성은 지정된 `file`에 있는 `tag name`에 대한 [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-193">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="930e7-194">`name` 특성은 주석 앞에 오는 태그의 이름 지정자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-194">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="930e7-195">`name` 대신 사용할 수 있는 `id` 특성은 주석 앞에 오는 태그의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-195">The `id` attribute, which can be used in place of `name`, represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="930e7-196">사용자 정의 태그</span><span class="sxs-lookup"><span data-stu-id="930e7-196">User-defined tags</span></span>

<span data-ttu-id="930e7-197">위에서 설명한 모든 태그는 C# 컴파일러에서 인식되는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-197">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="930e7-198">그러나 사용자가 자유롭게 태그를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-198">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="930e7-199">Sandcastle 등의 도구는 [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) 같은 추가 태그를 지원하고 [네임스페이스 문서화](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-199">Tools like Sandcastle bring support for extra tags like [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) and [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="930e7-200">사용자 지정 또는 사내 문서 생성 도구는 표준 태그와 함께 사용할 수도 있고 HTML에서 PDF까지 다양한 출력 형식을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-200">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="930e7-201">권장 사항</span><span class="sxs-lookup"><span data-stu-id="930e7-201">Recommendations</span></span>

<span data-ttu-id="930e7-202">여러 가지 이유로 코드를 문서화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-202">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="930e7-203">이어서 일부 모범 사례, 일반적인 사용 사례 시나리오 및 C# 코드에서 XML 문서 태그를 사용할 때 알아야 하는 내용을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-203">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="930e7-204">일관성을 보장하기 위해 모든 공개 형식과 해당 멤버를 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-204">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="930e7-205">문서화해야 한다면 모두 문서화하세요.</span><span class="sxs-lookup"><span data-stu-id="930e7-205">If you must do it, do it all.</span></span>
- <span data-ttu-id="930e7-206">Private 멤버는 XML 주석을 사용하여 문서화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-206">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="930e7-207">그러나 이렇게 하면 라이브러리의 내부(잠재적으로 기밀) 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-207">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="930e7-208">IntelliSense에는 `<summary>` 태그의 내용이 필요하므로 최소한 형식과 해당 멤버에 이 태그가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-208">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="930e7-209">문서 텍스트는 마침표로 끝나는 전체 문장을 사용하여 기록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-209">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="930e7-210">Partial 클래스는 완전히 지원되고 문서 정보는 해당 형식의 단일 항목에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-210">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="930e7-211">컴파일러에서 `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` 및 `<typeparam>` 태그의 구문을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-211">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>`, and `<typeparam>` tags.</span></span>
- <span data-ttu-id="930e7-212">컴파일러는 파일 경로와 코드의 다른 부분에 대한 참조가 포함된 매개 변수의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="930e7-212">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="930e7-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="930e7-213">See also</span></span>

- [<span data-ttu-id="930e7-214">XML 문서 주석(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="930e7-214">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="930e7-215">문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="930e7-215">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
