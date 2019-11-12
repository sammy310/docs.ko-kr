---
title:
- 문서 제목
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: 20f581f1684d99766b19390daa9ff7a076d44ac3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423759"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="ae358-102">메타데이터 및 Markdown 템플릿</span><span class="sxs-lookup"><span data-stu-id="ae358-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="ae358-103">이 dotnet/docs 템플릿에는 Markdown 구문의 예제와 메타데이터 설정 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="ae358-104">이 템플릿을 최대한 활용하려면 [원시 Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) 및 [렌더링된 보기](https://github.com/dotnet/docs/blob/master/styleguide/template.md)를 모두 확인해야 합니다. 예를 들어 원시 Markdown에는 메타데이터 블록이 표시되는 반면 렌더링된 보기에는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (for instance, the raw Markdown shows the metadata block, while the rendered view does not).</span></span>

<span data-ttu-id="ae358-105">Markdown 파일을 만들 때는 이 템플릿을 새 파일로 복사하고, 아래에 지정되어 있는 것처럼 메타데이터를 입력하고, 위의 H1 제목을 문서 제목으로 설정한 다음 내용을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="ae358-106">Metadata</span><span class="sxs-lookup"><span data-stu-id="ae358-106">Metadata</span></span>

<span data-ttu-id="ae358-107">위의 [원시 Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)에는 전체 메타데이터 블록이 필수 필드와 선택적 필드로 구분되어 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="ae358-108">몇 가지 주요 참고 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-108">Some key notes:</span></span>

- <span data-ttu-id="ae358-109">메타데이터 요소의 값과 콜론(:) 사이에는 공백이 **있어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="ae358-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="ae358-110">선택적 메타데이터 요소에 값이 없으면 #으로 요소를 주석으로 처리하거나 제거합니다(공백으로 두거나 “na”를 사용하지 않음).</span><span class="sxs-lookup"><span data-stu-id="ae358-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="ae358-111">주석 처리된 요소에 값을 추가하는 경우 #을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="ae358-112">제목 등의 값에 콜론이 포함되어 있으면 메타데이터 파서가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="ae358-113">이 경우 `title: "Writing .NET Core console apps: An advanced step-by-step guide"`와 같이 큰따옴표를 사용하여 제목을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="ae358-114">**title**: 검색 엔진 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="ae358-115">제목(title)은 H1 제목(heading)의 제목(title)과 같을 필요는 없으며 60자 이내로 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="ae358-116">**설명**: 문서의 내용을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="ae358-117">일반적으로 검색 결과 페이지에 표시되지만 검색 순위에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="ae358-118">길이는 공백을 포함하여 115~145자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="ae358-119">**author** 및 **ms.author**: author 필드는 작성자의 별칭이 아닌 **GitHub 사용자 이름**을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="ae358-120">반면 **ms.author** 필드에서는 Microsoft 별칭을 포함해야 하며, 문서 유지 관리를 담당하는 개인을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="ae358-121">**ms.topic**: 토픽 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="ae358-122">가장 일반적인 값은 `conceptual`이고 전역 수준에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="ae358-123">기타 일반적으로 사용되는 값은 `tutorial`, `overview` 및 `reference`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="ae358-124">**dev_langs**에서는 토픽에 대해 표시된 언어 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-124">**dev_langs** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="ae358-125">지원되는 값 목록은 [지원되는 언어](#supported-languages) 섹션에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="ae358-126">토픽에 포함된 프로그래밍 언어가 둘 이상 있는 경우에만 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="ae358-127">일반적으로 당사의 콘텐츠에서는 이 값으로 `csharp`, `vb`, `fsharp` 및 `cpp`만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="ae358-128">**ms.prod**: BI 용도로 사용되는 제품 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="ae358-129">이 ID는 일반적으로 전역 수준에서 설정되므로 대개 각 문서의 메타데이터 블록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="ae358-130">**ms.technology**: 추가 BI 분류.</span><span class="sxs-lookup"><span data-stu-id="ae358-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="ae358-131">지원되는 일부 값은 C# 토픽의 경우 `devlang-csharp`이고, F# 토픽의 경우 `devlang-fsharp`이며, VB 토픽의 경우 `devlang-visual-basic`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="ae358-132">다른 가이드의 경우 값이 다를 수 있으므로 팀 멤버에게 문의하여 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ae358-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="ae358-133">**ms.date**: YYYY/MM/DD 형식의 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="ae358-134">게시된 페이지에 표시되어 마지막으로 문서가 대폭 편집되었거나 확실히 “새로 고침”(즉, 문서가 검토되었고 최신 상태라고 간주됨)된 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="ae358-135">**helpviewer_keywords**: 항목은 오프라인 서적 색인(Visual Studio의 기능)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="ae358-136">**f1_keywords**: 문서를 F1 키(Visual Studio의 기능)에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="ae358-137">기본 Markdown, GFM 및 특수 문자</span><span class="sxs-lookup"><span data-stu-id="ae358-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="ae358-138">모든 기본 및 GFM(GitHub Flavored Markdown)이 지원되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="ae358-139">여기에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae358-139">For more information on these, see:</span></span>

- [<span data-ttu-id="ae358-140">기준 Markdown 구문</span><span class="sxs-lookup"><span data-stu-id="ae358-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="ae358-141">GFM 설명서</span><span class="sxs-lookup"><span data-stu-id="ae358-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="ae358-142">Markdown은 서식 지정을 위해 \*, \`, \# 등의 특수 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="ae358-143">이러한 문자 중 하나를 내용에 포함하려는 경우에는 다음 두 작업 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="ae358-144">특수 문자 앞에 백슬래시를 넣어 특수 문자를 "이스케이프"합니다(예: \*의 경우 `\*`).</span><span class="sxs-lookup"><span data-stu-id="ae358-144">Put a backslash before the special character to "escape" it (for example, `\*` for an \*)</span></span>
- <span data-ttu-id="ae358-145">문자의 [HTML 엔터티 코드](https://www.ascii.cl/htmlcodes.htm)를 사용합니다(예: &#42;의 경우 `&#42;`).</span><span class="sxs-lookup"><span data-stu-id="ae358-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for an &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="ae358-146">파일 이름</span><span class="sxs-lookup"><span data-stu-id="ae358-146">File name</span></span>

<span data-ttu-id="ae358-147">파일 이름은 다음 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-147">File names use the following rules:</span></span>

- <span data-ttu-id="ae358-148">소문자, 숫자 및 하이픈만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="ae358-149">공백 또는 문장 부호 문자는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="ae358-150">하이픈을 사용하여 파일 이름의 단어와 숫자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="ae358-151">개발, 구매, 빌드, 문제 해결 등의 구체적인 작업 동사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="ae358-152">현재 진행형 단어는 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-152">No -ing words.</span></span>
- <span data-ttu-id="ae358-153">한, 및, 그, 내, 또는 등의 군더더기로 간주되는 단어는 가급적 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="ae358-154">Markdown 파일 및 .md 파일 확장명을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="ae358-155">파일 이름은 비교적 짧게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-155">Keep file names reasonably short.</span></span> <span data-ttu-id="ae358-156">문서의 URL에 파일 이름이 포함되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="ae358-157">제목</span><span class="sxs-lookup"><span data-stu-id="ae358-157">Headings</span></span>

<span data-ttu-id="ae358-158">문장 스타일 대/소문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="ae358-159">제목의 첫 번째 단어, 고유 명사 및 콜론 다음의 첫 글자를 대문자로 지정합니다(예: "Tutorial: Predict prices using regression with ML.NET").</span><span class="sxs-lookup"><span data-stu-id="ae358-159">Capitalize the first letter of the first word of a heading, proper nouns, and the first letter following a colon (for example, "Tutorial: Predict prices using regression with ML.NET").</span></span>

<span data-ttu-id="ae358-160">“방법” 뒤에 콜론을 추가하지 않는 형식(예: 배열을 정렬하는 방법, 사용 금지 - “방법: 배열 정렬”)입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-160">Don't add a colon after "How to" (for example, "How to sort an array" and not "How to: Sort an array").</span></span>

<span data-ttu-id="ae358-161">제목은 atx 스타일로 작성해야 합니다. 즉, 줄 시작 부분에서 HTML 제목 수준 H1~H6에 해당하는 1~6개의 해시 문자(#)를 사용하여 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-161">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="ae358-162">위에서는 수준 1/수준 2 헤더의 예가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-162">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="ae358-163">항목에는 수준 1 제목(H1)이 **하나만** 있어야 합니다. 이 제목이 페이지의 제목으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-163">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="ae358-164">제목이 `#` 문자로 끝나는 경우, 제목을 올바르게 렌더링하려면 이 문자를 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-164">If your heading ends in a `#` character, you need to escape it for the title to render correctly.</span></span> <span data-ttu-id="ae358-165">예: `# Async programming in F\#`.</span><span class="sxs-lookup"><span data-stu-id="ae358-165">For example, `# Async programming in F\#`.</span></span>

<span data-ttu-id="ae358-166">수준 2 제목은 페이지 제목 아래의 "문서 내용" 섹션에 표시되는 페이지 TOC를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-166">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="ae358-167">수준 3 제목</span><span class="sxs-lookup"><span data-stu-id="ae358-167">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="ae358-168">수준 4 제목</span><span class="sxs-lookup"><span data-stu-id="ae358-168">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="ae358-169">수준 5 제목</span><span class="sxs-lookup"><span data-stu-id="ae358-169">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="ae358-170">수준 6 제목</span><span class="sxs-lookup"><span data-stu-id="ae358-170">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="ae358-171">텍스트 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="ae358-171">Text styling</span></span>

<span data-ttu-id="ae358-172">*기울임꼴* 파일, 폴더, 경로(긴 항목의 경우 자체 줄로 분할), 새 용어에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-172">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="ae358-173">**굵은 글씨체** UI 요소에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-173">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="ae358-174">`Code` 인라인 코드, 언어 키워드, NuGet 패키지 이름, 명령줄 명령, 데이터베이스 테이블 및 열 이름, 클릭할 수 없게 하려는 URL 등에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-174">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="ae358-175">링크</span><span class="sxs-lookup"><span data-stu-id="ae358-175">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="ae358-176">내부 링크</span><span class="sxs-lookup"><span data-stu-id="ae358-176">Internal Links</span></span>

<span data-ttu-id="ae358-177">같은 Markdown 파일의 헤더(앵커 링크라고도 함)에 연결하려면 연결할 헤더의 ID를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-177">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="ae358-178">ID를 확인하려면 렌더링된 문서의 소스를 확인하여 헤더의 ID(예: `id="blockquote"`)를 찾은 다음 `#blockquote`와 같이 # + ID를 사용하여 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-178">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="ae358-179">ID는 헤더 텍스트에 따라 자동 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-179">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="ae358-180">예를 들어 이름이 `## Step 2`인 고유 섹션의 경우 ID는 `id="step-2"`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-180">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="ae358-181">예: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)`에서 [언어 식별자를 사용하여 인라인 블록 선언](#inline-code-blocks-with-language-identifier)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-181">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="ae358-182">같은 리포지토리의 Markdown 파일에 연결하려면 파일 이름 끝의 ".md"를 포함한 [상대 링크](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-182">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="ae358-183">예: `[Readme file](../README.md)`에서 [Readme 파일](../README.md)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-183">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="ae358-184">(링크는 대/소문자를 구분합니다.)</span><span class="sxs-lookup"><span data-stu-id="ae358-184">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="ae358-185">예: `[Welcome to .NET](../docs/welcome.md)`에서 [.NET 시작](../docs/welcome.md)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-185">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="ae358-186">같은 리포지토리에 있는 Markdown 파일의 헤더에 연결하려면 상대 링크 + 해시 태그 링크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-186">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="ae358-187">예: `[.NET Community](../docs/welcome.md#open-source)`에서 [.NET Community](../docs/welcome.md#open-source)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-187">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="ae358-188">대부분의 경우에는 상대 링크가 GitHub의 소스에서 확인되므로 상대 링크를 사용하고 링크에서 `~/` 사용을 억제합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-188">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="ae358-189">그러나 종속 리포지토리의 파일에 연결할 때마다 `~/` 문자를 사용하여 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-189">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="ae358-190">종속 리포지토리의 파일은 GitHub에서 다른 위치에 있으므로 링크 작성 방법과 관계없이 상대 링크를 사용하여 링크가 제대로 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-190">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="ae358-191">C# 언어 사양 및 Visual Basic 언어 사양은 언어 리포지토리의 소스를 포함하여 . NET 문서에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-191">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="ae358-192">Markdown 소스는 [csharplang](https://github.com/dotnet/csharplang) 및 [visual basic](https://github.com/dotnet/vblang) 리포지토리에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-192">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="ae358-193">사양에 대한 링크는 해당 사양이 포함된 소스 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-193">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="ae358-194">C#의 경우 **~/_csharplang/spec**이고 VB의 경우 **~/_vblang/spec**입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-194">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="ae358-195">예: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)`에서는 [C# 쿼리 식](~/_csharplang/spec/expressions.md#query-expressions)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-195">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="ae358-196">외부 링크</span><span class="sxs-lookup"><span data-stu-id="ae358-196">External Links</span></span>

<span data-ttu-id="ae358-197">외부 파일에 연결하려면 링크로 전체 URL을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-197">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="ae358-198">예: `[GitHub](https://www.github.com)`에서는 [GitHub](https://www.github.com)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-198">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="ae358-199">URL은 Markdown 파일에 표시되는 경우 클릭 가능한 링크로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-199">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="ae358-200">예: `<https://www.github.com>`에서는 <https://www.github.com>을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-200">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="ae358-201">외부 링크의 경우 `https` 프로토콜을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-201">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="ae358-202">`https`를 지원하지 않는 사이트에만 `http` 링크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-202">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="ae358-203">API에 대한 링크</span><span class="sxs-lookup"><span data-stu-id="ae358-203">Links to APIs</span></span>

<span data-ttu-id="ae358-204">빌드 시스템에는 외부 링크를 사용하지 않고도 .NET API에 연결할 수 있는 몇 가지 확장이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-204">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="ae358-205">API에 연결할 때는 소스 코드에서 자동 생성되는 해당 UID(고유 식별자)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-205">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="ae358-206">UID는 정규화된 형식 및 멤버 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-206">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="ae358-207">UID 뒤에 \*(또는 %2A)를 추가하는 경우 링크는 특정 API가 아니라 오버로드 페이지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-207">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="ae358-208">예를 들어 [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_)와 같은 특정 오버로드 대신 일반적인 방식으로 [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) 페이지를 연결하려고 할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-208">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="ae358-209">멤버가 오버로드되지 않은 경우 멤버 페이지에 연결하는 데 \*도 사용할 수 있습니다. 그러면 UID에 매개 변수 목록을 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-209">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="ae358-210">특정 메서드 오버로드에 연결하려면 메서드의 매개 변수마다 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-210">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="ae358-211">예를 들어, \<xref:System.DateTime.ToString>을 통해서는 매개 변수가 없는 [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) 메서드에 연결하는 반면, \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)>를 통해서는 [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) 메서드에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-211">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="ae358-212">`https://xref.docs.microsoft.com/autocomplete`에서 오버로드된 특정 멤버의 UID를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-212">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="ae358-213">쿼리 문자열 “?text= *\<type-member-name>* ”을 통해서는 확인할 UID가 있는 멤버 또는 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-213">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="ae358-214">예를 들어, `https://xref.docs.microsoft.com/autocomplete?text=string.format`에서는 [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) 오버로드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-214">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="ae358-215">[System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1)와 같은 제네릭 형식에 연결하려면 \` (%60) 문자 다음에 제네릭 형식 매개 변수의 수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-215">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="ae358-216">예를 들어, \<xref:System.Nullable%601>에서는 [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) 형식에 연결하는 반면 \<xref:System.Func%602>에서는 [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) 대리자에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-216">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="ae358-217">다음 구문 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-217">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="ae358-218">자동 연결: `<xref:UID>` 또는 `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="ae358-218">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="ae358-219">`displayProperty` 쿼리 매개 변수를 통해서는 정규화된 링크 텍스트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-219">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="ae358-220">기본적으로 링크 텍스트는 멤버 또는 형식 이름만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-220">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="ae358-221">Markdown 링크: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="ae358-221">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="ae358-222">표시되는 링크 텍스트를 사용자 지정하려는 경우에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-222">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="ae358-223">예:</span><span class="sxs-lookup"><span data-stu-id="ae358-223">Examples:</span></span>

- <span data-ttu-id="ae358-224">`<xref:System.String>`은 [문자열](https://docs.microsoft.com/dotnet/api/system.string)로 렌더링</span><span class="sxs-lookup"><span data-stu-id="ae358-224">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="ae358-225">`<xref:System.String?displayProperty=nameWithType>`은 [System.String](https://docs.microsoft.com/dotnet/api/system.string)으로 렌더링</span><span class="sxs-lookup"><span data-stu-id="ae358-225">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="ae358-226">`[String class](xref:System.String)`은 [문자열 클래스](https://docs.microsoft.com/dotnet/api/system.string)로 렌더링</span><span class="sxs-lookup"><span data-stu-id="ae358-226">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="ae358-227">이 표기법을 사용하는 방법에 대한 자세한 내용은 [상호 참조 사용](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae358-227">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="ae358-228">UID를 찾는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-228">There are two ways to find the UID:</span></span>

- <span data-ttu-id="ae358-229">연결하려는 API 페이지의 소스를 확인하고 assetid 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-229">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="ae358-230">개별 오버로드 값은 소스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-230">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="ae358-231">다음 도구를 사용하여 UID 검색 https://xref.docs.microsoft.com/autocomplete?text=tostring (tostring을 사용자가 찾으려는 API 이름의 일부로 대체).</span><span class="sxs-lookup"><span data-stu-id="ae358-231">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="ae358-232">이 도구를 통해서는 UID 부분에서 제공된 `text` 쿼리 매개 변수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-232">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="ae358-233">예를 들어, 멤버 이름(ToString), 부분 멤버 이름(ToStri), 형식 및 멤버 이름(Double.ToString) 등을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-233">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="ae358-234">UID에 특수 문자 \`, \# 또는 \*가 포함된 경우 UID 값은 각각 `%60`, `%23` 및 `%2A`로 인코딩된 HTML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-234">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="ae358-235">때때로 괄호가 인코딩된 것을 볼 수 있지만, 요구 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-235">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="ae358-236">예:</span><span class="sxs-lookup"><span data-stu-id="ae358-236">Examples:</span></span>

- <span data-ttu-id="ae358-237">System.Threading.Tasks.Task\`1은 `System.Threading.Tasks.Task%601`이 됨</span><span class="sxs-lookup"><span data-stu-id="ae358-237">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="ae358-238">System.Exception.\#ctor은 `System.Exception.%23ctor`이 됨</span><span class="sxs-lookup"><span data-stu-id="ae358-238">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="ae358-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode)은 `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`가 됨</span><span class="sxs-lookup"><span data-stu-id="ae358-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="ae358-240">목록</span><span class="sxs-lookup"><span data-stu-id="ae358-240">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="ae358-241">순서가 지정된 목록</span><span class="sxs-lookup"><span data-stu-id="ae358-241">Ordered lists</span></span>

1. <span data-ttu-id="ae358-242">This</span><span class="sxs-lookup"><span data-stu-id="ae358-242">This</span></span>
1. <span data-ttu-id="ae358-243">예</span><span class="sxs-lookup"><span data-stu-id="ae358-243">Is</span></span>
1. <span data-ttu-id="ae358-244">입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-244">An</span></span>
1. <span data-ttu-id="ae358-245">Ordered</span><span class="sxs-lookup"><span data-stu-id="ae358-245">Ordered</span></span>
1. <span data-ttu-id="ae358-246">목록</span><span class="sxs-lookup"><span data-stu-id="ae358-246">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="ae358-247">포함된 목록이 있는 순서가 지정된 목록</span><span class="sxs-lookup"><span data-stu-id="ae358-247">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="ae358-248">여기</span><span class="sxs-lookup"><span data-stu-id="ae358-248">Here</span></span>
1. <span data-ttu-id="ae358-249">에</span><span class="sxs-lookup"><span data-stu-id="ae358-249">comes</span></span>
1. <span data-ttu-id="ae358-250">an</span><span class="sxs-lookup"><span data-stu-id="ae358-250">an</span></span>
1. <span data-ttu-id="ae358-251">포함된</span><span class="sxs-lookup"><span data-stu-id="ae358-251">embedded</span></span>
    1. <span data-ttu-id="ae358-252">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="ae358-252">Miss Scarlett</span></span>
    1. <span data-ttu-id="ae358-253">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="ae358-253">Professor Plum</span></span>
1. <span data-ttu-id="ae358-254">ordered</span><span class="sxs-lookup"><span data-stu-id="ae358-254">ordered</span></span>
1. <span data-ttu-id="ae358-255">list</span><span class="sxs-lookup"><span data-stu-id="ae358-255">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="ae358-256">순서가 지정되지 않은 목록</span><span class="sxs-lookup"><span data-stu-id="ae358-256">Unordered Lists</span></span>

- <span data-ttu-id="ae358-257">This</span><span class="sxs-lookup"><span data-stu-id="ae358-257">This</span></span>
- <span data-ttu-id="ae358-258">is</span><span class="sxs-lookup"><span data-stu-id="ae358-258">is</span></span>
- <span data-ttu-id="ae358-259">a</span><span class="sxs-lookup"><span data-stu-id="ae358-259">a</span></span>
- <span data-ttu-id="ae358-260">글머리 기호</span><span class="sxs-lookup"><span data-stu-id="ae358-260">bulleted</span></span>
- <span data-ttu-id="ae358-261">list</span><span class="sxs-lookup"><span data-stu-id="ae358-261">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="ae358-262">포함된 목록이 있는 순서가 지정되지 않은 목록</span><span class="sxs-lookup"><span data-stu-id="ae358-262">Unordered list with an embedded list</span></span>

- <span data-ttu-id="ae358-263">This</span><span class="sxs-lookup"><span data-stu-id="ae358-263">This</span></span>
- <span data-ttu-id="ae358-264">글머리 기호</span><span class="sxs-lookup"><span data-stu-id="ae358-264">bulleted</span></span>
- <span data-ttu-id="ae358-265">list</span><span class="sxs-lookup"><span data-stu-id="ae358-265">list</span></span>
  - <span data-ttu-id="ae358-266">유유진</span><span class="sxs-lookup"><span data-stu-id="ae358-266">Mrs. Peacock</span></span>
  - <span data-ttu-id="ae358-267">주준서</span><span class="sxs-lookup"><span data-stu-id="ae358-267">Mr. Green</span></span>
- <span data-ttu-id="ae358-268">포함</span><span class="sxs-lookup"><span data-stu-id="ae358-268">contains</span></span>
- <span data-ttu-id="ae358-269">기타</span><span class="sxs-lookup"><span data-stu-id="ae358-269">other</span></span>
  1. <span data-ttu-id="ae358-270">유현기 대령</span><span class="sxs-lookup"><span data-stu-id="ae358-270">Colonel Mustard</span></span>
  1. <span data-ttu-id="ae358-271">안예은</span><span class="sxs-lookup"><span data-stu-id="ae358-271">Mrs. White</span></span>
- <span data-ttu-id="ae358-272">목록</span><span class="sxs-lookup"><span data-stu-id="ae358-272">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="ae358-273">가로줄</span><span class="sxs-lookup"><span data-stu-id="ae358-273">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="ae358-274">Tables</span><span class="sxs-lookup"><span data-stu-id="ae358-274">Tables</span></span>

| <span data-ttu-id="ae358-275">Tables</span><span class="sxs-lookup"><span data-stu-id="ae358-275">Tables</span></span>        | <span data-ttu-id="ae358-276">멋진</span><span class="sxs-lookup"><span data-stu-id="ae358-276">Are</span></span>           | <span data-ttu-id="ae358-277">표</span><span class="sxs-lookup"><span data-stu-id="ae358-277">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="ae358-278">3열은</span><span class="sxs-lookup"><span data-stu-id="ae358-278">col 3 is</span></span>      | <span data-ttu-id="ae358-279">오른쪽 맞춤</span><span class="sxs-lookup"><span data-stu-id="ae358-279">right-aligned</span></span> | <span data-ttu-id="ae358-280">$1600</span><span class="sxs-lookup"><span data-stu-id="ae358-280">$1600</span></span> |
| <span data-ttu-id="ae358-281">2열은</span><span class="sxs-lookup"><span data-stu-id="ae358-281">col 2 is</span></span>      | <span data-ttu-id="ae358-282">가운데 맞춤</span><span class="sxs-lookup"><span data-stu-id="ae358-282">centered</span></span>      |   <span data-ttu-id="ae358-283">$12</span><span class="sxs-lookup"><span data-stu-id="ae358-283">$12</span></span> |
| <span data-ttu-id="ae358-284">1열은 기본값</span><span class="sxs-lookup"><span data-stu-id="ae358-284">col 1 is default</span></span> | <span data-ttu-id="ae358-285">왼쪽 맞춤</span><span class="sxs-lookup"><span data-stu-id="ae358-285">left-aligned</span></span>     |    <span data-ttu-id="ae358-286">$1</span><span class="sxs-lookup"><span data-stu-id="ae358-286">$1</span></span> |

<span data-ttu-id="ae358-287">[Markdown 테이블 생성기 도구](https://www.tablesgenerator.com/markdown_tables)를 사용하면 테이블을 보다 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-287">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="ae358-288">코드</span><span class="sxs-lookup"><span data-stu-id="ae358-288">Code</span></span>

<span data-ttu-id="ae358-289">코드를 포함하는 가장 효율적인 방법은 작동하는 샘플의 조각을 포함하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-289">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="ae358-290">[지원 가이드](../CONTRIBUTING.md#contributing-to-samples)의 지침에 따라 샘플을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-290">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="ae358-291">다음 구문을 사용하여 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-291">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="ae358-292">`-<language>`(*선택 사항*이지만 *권장됨*)</span><span class="sxs-lookup"><span data-stu-id="ae358-292">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="ae358-293">참조되는 코드 조각의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-293">Language of the code snippet being referenced.</span></span> <span data-ttu-id="ae358-294">지원되는 값 목록은 [지원되는 언어](#supported-languages)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae358-294">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="ae358-295">`<name>`(*선택 사항*)</span><span class="sxs-lookup"><span data-stu-id="ae358-295">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="ae358-296">코드 조각의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-296">Name for the code snippet.</span></span> <span data-ttu-id="ae358-297">출력 HTML에는 영향을 주지 않지만 이를 사용하여 Markdown 소스에 대한 가독성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-297">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="ae358-298">`<pathToFile>`(*필수*)</span><span class="sxs-lookup"><span data-stu-id="ae358-298">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="ae358-299">참조할 코드 조각 파일을 나타내는 파일 시스템의 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-299">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="ae358-300">`<queryoption>` 및 `<queryoptionvalue>`(*선택 사항*)</span><span class="sxs-lookup"><span data-stu-id="ae358-300">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="ae358-301">파일에서 코드를 검색하는 방법을 지정하는 데 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-301">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="ae358-302">`#`:  `#L{startlinenumber}-L{endlinenumber}`(줄 범위) *또는* `#{tagname}`(태그 이름).</span><span class="sxs-lookup"><span data-stu-id="ae358-302">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="ae358-303">하지만 줄 번호는 변경되기 쉬우므로 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-303">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="ae358-304">태그 이름은 코드 조각을 참조하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-304">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="ae358-305">`range`: `?range=1,3-5` 줄의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-305">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="ae358-306">이 예에는 줄 1, 3, 4 및 5가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-306">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="ae358-307">`dedent`: `?dedent=8` 공백 수(이 경우 8)만큼 줄 들여쓰기를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-307">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="ae358-308">이는 `range` 및 파일 줄의 하위 집합을 선택하는 기타 쿼리 옵션과 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-308">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="ae358-309">`outdent`: `?outdent=8` 공백 수(이 경우 8)만큼 줄 들여쓰기를 뒤바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-309">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="ae358-310">이는 `range` 및 파일 줄의 하위 집합을 선택하는 기타 쿼리 옵션과 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-310">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="ae358-311">가능하면 태그 이름 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-311">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="ae358-312">태그 이름은 소스 코드에 있는 `Snippettagname` 형식의 코드 주석 또는 지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-312">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="ae358-313">다음 예제에서는 태그 이름 `1`을 참조하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-313">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="ae358-314">[이 소스 파일](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs)에서 코드 조각 태그가 구성된 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-314">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="ae358-315">언어별 코드 조각 소스 파일의 태그 이름 표현에 관한 자세한 내용은 [DocFX 지침](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae358-315">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="ae358-316">전체 프로그램의 조각을 포함하면 모든 코드가 Microsoft CI(연속 통합) 시스템을 통해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-316">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="ae358-317">그러나 컴파일 시간 또는 런타임 오류를 발생시키는 항목을 표시해야 하는 경우 인라인 코드 블록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-317">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="ae358-318">언어 식별자가 포함된 인라인 코드 블록</span><span class="sxs-lookup"><span data-stu-id="ae358-318">Inline code blocks with language identifier</span></span>

<span data-ttu-id="ae358-319">3개의 backtick(\`\`\`) + 언어 ID를 사용항여 코드 블록에 언어별 색 코딩을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-319">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="ae358-320">다음은 지원되는 언어 목록으로, 각 언어 ID의 markdown 레이블을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-320">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="ae358-321">지원되는 언어</span><span class="sxs-lookup"><span data-stu-id="ae358-321">Supported languages</span></span>

|<span data-ttu-id="ae358-322">name</span><span class="sxs-lookup"><span data-stu-id="ae358-322">Name</span></span>|<span data-ttu-id="ae358-323">Markdown 레이블</span><span class="sxs-lookup"><span data-stu-id="ae358-323">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="ae358-324">.NET 콘솔</span><span class="sxs-lookup"><span data-stu-id="ae358-324">.NET Console</span></span>|<span data-ttu-id="ae358-325">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="ae358-325">dotnetcli</span></span>|
|<span data-ttu-id="ae358-326">ASP.NET(C#)</span><span class="sxs-lookup"><span data-stu-id="ae358-326">ASP.NET (C#)</span></span>|<span data-ttu-id="ae358-327">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="ae358-327">aspx-csharp</span></span>|
|<span data-ttu-id="ae358-328">ASP.NET(VB)</span><span class="sxs-lookup"><span data-stu-id="ae358-328">ASP.NET (VB)</span></span>|<span data-ttu-id="ae358-329">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="ae358-329">aspx-vb</span></span>|
|<span data-ttu-id="ae358-330">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="ae358-330">Azure CLI</span></span>|<span data-ttu-id="ae358-331">azurecli</span><span class="sxs-lookup"><span data-stu-id="ae358-331">azurecli</span></span>|
|<span data-ttu-id="ae358-332">AzCopy</span><span class="sxs-lookup"><span data-stu-id="ae358-332">AzCopy</span></span>|<span data-ttu-id="ae358-333">azcopy</span><span class="sxs-lookup"><span data-stu-id="ae358-333">azcopy</span></span>|
|<span data-ttu-id="ae358-334">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae358-334">Azure PowerShell</span></span>|<span data-ttu-id="ae358-335">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="ae358-335">azurepowershell</span></span>|
|<span data-ttu-id="ae358-336">Bash</span><span class="sxs-lookup"><span data-stu-id="ae358-336">Bash</span></span>|<span data-ttu-id="ae358-337">bash</span><span class="sxs-lookup"><span data-stu-id="ae358-337">bash</span></span>|
|<span data-ttu-id="ae358-338">C++</span><span class="sxs-lookup"><span data-stu-id="ae358-338">C++</span></span>|<span data-ttu-id="ae358-339">cpp</span><span class="sxs-lookup"><span data-stu-id="ae358-339">cpp</span></span>|
|<span data-ttu-id="ae358-340">C++/CX</span><span class="sxs-lookup"><span data-stu-id="ae358-340">C++/CX</span></span>|<span data-ttu-id="ae358-341">cppcx</span><span class="sxs-lookup"><span data-stu-id="ae358-341">cppcx</span></span>|
|<span data-ttu-id="ae358-342">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="ae358-342">C++/WinRT</span></span>|<span data-ttu-id="ae358-343">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="ae358-343">cppwinrt</span></span>|
|<span data-ttu-id="ae358-344">C#</span><span class="sxs-lookup"><span data-stu-id="ae358-344">C#</span></span>|<span data-ttu-id="ae358-345">c샵</span><span class="sxs-lookup"><span data-stu-id="ae358-345">csharp</span></span>|
|<span data-ttu-id="ae358-346">브라우저의 C#</span><span class="sxs-lookup"><span data-stu-id="ae358-346">C# in browser</span></span>|<span data-ttu-id="ae358-347">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="ae358-347">csharp-interactive</span></span>|
|<span data-ttu-id="ae358-348">Console</span><span class="sxs-lookup"><span data-stu-id="ae358-348">Console</span></span>|<span data-ttu-id="ae358-349">콘솔</span><span class="sxs-lookup"><span data-stu-id="ae358-349">console</span></span>|
|<span data-ttu-id="ae358-350">CSHTML</span><span class="sxs-lookup"><span data-stu-id="ae358-350">CSHTML</span></span>|<span data-ttu-id="ae358-351">cshtml</span><span class="sxs-lookup"><span data-stu-id="ae358-351">cshtml</span></span>|
|<span data-ttu-id="ae358-352">DAX</span><span class="sxs-lookup"><span data-stu-id="ae358-352">DAX</span></span>|<span data-ttu-id="ae358-353">dax</span><span class="sxs-lookup"><span data-stu-id="ae358-353">dax</span></span>|
|<span data-ttu-id="ae358-354">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="ae358-354">Dockerfile</span></span>|<span data-ttu-id="ae358-355">dockerfile</span><span class="sxs-lookup"><span data-stu-id="ae358-355">dockerfile</span></span>|
|<span data-ttu-id="ae358-356">F#</span><span class="sxs-lookup"><span data-stu-id="ae358-356">F#</span></span>|<span data-ttu-id="ae358-357">fsharp</span><span class="sxs-lookup"><span data-stu-id="ae358-357">fsharp</span></span>|
|<span data-ttu-id="ae358-358">이동</span><span class="sxs-lookup"><span data-stu-id="ae358-358">Go</span></span>|<span data-ttu-id="ae358-359">이동</span><span class="sxs-lookup"><span data-stu-id="ae358-359">go</span></span>|
|<span data-ttu-id="ae358-360">HTML</span><span class="sxs-lookup"><span data-stu-id="ae358-360">HTML</span></span>|<span data-ttu-id="ae358-361">html</span><span class="sxs-lookup"><span data-stu-id="ae358-361">html</span></span>|
|<span data-ttu-id="ae358-362">HTTP</span><span class="sxs-lookup"><span data-stu-id="ae358-362">HTTP</span></span>|<span data-ttu-id="ae358-363">http</span><span class="sxs-lookup"><span data-stu-id="ae358-363">http</span></span>|
|<span data-ttu-id="ae358-364">Java</span><span class="sxs-lookup"><span data-stu-id="ae358-364">Java</span></span>|<span data-ttu-id="ae358-365">java</span><span class="sxs-lookup"><span data-stu-id="ae358-365">java</span></span>|
|<span data-ttu-id="ae358-366">JavaScript</span><span class="sxs-lookup"><span data-stu-id="ae358-366">JavaScript</span></span>|<span data-ttu-id="ae358-367">javascript</span><span class="sxs-lookup"><span data-stu-id="ae358-367">javascript</span></span>|
|<span data-ttu-id="ae358-368">JSON</span><span class="sxs-lookup"><span data-stu-id="ae358-368">JSON</span></span>|<span data-ttu-id="ae358-369">json :</span><span class="sxs-lookup"><span data-stu-id="ae358-369">json</span></span>|
|<span data-ttu-id="ae358-370">Kusto 쿼리 언어</span><span class="sxs-lookup"><span data-stu-id="ae358-370">Kusto Query Language</span></span>|<span data-ttu-id="ae358-371">kusto</span><span class="sxs-lookup"><span data-stu-id="ae358-371">kusto</span></span>|
|<span data-ttu-id="ae358-372">Markdown</span><span class="sxs-lookup"><span data-stu-id="ae358-372">Markdown</span></span>|<span data-ttu-id="ae358-373">md</span><span class="sxs-lookup"><span data-stu-id="ae358-373">md</span></span>|
|<span data-ttu-id="ae358-374">NodeJS</span><span class="sxs-lookup"><span data-stu-id="ae358-374">NodeJS</span></span>|<span data-ttu-id="ae358-375">nodejs</span><span class="sxs-lookup"><span data-stu-id="ae358-375">nodejs</span></span>|
|<span data-ttu-id="ae358-376">Objective-C</span><span class="sxs-lookup"><span data-stu-id="ae358-376">Objective-C</span></span>|<span data-ttu-id="ae358-377">objc</span><span class="sxs-lookup"><span data-stu-id="ae358-377">objc</span></span>|
|<span data-ttu-id="ae358-378">OData</span><span class="sxs-lookup"><span data-stu-id="ae358-378">OData</span></span>|<span data-ttu-id="ae358-379">odata</span><span class="sxs-lookup"><span data-stu-id="ae358-379">odata</span></span>|
|<span data-ttu-id="ae358-380">PHP</span><span class="sxs-lookup"><span data-stu-id="ae358-380">PHP</span></span>|<span data-ttu-id="ae358-381">php</span><span class="sxs-lookup"><span data-stu-id="ae358-381">php</span></span>|
|<span data-ttu-id="ae358-382">protobuf</span><span class="sxs-lookup"><span data-stu-id="ae358-382">protobuf</span></span>|<span data-ttu-id="ae358-383">protobuf</span><span class="sxs-lookup"><span data-stu-id="ae358-383">protobuf</span></span>|
|<span data-ttu-id="ae358-384">PowerApps(점 소수 구분 기호)</span><span class="sxs-lookup"><span data-stu-id="ae358-384">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="ae358-385">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="ae358-385">powerapps-dot</span></span>|
|<span data-ttu-id="ae358-386">PowerApps(쉼표 소수 구분 기호)</span><span class="sxs-lookup"><span data-stu-id="ae358-386">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="ae358-387">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="ae358-387">powerapps-comma</span></span>|
|<span data-ttu-id="ae358-388">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae358-388">PowerShell</span></span>|<span data-ttu-id="ae358-389">powershell</span><span class="sxs-lookup"><span data-stu-id="ae358-389">powershell</span></span>|
|<span data-ttu-id="ae358-390">Python</span><span class="sxs-lookup"><span data-stu-id="ae358-390">Python</span></span>|<span data-ttu-id="ae358-391">python</span><span class="sxs-lookup"><span data-stu-id="ae358-391">python</span></span>|
|<span data-ttu-id="ae358-392">Q#</span><span class="sxs-lookup"><span data-stu-id="ae358-392">Q#</span></span>|<span data-ttu-id="ae358-393">qsharp</span><span class="sxs-lookup"><span data-stu-id="ae358-393">qsharp</span></span>|
|<span data-ttu-id="ae358-394">R</span><span class="sxs-lookup"><span data-stu-id="ae358-394">R</span></span>|<span data-ttu-id="ae358-395">r</span><span class="sxs-lookup"><span data-stu-id="ae358-395">r</span></span>|
|<span data-ttu-id="ae358-396">Ruby</span><span class="sxs-lookup"><span data-stu-id="ae358-396">Ruby</span></span>|<span data-ttu-id="ae358-397">ruby</span><span class="sxs-lookup"><span data-stu-id="ae358-397">ruby</span></span>|
|<span data-ttu-id="ae358-398">SQL</span><span class="sxs-lookup"><span data-stu-id="ae358-398">SQL</span></span>|<span data-ttu-id="ae358-399">sql</span><span class="sxs-lookup"><span data-stu-id="ae358-399">sql</span></span>|
|<span data-ttu-id="ae358-400">Swift</span><span class="sxs-lookup"><span data-stu-id="ae358-400">Swift</span></span>|<span data-ttu-id="ae358-401">swift</span><span class="sxs-lookup"><span data-stu-id="ae358-401">swift</span></span>|
|<span data-ttu-id="ae358-402">TypeScript</span><span class="sxs-lookup"><span data-stu-id="ae358-402">TypeScript</span></span>|<span data-ttu-id="ae358-403">typescript</span><span class="sxs-lookup"><span data-stu-id="ae358-403">typescript</span></span>|
|<span data-ttu-id="ae358-404">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae358-404">Visual Basic</span></span>|<span data-ttu-id="ae358-405">vb</span><span class="sxs-lookup"><span data-stu-id="ae358-405">vb</span></span>|
|<span data-ttu-id="ae358-406">VBScript</span><span class="sxs-lookup"><span data-stu-id="ae358-406">VBScript</span></span>|<span data-ttu-id="ae358-407">vbscript</span><span class="sxs-lookup"><span data-stu-id="ae358-407">vbscript</span></span>|
|<span data-ttu-id="ae358-408">XAML</span><span class="sxs-lookup"><span data-stu-id="ae358-408">XAML</span></span>|<span data-ttu-id="ae358-409">xaml</span><span class="sxs-lookup"><span data-stu-id="ae358-409">xaml</span></span>|
|<span data-ttu-id="ae358-410">XML</span><span class="sxs-lookup"><span data-stu-id="ae358-410">XML</span></span>|<span data-ttu-id="ae358-411">Xml</span><span class="sxs-lookup"><span data-stu-id="ae358-411">xml</span></span>|

<span data-ttu-id="ae358-412">`csharp-interactive` 이름은 C# 언어를 지정하고 브라우저에서 샘플을 실행하는 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-412">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="ae358-413">해당 코드 조각은 Docker 컨테이너에서 컴파일되고 실행되며, 해당 프로그램의 실행 결과는 사용자의 브라우저 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-413">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="ae358-414">다음은 C#(\`\`\`csharp), Python(\`\`\`python) 및 PowerShell(\`\`\`powershell)의 언어 ID를 사용하는 코드 블록의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-414">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c"></a><span data-ttu-id="ae358-415">C\#</span><span class="sxs-lookup"><span data-stu-id="ae358-415">C\#</span></span>

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a><span data-ttu-id="ae358-416">Python</span><span class="sxs-lookup"><span data-stu-id="ae358-416">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="ae358-417">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae358-417">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="ae358-418">제네릭 코드 블록</span><span class="sxs-lookup"><span data-stu-id="ae358-418">Generic code block</span></span>

<span data-ttu-id="ae358-419">제네릭 코드 블록 코딩에는 3개의 backtick(&#96;&#96;&#96;)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-419">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="ae358-420">이 경우 설명서 사이트에서 적절한 구문이 강조 표시되도록 이전 섹션에서 설명한 것처럼 언어 식별자가 포함된 코드 블록을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-420">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="ae358-421">제네릭 코드 블록은 필요할 때만 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ae358-421">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="ae358-422">blockquote</span><span class="sxs-lookup"><span data-stu-id="ae358-422">Blockquotes</span></span>

> <span data-ttu-id="ae358-423">가뭄이 천만 년이나 계속되어 끔찍한 도마뱀이 다스리던 시대도 끝이 났습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-423">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="ae358-424">후세에는 아프리카라고 불릴 대륙인 이곳 적도에서는 생존을 위한 싸움이 극에 달했으며 아직은 누구도 승리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-424">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="ae358-425">이 황량하고 말라빠진 땅에서는 작고 날쌔며 사나운 생명체만이 살아남거나, 살아남을 수 있다는 희망이라도 품을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-425">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="ae358-426">이미지</span><span class="sxs-lookup"><span data-stu-id="ae358-426">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="ae358-427">정적 이미지 또는 애니메이션 gif</span><span class="sxs-lookup"><span data-stu-id="ae358-427">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![대체 텍스트입니다.](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="ae358-429">연결된 이미지</span><span class="sxs-lookup"><span data-stu-id="ae358-429">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="ae358-430">[![연결된 이미지의 대체 텍스트](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="ae358-430">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="ae358-431">비디오</span><span class="sxs-lookup"><span data-stu-id="ae358-431">Videos</span></span>

<span data-ttu-id="ae358-432">현재, 다음 구문을 사용하여 Channel 9 및 YouTube 동영상을 모두 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-432">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="ae358-433">Channel 9</span><span class="sxs-lookup"><span data-stu-id="ae358-433">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="ae358-434">동영상의 올바른 URL을 가져오려면 동영상 프레임 아래의 **포함** 탭을 선택하고 `<iframe>` 요소에서 URL을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-434">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="ae358-435">예:</span><span class="sxs-lookup"><span data-stu-id="ae358-435">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="ae358-436">YouTube</span><span class="sxs-lookup"><span data-stu-id="ae358-436">YouTube</span></span>

<span data-ttu-id="ae358-437">동영상의 올바른 URL을 가져오려면 동영상을 마우스 오른쪽 단추로 클릭하고 **Embed 태그 복사**를 선택한 다음, `<iframe>` 요소에서 URL을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-437">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="ae358-438">예:</span><span class="sxs-lookup"><span data-stu-id="ae358-438">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="ae358-439">docs.microsoft 확장</span><span class="sxs-lookup"><span data-stu-id="ae358-439">docs.microsoft extensions</span></span>

<span data-ttu-id="ae358-440">docs.microsoft는 GitHub Flavored Markdown에 대해 몇 가지 추가 확장을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-440">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="ae358-441">경고</span><span class="sxs-lookup"><span data-stu-id="ae358-441">Alerts</span></span>

<span data-ttu-id="ae358-442">설명서 사이트에서 적절한 스타일로 렌더링되도록 다음 경고 스타일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-442">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="ae358-443">그러나 GitHub의 렌더링 엔진은 스타일을 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-443">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="ae358-444">그러면 이러한 항목은 다음과 같이 렌더링됩니다. ![경고 스타일](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="ae358-444">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="ae358-445">포함되는 내용</span><span class="sxs-lookup"><span data-stu-id="ae358-445">Includes</span></span>

<span data-ttu-id="ae358-446">Include를 사용하여 한 파일의 Markdown을 다른 파일에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-446">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="ae358-447">선택된 목록</span><span class="sxs-lookup"><span data-stu-id="ae358-447">Checked lists</span></span>

<span data-ttu-id="ae358-448">목록의 경우 사용자 지정 스타일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-448">A custom style is available for lists.</span></span> <span data-ttu-id="ae358-449">녹색 확인 표시가 있는 목록을 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-449">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="ae358-450">.NET Core 앱을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="ae358-450">How to create a .NET Core app</span></span>
> - <span data-ttu-id="ae358-451">Microsoft.XmlSerializer.Generator 패키지에 대한 참조를 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="ae358-451">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="ae358-452">MyApp.csproj를 편집하여 종속성을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="ae358-452">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="ae358-453">클래스 및 XmlSerializer를 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="ae358-453">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="ae358-454">애플리케이션을 빌드하고 실행하는 방법</span><span class="sxs-lookup"><span data-stu-id="ae358-454">How to build and run the application</span></span>

<span data-ttu-id="ae358-455">[.NET Core 문서](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator)에서 작동 중인 선택된 목록의 예를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-455">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="ae358-456">단추</span><span class="sxs-lookup"><span data-stu-id="ae358-456">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="ae358-457">단추 링크</span><span class="sxs-lookup"><span data-stu-id="ae358-457">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="ae358-458">[Visual Studio 문서](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio)에서 작동 중인 단추의 예를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-458">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="ae358-459">선택기</span><span class="sxs-lookup"><span data-stu-id="ae358-459">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="ae358-462">[Azure 문서](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic)에서 작동 중인 선택기의 예를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-462">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="ae358-463">단계별 작업</span><span class="sxs-lookup"><span data-stu-id="ae358-463">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ae358-464">[이전](../docs/csharp/expression-trees-interpreting.md)
>[다음](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="ae358-464">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="ae358-465">[C# 가이드](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure)에서 작동 중인 단계별 예제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae358-465">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
