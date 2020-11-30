---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032630"
---
### <a name="razor-razortemplateengine-api-removed"></a><span data-ttu-id="a5807-101">Razor: RazorTemplateEngine API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="a5807-101">Razor: RazorTemplateEngine API removed</span></span>

<span data-ttu-id="a5807-102">[RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) API가 제거되고 <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>으로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-102">The [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) API was removed and replaced with <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.</span></span>

<span data-ttu-id="a5807-103">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5807-103">For discussion, see GitHub issue [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a5807-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a5807-104">Version introduced</span></span>

<span data-ttu-id="a5807-105">3.0</span><span class="sxs-lookup"><span data-stu-id="a5807-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a5807-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="a5807-106">Old behavior</span></span>

<span data-ttu-id="a5807-107">템플릿 엔진을 만들고 Razor 파일의 코드를 구문 분석하고 생성하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-107">A template engine can be created and used to parse and generate code for Razor files.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a5807-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="a5807-108">New behavior</span></span>

<span data-ttu-id="a5807-109">`RazorProjectEngine`을 만들고 Razor 파일의 코드를 구문 분석하고 생성하기 위해 해당 엔진에 `RazorTemplateEngine`과 동일한 유형의 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-109">`RazorProjectEngine` can be created and provided the same type of information as `RazorTemplateEngine` to parse and generate code for Razor files.</span></span> <span data-ttu-id="a5807-110">`RazorProjectEngine`은 추가 수준의 구성도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-110">`RazorProjectEngine` also provides extra levels of configuration.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a5807-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="a5807-111">Reason for change</span></span>

<span data-ttu-id="a5807-112">`RazorTemplateEngine`이 기존 구현과 너무 긴밀하게 결합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-112">`RazorTemplateEngine` was too tightly coupled to the existing implementations.</span></span> <span data-ttu-id="a5807-113">이러한 결합으로 인해 Razor 구문 분석/생성 파이프라인을 제대로 구성하려고 할 때 더 많은 질문이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-113">This tight coupling led to more questions when trying to properly configure a Razor parsing/generation pipeline.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a5807-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a5807-114">Recommended action</span></span>

<span data-ttu-id="a5807-115">`RazorTemplateEngine` 대신 `RazorProjectEngine`을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5807-115">Use `RazorProjectEngine` instead of `RazorTemplateEngine`.</span></span> <span data-ttu-id="a5807-116">다음 예제를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="a5807-116">Consider the following examples.</span></span>

##### <a name="create-and-configure-the-razorprojectengine"></a><span data-ttu-id="a5807-117">RazorProjectEngine 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="a5807-117">Create and configure the RazorProjectEngine</span></span>

```csharp
RazorProjectEngine projectEngine =
    RazorProjectEngine.Create(RazorConfiguration.Default,
        RazorProjectFileSystem.Create(@"C:\source\repos\ConsoleApp4\ConsoleApp4"),
        builder =>
        {
            builder.ConfigureClass((document, classNode) =>
            {
                classNode.ClassName = "MyClassName";

                // Can also configure other aspects of the class here.
            });

            // More configuration can go here
        });
```

##### <a name="generate-code-for-a-razor-file"></a><span data-ttu-id="a5807-118">Razor 파일의 코드 생성</span><span class="sxs-lookup"><span data-stu-id="a5807-118">Generate code for a Razor file</span></span>

```csharp
RazorProjectItem item = projectEngine.FileSystem.GetItem(
    @"C:\source\repos\ConsoleApp4\ConsoleApp4\Example.cshtml",
    FileKinds.Legacy);
RazorCodeDocument output = projectEngine.Process(item);

// Things available
RazorSyntaxTree syntaxTree = output.GetSyntaxTree();
DocumentIntermediateNode intermediateDocument =
    output.GetDocumentIntermediateNode();
RazorCSharpDocument csharpDocument = output.GetCSharpDocument();
```

#### <a name="category"></a><span data-ttu-id="a5807-119">범주</span><span class="sxs-lookup"><span data-stu-id="a5807-119">Category</span></span>

<span data-ttu-id="a5807-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a5807-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a5807-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a5807-121">Affected APIs</span></span>

- [<span data-ttu-id="a5807-122">RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="a5807-122">RazorTemplateEngine</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [<span data-ttu-id="a5807-123">RazorTemplateEngineOptions</span><span class="sxs-lookup"><span data-stu-id="a5807-123">RazorTemplateEngineOptions</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
