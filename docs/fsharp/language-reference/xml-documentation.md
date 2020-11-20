---
title: XML 문서
description: '주석에서 문서를 생성 하기 위한 F #의 지원에 대해 알아봅니다.'
ms.date: 09/15/2020
ms.openlocfilehash: 8720d66204333eb21dc998655467f9a5745a33f3
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982481"
---
# <a name="document-your-code-with-xml-comments"></a><span data-ttu-id="8c2fd-103">XML 주석을 사용하여 코드 문서화</span><span class="sxs-lookup"><span data-stu-id="8c2fd-103">Document your code with XML comments</span></span>

<span data-ttu-id="8c2fd-104">F #에서 삼중 슬래시 (///) 코드 주석으로 문서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-104">You can produce documentation from triple-slash (///) code comments in F#.</span></span> <span data-ttu-id="8c2fd-105">XML 주석은 코드 파일 (fs) 또는 서명 (. fsi.exe) 파일의 선언 앞에 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-105">XML comments can precede declarations in code files (.fs) or signature (.fsi) files.</span></span>

<span data-ttu-id="8c2fd-106">XML 문서 주석은 사용자 정의 형식이나 멤버의 정의 위에 추가되는 특수 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-106">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="8c2fd-107">컴파일 시간에 XML 문서 파일을 생성하기 위해 컴파일러에서 처리될 수 있으므로 특별합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-107">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="8c2fd-108">Ide에서 도구 설명을 사용 하 여 형식 또는 멤버에 대 한 빠른 정보를 표시할 수 있도록 컴파일러에서 생성 된 XML 파일은 .NET 어셈블리와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-108">The compiler-generated XML file can be distributed alongside your .NET assembly so that IDEs can use tooltips to show quick information about types or members.</span></span> <span data-ttu-id="8c2fd-109">또한 XML 파일은 [fsdocs](http://fsprojects.github.io/FSharp.Formatting/) 와 같은 도구를 통해 실행 하 여 API 참조 웹 사이트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-109">Additionally, the XML file can be run through tools like [fsdocs](http://fsprojects.github.io/FSharp.Formatting/) to generate API reference websites.</span></span>

<span data-ttu-id="8c2fd-110">아래에 설명 된 옵션을 사용 하 여 컴파일 시간에 주석의 유효성 및 완전성을 확인할 수 없는 경우에는 컴파일러에서 다른 모든 주석과 마찬가지로 XML 문서 주석을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-110">XML documentation comments, like all other comments, are ignored by the compiler, unless the options described below are enabled to check the validity and completeness of comments at compile-time.</span></span>

<span data-ttu-id="8c2fd-111">다음 중 하나를 수행하여 컴파일 시간에 XML 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-111">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="8c2fd-112">`GenerateDocumentationFile`프로젝트 파일의 섹션에 요소를 추가 하면 `<PropertyGroup>` `.fsproj` 어셈블리와 동일한 루트 파일 이름을 가진 XML 파일이 프로젝트 디렉터리에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-112">You can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your `.fsproj` project file, which generates an XML file in the project directory with the same root filename as the assembly.</span></span> <span data-ttu-id="8c2fd-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-113">For example:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

- <span data-ttu-id="8c2fd-114">Visual Studio를 사용하여 애플리케이션을 개발할 경우 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="8c2fd-115">[속성] 대화 상자에서 **빌드** 탭을 선택하고 **XML 문서 파일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="8c2fd-116">컴파일러가 파일을 쓰는 위치를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-116">You can also change the location to which the compiler writes the file.</span></span>

<span data-ttu-id="8c2fd-117">Xml 태그를 사용 하거나 사용 하지 않고 XML 문서 주석을 작성 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-117">There are two ways to write XML documentation comments: with and without XML tags.</span></span> <span data-ttu-id="8c2fd-118">두 가지 모두 삼중 슬래시 주석을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-118">Both use triple-slash comments.</span></span>

## <a name="comments-without-xml-tags"></a><span data-ttu-id="8c2fd-119">XML 태그가 없는 주석</span><span class="sxs-lookup"><span data-stu-id="8c2fd-119">Comments without XML tags</span></span>

<span data-ttu-id="8c2fd-120">`///`주석이로 시작 하지 않는 경우 `<` 전체 주석 텍스트는 바로 다음에 오는 코드 구문에 대 한 요약 설명서로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-120">If a `///` comment does not start with a `<` then the entire comment text is taken as the summary documentation for the code construct that immediately follows.</span></span> <span data-ttu-id="8c2fd-121">각 구문에 대 한 간략 한 요약만 작성 하려는 경우이 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-121">Use this method when you want to write only a brief summary for each construct.</span></span>

<span data-ttu-id="8c2fd-122">주석은 설명서를 준비 하는 동안 XML로 인코딩되고와 같은 문자를 `<` `>` 이스케이프 처리 `&` 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-122">The comment is encoded to XML during documentation preparation, so characters such as `<`, `>` and `&` need not be escaped.</span></span> <span data-ttu-id="8c2fd-123">요약 태그를 명시적으로 지정 하지 않은 경우에는 **매개 변수** 또는 태그를 **반환** 하는 등의 다른 태그를 지정 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-123">If you don't specify a summary tag explicitly, you should not specify other tags, such as **param** or **returns** tags.</span></span>

<span data-ttu-id="8c2fd-124">다음 예제에서는 XML 태그가 없는 대체 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-124">The following example shows the alternative method, without XML tags.</span></span> <span data-ttu-id="8c2fd-125">이 예제에서는 주석의 전체 텍스트를 요약으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-125">In this example, the entire text in the comment is considered a summary.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="comments-with-xml-tags"></a><span data-ttu-id="8c2fd-126">XML 태그가 있는 주석</span><span class="sxs-lookup"><span data-stu-id="8c2fd-126">Comments with XML tags</span></span>

<span data-ttu-id="8c2fd-127">주석 본문이 (일반적으로)로 시작 하는 경우 `<` `<summary>` xml 태그를 사용 하 여 xml 형식의 주석 본문으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-127">If a comment body begins with `<` (normally `<summary>`) then it is treated as an XML formatted comment body using XML tags.</span></span> <span data-ttu-id="8c2fd-128">이 두 번째를 사용 하면 간단한 요약, 추가 설명, 각 매개 변수 및 형식 매개 변수와 throw 된 예외에 대 한 설명서 및 반환 값에 대 한 설명 등을 위한 별도의 메모를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-128">This second enables you to specify separate notes for a short summary, additional remarks, documentation for each parameter and type parameter and exceptions thrown, and a description of the return value.</span></span>

<span data-ttu-id="8c2fd-129">다음은 서명 파일의 일반적인 XML 문서 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-129">The following is a typical XML documentation comment in a signature file:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="recommended-tags"></a><span data-ttu-id="8c2fd-130">권장 태그</span><span class="sxs-lookup"><span data-stu-id="8c2fd-130">Recommended Tags</span></span>

<span data-ttu-id="8c2fd-131">XML 태그를 사용 하는 경우 다음 표에서는 F # XML 코드 주석에서 인식 되는 외부 태그를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-131">If you are using XML tags, the following table describes the outer tags recognized in F# XML code comments.</span></span>

| <span data-ttu-id="8c2fd-132">태그 구문</span><span class="sxs-lookup"><span data-stu-id="8c2fd-132">Tag syntax</span></span>                                  | <span data-ttu-id="8c2fd-133">설명</span><span class="sxs-lookup"><span data-stu-id="8c2fd-133">Description</span></span> |
|---------------------------------------------|-----------|
| <span data-ttu-id="8c2fd-134">`<summary>`**_본문_**`</summary>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-134">`<summary>`**_text_**`</summary>`</span></span>           | <span data-ttu-id="8c2fd-135">*텍스트* 를 프로그램 요소에 대 한 간단한 설명으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-135">Specifies that *text* is a brief description of the program element.</span></span> <span data-ttu-id="8c2fd-136">설명은 일반적으로 하나 또는 두 개의 문장입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-136">The description is usually one or two sentences.</span></span>|
| <span data-ttu-id="8c2fd-137">`<remarks>`**_본문_**`</remarks>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-137">`<remarks>`**_text_**`</remarks>`</span></span>           | <span data-ttu-id="8c2fd-138">*텍스트* 에 프로그램 요소에 대 한 보충 정보가 포함 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-138">Specifies that *text* contains supplementary information about the program element.</span></span>|
| <span data-ttu-id="8c2fd-139">`<param name="`**_이름_** `">` **_설명_**`</param>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-139">`<param name="`**_name_**`">`**_description_**`</param>`</span></span> | <span data-ttu-id="8c2fd-140">함수 또는 메서드 매개 변수의 이름 및 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-140">Specifies the name and description for a function or method parameter.</span></span>|
| <span data-ttu-id="8c2fd-141">`<typeparam name="`**_이름_** `">` **_설명_**`</typeparam>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-141">`<typeparam name="`**_name_**`">`**_description_**`</typeparam>`</span></span> | <span data-ttu-id="8c2fd-142">형식 매개 변수에 대 한 이름 및 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-142">Specifies the name and description for a type parameter.</span></span>|
| <span data-ttu-id="8c2fd-143">`<returns>`**_본문_**`</returns>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-143">`<returns>`**_text_**`</returns>`</span></span>           | <span data-ttu-id="8c2fd-144">함수 또는 메서드의 반환 값을 설명 하는 *텍스트* 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-144">Specifies that *text* describes the return value of a function or method.</span></span>|
| <span data-ttu-id="8c2fd-145">`<exception cref="`**_유형_** `">` **_설명_**`</exception>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-145">`<exception cref="`**_type_**`">`**_description_**`</exception>`</span></span> |<span data-ttu-id="8c2fd-146">생성할 수 있는 예외의 형식 및 예외가 throw 되는 상황을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-146">Specifies the type of exception that can be generated and the circumstances under which it is thrown.</span></span>|
| <span data-ttu-id="8c2fd-147">`<seealso cref="`**_참조일_**`"/>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-147">`<seealso cref="`**_reference_**`"/>`</span></span>      | <span data-ttu-id="8c2fd-148">다른 형식에 대 한 설명서 링크도 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-148">Specifies a See Also link to the documentation for another type.</span></span> <span data-ttu-id="8c2fd-149">*참조* 는 XML 문서 파일에 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-149">The *reference* is the name as it appears in the XML documentation file.</span></span> <span data-ttu-id="8c2fd-150">링크도 일반적으로 설명서 페이지의 아래쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-150">See Also links usually appear at the bottom of a documentation page.</span></span>|

<span data-ttu-id="8c2fd-151">다음 표에서는 설명 섹션 내에서 사용할 태그에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-151">The following table describes the tags for use inside description sections:</span></span>

| <span data-ttu-id="8c2fd-152">태그 구문</span><span class="sxs-lookup"><span data-stu-id="8c2fd-152">Tag syntax</span></span>                                | <span data-ttu-id="8c2fd-153">설명</span><span class="sxs-lookup"><span data-stu-id="8c2fd-153">Description</span></span> |
|-------------------------------------------|-------------|
| <span data-ttu-id="8c2fd-154">`<para>`**_본문_**`</para>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-154">`<para>`**_text_**`</para>`</span></span>               | <span data-ttu-id="8c2fd-155">텍스트 단락을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-155">Specifies a paragraph of text.</span></span> <span data-ttu-id="8c2fd-156">이는 **설명** 태그 내에서 텍스트를 구분 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-156">This is used to separate text inside the **remarks** tag.</span></span>|
| <span data-ttu-id="8c2fd-157">`<code>`**_본문_**`</code>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-157">`<code>`**_text_**`</code>`</span></span>               | <span data-ttu-id="8c2fd-158">*텍스트가* 여러 줄의 코드 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-158">Specifies that *text* is multiple lines of code.</span></span> <span data-ttu-id="8c2fd-159">문서 생성기는이 태그를 사용 하 여 코드에 적절 한 글꼴로 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-159">This tag can be used by documentation generators to display text in a font that is appropriate for code.</span></span>|
| <span data-ttu-id="8c2fd-160">`<paramref name="`**_이름의_**`"/>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-160">`<paramref name="`**_name_**`"/>`</span></span>         | <span data-ttu-id="8c2fd-161">동일한 문서 주석에 있는 매개 변수에 대 한 참조를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-161">Specifies a reference to a parameter in the same documentation comment.</span></span>|
| <span data-ttu-id="8c2fd-162">`<typeparamref name="`**_이름의_**`"/>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-162">`<typeparamref name="`**_name_**`"/>`</span></span>     | <span data-ttu-id="8c2fd-163">동일한 문서 주석의 형식 매개 변수에 대 한 참조를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-163">Specifies a reference to a type parameter in the same documentation comment.</span></span>|
| <span data-ttu-id="8c2fd-164">`<c>`**_본문_**`</c>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-164">`<c>`**_text_**`</c>`</span></span>                     | <span data-ttu-id="8c2fd-165">*텍스트* 를 인라인 코드로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-165">Specifies that *text* is inline code.</span></span> <span data-ttu-id="8c2fd-166">문서 생성기는이 태그를 사용 하 여 코드에 적절 한 글꼴로 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-166">This tag can be used by documentation generators to display text in a font that is appropriate for code.</span></span>|
| <span data-ttu-id="8c2fd-167">`<see cref="`**_참조_** `">` **_텍스트_**`</see>`</span><span class="sxs-lookup"><span data-stu-id="8c2fd-167">`<see cref="`**_reference_**`">`**_text_**`</see>`</span></span> | <span data-ttu-id="8c2fd-168">다른 프로그램 요소에 대 한 인라인 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-168">Specifies an inline link to another program element.</span></span> <span data-ttu-id="8c2fd-169">*참조* 는 XML 문서 파일에 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-169">The *reference* is the name as it appears in the XML documentation file.</span></span> <span data-ttu-id="8c2fd-170">*텍스트* 는 링크에 표시 되는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-170">The *text* is the text shown in the link.</span></span>|

### <a name="user-defined-tags"></a><span data-ttu-id="8c2fd-171">사용자 정의 태그</span><span class="sxs-lookup"><span data-stu-id="8c2fd-171">User-defined tags</span></span>

<span data-ttu-id="8c2fd-172">이전 태그는 F # 컴파일러 및 일반적인 F # 편집기 도구에서 인식 되는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-172">The previous tags represent those that are recognized by the F# compiler and typical F# editor tooling.</span></span> <span data-ttu-id="8c2fd-173">그러나 사용자가 자유롭게 태그를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-173">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="8c2fd-174">Fsdocs와 같은 도구는와 같은 추가 태그를 지원 [\<namespacedoc>](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1031-xmldoc-extensions.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-174">Tools like fsdocs bring support for extra tags like [\<namespacedoc>](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1031-xmldoc-extensions.md).</span></span>
<span data-ttu-id="8c2fd-175">사용자 지정 또는 사내 문서 생성 도구는 표준 태그와 함께 사용할 수도 있고 HTML에서 PDF까지 다양한 출력 형식을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-175">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="compile-time-checking"></a><span data-ttu-id="8c2fd-176">컴파일 시간 검사</span><span class="sxs-lookup"><span data-stu-id="8c2fd-176">Compile-time checking</span></span>

<span data-ttu-id="8c2fd-177">`--warnon:3390`을 사용 하는 경우 컴파일러는 XML의 구문과 및 태그에서 참조 되는 매개 변수를 확인 합니다 `<param>` `<paramref>` .</span><span class="sxs-lookup"><span data-stu-id="8c2fd-177">When `--warnon:3390` is enabled, the compiler verifies the syntax of the XML and the parameters referred to in `<param>` and `<paramref>` tags.</span></span>

## <a name="documenting-f-constructs"></a><span data-ttu-id="8c2fd-178">F # 구문 문서화</span><span class="sxs-lookup"><span data-stu-id="8c2fd-178">Documenting F# Constructs</span></span>

<span data-ttu-id="8c2fd-179">모듈, 멤버, 공용 구조체 케이스 및 레코드 필드와 같은 F # 생성자는 선언 직전 `///` 에 주석으로 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-179">F# constructs such as modules, members, union cases and record fields are documented by a `///` comment immediately prior to their declaration.</span></span>
<span data-ttu-id="8c2fd-180">필요한 경우 인수 목록 앞에 주석을 제공 하 여 클래스의 암시적 생성자를 문서화 `///` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-180">If needed, implicit constructors of classes are documented by giving a `///` comment prior to the argument list.</span></span> <span data-ttu-id="8c2fd-181">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-181">For example:</span></span>

```fsharp
/// This is the type
type SomeType
      /// This is the implicit constructor
      (a: int, b: int) =

    /// This is the member
    member _.Sum() = a + b
```

## <a name="limitations"></a><span data-ttu-id="8c2fd-182">제한 사항</span><span class="sxs-lookup"><span data-stu-id="8c2fd-182">Limitations</span></span>

<span data-ttu-id="8c2fd-183">C #에서 XML 문서의 일부 기능 및 기타 .NET 언어는 c #에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-183">Some features of XML documentation in C# and other .NET languages are not supported in C#.</span></span>

- <span data-ttu-id="8c2fd-184">F #에서 상호 참조는 해당 기호의 전체 XML 시그니처를 사용 해야 합니다 (예:) `cref="T:System.Console"` .</span><span class="sxs-lookup"><span data-stu-id="8c2fd-184">In F#, cross-references must use the full XML signature of the corresponding symbol, for example `cref="T:System.Console"`.</span></span>
  <span data-ttu-id="8c2fd-185">와 같은 간단한 c # 스타일 상호 참조 `cref="Console"` 는 전체 XML 서명에 대해 구체화 되지 않으며 이러한 요소는 F # 컴파일러에서 확인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-185">Simple C#-style cross-references such as `cref="Console"` are not elaborated to full XML signatures and these elements are not checked by the F# compiler.</span></span> <span data-ttu-id="8c2fd-186">일부 설명서 도구는 후속 처리를 통해 이러한 상호 참조를 사용할 수 있지만 전체 서명을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-186">Some documentation tooling may allow the use of these cross-references by subsequent processing, but the full signatures should be used.</span></span>
  
- <span data-ttu-id="8c2fd-187">태그는 `<include>` `<inheritdoc>` F # 컴파일러에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-187">The tags `<include>`, `<inheritdoc>` are not supported by the F# compiler.</span></span> <span data-ttu-id="8c2fd-188">사용 되는 경우에는 오류가 발생 하지 않지만 생성 된 설명서에 영향을 주지 않으면 서 생성 된 설명서 파일에 단순히 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-188">No error is given if they are used, but they are simply copied to the generated documentation file without otherwise affecting the documentation generated.</span></span>

- <span data-ttu-id="8c2fd-189">를 사용 하는 경우에도 F # 컴파일러에서 상호 참조를 검사 하지 않습니다 `-warnon:3390` .</span><span class="sxs-lookup"><span data-stu-id="8c2fd-189">Cross-references are not checked by the F# compiler, even when `-warnon:3390` is used.</span></span>

- <span data-ttu-id="8c2fd-190">태그에 사용 되는 이름은 `<typeparam>` `<typeparamref>` 이 사용 되는 경우에도 F # 컴파일러에서 확인 되지 않습니다 `--warnon:3390` .</span><span class="sxs-lookup"><span data-stu-id="8c2fd-190">The names used in the tags `<typeparam>` and `<typeparamref>` are not checked by the F# compiler, even when `--warnon:3390` is used.</span></span>

- <span data-ttu-id="8c2fd-191">이 사용 되는 경우에도 설명서가 누락 되 면 경고가 표시 되지 않습니다 `--warnon:3390` .</span><span class="sxs-lookup"><span data-stu-id="8c2fd-191">No warnings are given if documentation is missing, even when `--warnon:3390` is used.</span></span>

## <a name="recommendations"></a><span data-ttu-id="8c2fd-192">권장 사항</span><span class="sxs-lookup"><span data-stu-id="8c2fd-192">Recommendations</span></span>

<span data-ttu-id="8c2fd-193">여러 가지 이유로 코드를 문서화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-193">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="8c2fd-194">다음은 몇 가지 모범 사례, 일반적인 사용 사례 시나리오 및 F # 코드에서 XML 문서 태그를 사용할 때 알아야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-194">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your F# code.</span></span>

- <span data-ttu-id="8c2fd-195">`--warnon:3390`Xml 문서가 올바른 xml 인지 확인 하기 위해 코드에서 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-195">Enable the option `--warnon:3390` in your code to help ensure your XML documentation is valid XML.</span></span>

- <span data-ttu-id="8c2fd-196">구현에서 긴 XML 문서 주석을 분리 하는 서명 파일을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-196">Consider adding signature files to separate long XML documentation comments from your implementation.</span></span>

- <span data-ttu-id="8c2fd-197">일관성을 보장하기 위해 모든 공개 형식과 해당 멤버를 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-197">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="8c2fd-198">문서화해야 한다면 모두 문서화하세요.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-198">If you must do it, do it all.</span></span>

- <span data-ttu-id="8c2fd-199">최소한의 경우 모듈, 형식 및 해당 멤버에는 일반 `///` 주석이 나 태그가 있어야 합니다 `<summary>` .</span><span class="sxs-lookup"><span data-stu-id="8c2fd-199">At a bare minimum, modules, types and their members should have a plain `///` comment or `<summary>` tag.</span></span> <span data-ttu-id="8c2fd-200">F # 편집 도구의 자동 완성 도구 설명 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-200">This will show in an autocompletion tooltip window in F# editing tools.</span></span>

- <span data-ttu-id="8c2fd-201">문서 텍스트는 마침표로 끝나는 전체 문장을 사용하여 기록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2fd-201">Documentation text should be written using complete sentences ending with full stops.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c2fd-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c2fd-202">See also</span></span>

- <span data-ttu-id="8c2fd-203">C [# XML 문서 주석 &#40;c&#35; 프로그래밍 가이드&#41;](../../csharp/programming-guide/xmldoc/index.md).</span><span class="sxs-lookup"><span data-stu-id="8c2fd-203">[C# XML Documentation Comments &#40;C&#35; Programming Guide&#41;](../../csharp/programming-guide/xmldoc/index.md).</span></span>
- [<span data-ttu-id="8c2fd-204">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="8c2fd-204">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8c2fd-205">컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="8c2fd-205">Compiler Options</span></span>](compiler-options.md)
