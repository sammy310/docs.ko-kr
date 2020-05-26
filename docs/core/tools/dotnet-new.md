---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442243"
---
# <a name="dotnet-new"></a><span data-ttu-id="5240a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="5240a-103">dotnet new</span></span>

<span data-ttu-id="5240a-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5240a-105">이름</span><span class="sxs-lookup"><span data-stu-id="5240a-105">Name</span></span>

<span data-ttu-id="5240a-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5240a-107">개요</span><span class="sxs-lookup"><span data-stu-id="5240a-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="5240a-108">설명</span><span class="sxs-lookup"><span data-stu-id="5240a-108">Description</span></span>

<span data-ttu-id="5240a-109">`dotnet new` 명령은 템플릿을 기반으로 .NET Core 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="5240a-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="5240a-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="5240a-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="5240a-112">인수</span><span class="sxs-lookup"><span data-stu-id="5240a-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="5240a-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="5240a-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="5240a-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="5240a-116">`dotnet new --list` 또는 `dotnet new -l`을 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="5240a-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="5240a-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="5240a-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="5240a-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="5240a-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5240a-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="5240a-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="5240a-122">다음 표에는 .NET Core SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="5240a-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="5240a-124">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="5240a-125">템플릿</span><span class="sxs-lookup"><span data-stu-id="5240a-125">Templates</span></span>                                    | <span data-ttu-id="5240a-126">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="5240a-126">Short name</span></span>                      | <span data-ttu-id="5240a-127">언어</span><span class="sxs-lookup"><span data-stu-id="5240a-127">Language</span></span>     | <span data-ttu-id="5240a-128">Tags</span><span class="sxs-lookup"><span data-stu-id="5240a-128">Tags</span></span>                                  | <span data-ttu-id="5240a-129">도입</span><span class="sxs-lookup"><span data-stu-id="5240a-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="5240a-130">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="5240a-130">Console Application</span></span>                          | [<span data-ttu-id="5240a-131">콘솔</span><span class="sxs-lookup"><span data-stu-id="5240a-131">console</span></span>](#console)             | <span data-ttu-id="5240a-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5240a-132">[C#], F#, VB</span></span> | <span data-ttu-id="5240a-133">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="5240a-133">Common/Console</span></span>                        | <span data-ttu-id="5240a-134">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-134">1.0</span></span>        |
| <span data-ttu-id="5240a-135">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-135">Class library</span></span>                                | [<span data-ttu-id="5240a-136">classlib</span><span class="sxs-lookup"><span data-stu-id="5240a-136">classlib</span></span>](#classlib)           | <span data-ttu-id="5240a-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5240a-137">[C#], F#, VB</span></span> | <span data-ttu-id="5240a-138">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-138">Common/Library</span></span>                        | <span data-ttu-id="5240a-139">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-139">1.0</span></span>        |
| <span data-ttu-id="5240a-140">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="5240a-140">WPF Application</span></span>                              | [<span data-ttu-id="5240a-141">wpf</span><span class="sxs-lookup"><span data-stu-id="5240a-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="5240a-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-142">[C#]</span></span>         | <span data-ttu-id="5240a-143">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="5240a-143">Common/WPF</span></span>                            | <span data-ttu-id="5240a-144">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-144">3.0</span></span>        |
| <span data-ttu-id="5240a-145">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-145">WPF Class library</span></span>                            | [<span data-ttu-id="5240a-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="5240a-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="5240a-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-147">[C#]</span></span>         | <span data-ttu-id="5240a-148">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="5240a-148">Common/WPF</span></span>                            | <span data-ttu-id="5240a-149">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-149">3.0</span></span>        |
| <span data-ttu-id="5240a-150">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="5240a-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="5240a-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="5240a-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-152">[C#]</span></span>         | <span data-ttu-id="5240a-153">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="5240a-153">Common/WPF</span></span>                            | <span data-ttu-id="5240a-154">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-154">3.0</span></span>        |
| <span data-ttu-id="5240a-155">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="5240a-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="5240a-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="5240a-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-157">[C#]</span></span>         | <span data-ttu-id="5240a-158">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="5240a-158">Common/WPF</span></span>                            | <span data-ttu-id="5240a-159">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-159">3.0</span></span>        |
| <span data-ttu-id="5240a-160">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="5240a-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="5240a-161">winforms</span><span class="sxs-lookup"><span data-stu-id="5240a-161">winforms</span></span>](#winforms)           | <span data-ttu-id="5240a-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-162">[C#]</span></span>         | <span data-ttu-id="5240a-163">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="5240a-163">Common/WinForms</span></span>                       | <span data-ttu-id="5240a-164">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-164">3.0</span></span>        |
| <span data-ttu-id="5240a-165">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="5240a-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="5240a-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="5240a-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-167">[C#]</span></span>         | <span data-ttu-id="5240a-168">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="5240a-168">Common/WinForms</span></span>                       | <span data-ttu-id="5240a-169">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-169">3.0</span></span>        |
| <span data-ttu-id="5240a-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="5240a-170">Worker Service</span></span>                               | [<span data-ttu-id="5240a-171">worker</span><span class="sxs-lookup"><span data-stu-id="5240a-171">worker</span></span>](#web-others)           | <span data-ttu-id="5240a-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-172">[C#]</span></span>         | <span data-ttu-id="5240a-173">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="5240a-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="5240a-174">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-174">3.0</span></span>        |
| <span data-ttu-id="5240a-175">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="5240a-175">Unit Test Project</span></span>                            | [<span data-ttu-id="5240a-176">mstest</span><span class="sxs-lookup"><span data-stu-id="5240a-176">mstest</span></span>](#test)                 | <span data-ttu-id="5240a-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5240a-177">[C#], F#, VB</span></span> | <span data-ttu-id="5240a-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="5240a-178">Test/MSTest</span></span>                           | <span data-ttu-id="5240a-179">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-179">1.0</span></span>        |
| <span data-ttu-id="5240a-180">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="5240a-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="5240a-181">nunit</span><span class="sxs-lookup"><span data-stu-id="5240a-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="5240a-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5240a-182">[C#], F#, VB</span></span> | <span data-ttu-id="5240a-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="5240a-183">Test/NUnit</span></span>                            | <span data-ttu-id="5240a-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="5240a-184">2.1.400</span></span>    |
| <span data-ttu-id="5240a-185">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="5240a-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="5240a-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5240a-186">[C#], F#, VB</span></span> | <span data-ttu-id="5240a-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="5240a-187">Test/NUnit</span></span>                            | <span data-ttu-id="5240a-188">2.2</span><span class="sxs-lookup"><span data-stu-id="5240a-188">2.2</span></span>        |
| <span data-ttu-id="5240a-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="5240a-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="5240a-190">xunit</span><span class="sxs-lookup"><span data-stu-id="5240a-190">xunit</span></span>](#test)                  | <span data-ttu-id="5240a-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5240a-191">[C#], F#, VB</span></span> | <span data-ttu-id="5240a-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="5240a-192">Test/xUnit</span></span>                            | <span data-ttu-id="5240a-193">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-193">1.0</span></span>        |
| <span data-ttu-id="5240a-194">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5240a-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="5240a-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-195">[C#]</span></span>         | <span data-ttu-id="5240a-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5240a-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="5240a-197">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-197">3.0</span></span>        |
| <span data-ttu-id="5240a-198">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="5240a-198">Razor Page</span></span>                                   | [<span data-ttu-id="5240a-199">page</span><span class="sxs-lookup"><span data-stu-id="5240a-199">page</span></span>](#page)                   | <span data-ttu-id="5240a-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-200">[C#]</span></span>         | <span data-ttu-id="5240a-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5240a-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="5240a-202">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-202">2.0</span></span>        |
| <span data-ttu-id="5240a-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5240a-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="5240a-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="5240a-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="5240a-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-205">[C#]</span></span>         | <span data-ttu-id="5240a-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5240a-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="5240a-207">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-207">2.0</span></span>        |
| <span data-ttu-id="5240a-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5240a-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="5240a-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-209">[C#]</span></span>         | <span data-ttu-id="5240a-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5240a-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="5240a-211">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-211">2.0</span></span>        |
| <span data-ttu-id="5240a-212">Blazor 서버 앱</span><span class="sxs-lookup"><span data-stu-id="5240a-212">Blazor Server App</span></span>                            | [<span data-ttu-id="5240a-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="5240a-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="5240a-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-214">[C#]</span></span>         | <span data-ttu-id="5240a-215">웹/Blazor</span><span class="sxs-lookup"><span data-stu-id="5240a-215">Web/Blazor</span></span>                            | <span data-ttu-id="5240a-216">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-216">3.0</span></span>        |
| <span data-ttu-id="5240a-217">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="5240a-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="5240a-218">web</span><span class="sxs-lookup"><span data-stu-id="5240a-218">web</span></span>](#web)                     | <span data-ttu-id="5240a-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5240a-219">[C#], F#</span></span>     | <span data-ttu-id="5240a-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="5240a-220">Web/Empty</span></span>                             | <span data-ttu-id="5240a-221">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-221">1.0</span></span>        |
| <span data-ttu-id="5240a-222">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="5240a-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="5240a-223">mvc</span><span class="sxs-lookup"><span data-stu-id="5240a-223">mvc</span></span>](#web-options)             | <span data-ttu-id="5240a-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5240a-224">[C#], F#</span></span>     | <span data-ttu-id="5240a-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="5240a-225">Web/MVC</span></span>                               | <span data-ttu-id="5240a-226">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-226">1.0</span></span>        |
| <span data-ttu-id="5240a-227">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="5240a-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="5240a-228">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="5240a-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="5240a-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-229">[C#]</span></span>         | <span data-ttu-id="5240a-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="5240a-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="5240a-231">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="5240a-232">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="5240a-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="5240a-233">angular</span><span class="sxs-lookup"><span data-stu-id="5240a-233">angular</span></span>](#spa)                 | <span data-ttu-id="5240a-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-234">[C#]</span></span>         | <span data-ttu-id="5240a-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5240a-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="5240a-236">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-236">2.0</span></span>        |
| <span data-ttu-id="5240a-237">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="5240a-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="5240a-238">react</span><span class="sxs-lookup"><span data-stu-id="5240a-238">react</span></span>](#spa)                   | <span data-ttu-id="5240a-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-239">[C#]</span></span>         | <span data-ttu-id="5240a-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5240a-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="5240a-241">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-241">2.0</span></span>        |
| <span data-ttu-id="5240a-242">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="5240a-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="5240a-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="5240a-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="5240a-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-244">[C#]</span></span>         | <span data-ttu-id="5240a-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5240a-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="5240a-246">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-246">2.0</span></span>        |
| <span data-ttu-id="5240a-247">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-247">Razor Class Library</span></span>                          | [<span data-ttu-id="5240a-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="5240a-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="5240a-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-249">[C#]</span></span>         | <span data-ttu-id="5240a-250">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="5240a-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="5240a-251">2.1</span><span class="sxs-lookup"><span data-stu-id="5240a-251">2.1</span></span>        |
| <span data-ttu-id="5240a-252">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="5240a-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="5240a-253">webapi</span><span class="sxs-lookup"><span data-stu-id="5240a-253">webapi</span></span>](#webapi)               | <span data-ttu-id="5240a-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5240a-254">[C#], F#</span></span>     | <span data-ttu-id="5240a-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="5240a-255">Web/WebAPI</span></span>                            | <span data-ttu-id="5240a-256">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-256">1.0</span></span>        |
| <span data-ttu-id="5240a-257">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="5240a-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="5240a-258">grpc</span><span class="sxs-lookup"><span data-stu-id="5240a-258">grpc</span></span>](#web-others)             | <span data-ttu-id="5240a-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="5240a-259">[C#]</span></span>         | <span data-ttu-id="5240a-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="5240a-260">Web/gRPC</span></span>                              | <span data-ttu-id="5240a-261">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-261">3.0</span></span>        |
| <span data-ttu-id="5240a-262">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="5240a-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="5240a-263">Config</span><span class="sxs-lookup"><span data-stu-id="5240a-263">Config</span></span>                                | <span data-ttu-id="5240a-264">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-264">3.0</span></span>        |
| <span data-ttu-id="5240a-265">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="5240a-265">global.json file</span></span>                             | [<span data-ttu-id="5240a-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="5240a-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="5240a-267">Config</span><span class="sxs-lookup"><span data-stu-id="5240a-267">Config</span></span>                                | <span data-ttu-id="5240a-268">2.0</span><span class="sxs-lookup"><span data-stu-id="5240a-268">2.0</span></span>        |
| <span data-ttu-id="5240a-269">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="5240a-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="5240a-270">Config</span><span class="sxs-lookup"><span data-stu-id="5240a-270">Config</span></span>                                | <span data-ttu-id="5240a-271">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-271">1.0</span></span>        |
| <span data-ttu-id="5240a-272">Dotnet 로컬 도구 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="5240a-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="5240a-273">Config</span><span class="sxs-lookup"><span data-stu-id="5240a-273">Config</span></span>                                | <span data-ttu-id="5240a-274">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-274">3.0</span></span>        |
| <span data-ttu-id="5240a-275">웹 구성</span><span class="sxs-lookup"><span data-stu-id="5240a-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="5240a-276">Config</span><span class="sxs-lookup"><span data-stu-id="5240a-276">Config</span></span>                                | <span data-ttu-id="5240a-277">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-277">1.0</span></span>        |
| <span data-ttu-id="5240a-278">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="5240a-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="5240a-279">솔루션</span><span class="sxs-lookup"><span data-stu-id="5240a-279">Solution</span></span>                              | <span data-ttu-id="5240a-280">1.0</span><span class="sxs-lookup"><span data-stu-id="5240a-280">1.0</span></span>        |
| <span data-ttu-id="5240a-281">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="5240a-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="5240a-282">proto</span><span class="sxs-lookup"><span data-stu-id="5240a-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="5240a-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="5240a-283">Web/gRPC</span></span>                              | <span data-ttu-id="5240a-284">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="5240a-285">옵션</span><span class="sxs-lookup"><span data-stu-id="5240a-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="5240a-286">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="5240a-287">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="5240a-288">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5240a-289">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5240a-290">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-290">Prints out help for the command.</span></span> <span data-ttu-id="5240a-291">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="5240a-292">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="5240a-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="5240a-293">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5240a-294">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5240a-295">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="5240a-296">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="5240a-297">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="5240a-298">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="5240a-299">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="5240a-300">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="5240a-301">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-301">The language of the template to create.</span></span> <span data-ttu-id="5240a-302">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="5240a-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5240a-303">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5240a-304">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5240a-305">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="5240a-306">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5240a-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="5240a-307">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-307">The name for the created output.</span></span> <span data-ttu-id="5240a-308">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="5240a-309">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="5240a-310">.NET Core 2.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="5240a-311">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-311">Location to place the generated output.</span></span> <span data-ttu-id="5240a-312">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="5240a-313">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-313">Filters templates based on available types.</span></span> <span data-ttu-id="5240a-314">미리 정의된 값은 `project`, `item` 및 `other`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="5240a-315">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5240a-316">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="5240a-317">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="5240a-318">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5240a-319">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5240a-320">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="5240a-321">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="5240a-322">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="5240a-323">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="5240a-324">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="5240a-325">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="5240a-326">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="5240a-326">Template options</span></span>

<span data-ttu-id="5240a-327">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-327">Each project template may have additional options available.</span></span> <span data-ttu-id="5240a-328">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="5240a-329">콘솔</span><span class="sxs-lookup"><span data-stu-id="5240a-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-330">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-331">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="5240a-332">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-333">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-333">SDK version</span></span> | <span data-ttu-id="5240a-334">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-335">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-336">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5240a-337">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5240a-338">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="5240a-339">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-339">Not supported for F#.</span></span> <span data-ttu-id="5240a-340">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5240a-341">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-342">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="5240a-343">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="5240a-344">classlib</span><span class="sxs-lookup"><span data-stu-id="5240a-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-345">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-346">값: `netcoreapp<version>`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="5240a-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5240a-347">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5240a-348">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5240a-349">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="5240a-350">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-350">Not supported for F#.</span></span> <span data-ttu-id="5240a-351">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5240a-352">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-353">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="5240a-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="5240a-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-355">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-356">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="5240a-357">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5240a-358">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5240a-359">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="5240a-360">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-361">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="5240a-362">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="5240a-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5240a-363">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5240a-364">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="5240a-365">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-366">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="5240a-367">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="5240a-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-368">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-369">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="5240a-370">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-371">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-372">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="5240a-373">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="5240a-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-374">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-375">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="5240a-376">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-377">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-377">SDK version</span></span> | <span data-ttu-id="5240a-378">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-379">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-380">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="5240a-381">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-382">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="5240a-383">nunit</span><span class="sxs-lookup"><span data-stu-id="5240a-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-384">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="5240a-385">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-386">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-386">SDK version</span></span> | <span data-ttu-id="5240a-387">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-388">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-389">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5240a-390">2.2</span><span class="sxs-lookup"><span data-stu-id="5240a-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="5240a-391">2.1</span><span class="sxs-lookup"><span data-stu-id="5240a-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="5240a-392">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-393">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="5240a-394">페이지</span><span class="sxs-lookup"><span data-stu-id="5240a-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="5240a-395">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-395">Namespace for the generated code.</span></span> <span data-ttu-id="5240a-396">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="5240a-397">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="5240a-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="5240a-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="5240a-399">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-399">Namespace for the generated code.</span></span> <span data-ttu-id="5240a-400">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="5240a-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="5240a-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5240a-402">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-402">The type of authentication to use.</span></span> <span data-ttu-id="5240a-403">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-403">The possible values are:</span></span>

  - <span data-ttu-id="5240a-404">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="5240a-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5240a-405">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="5240a-406">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="5240a-407">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="5240a-408">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="5240a-409">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="5240a-410">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5240a-411">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-412">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="5240a-413">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5240a-414">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="5240a-415">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="5240a-416">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="5240a-417">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="5240a-418">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="5240a-419">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5240a-420">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5240a-421">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="5240a-422">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-422">The Client ID for this project.</span></span> <span data-ttu-id="5240a-423">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5240a-424">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="5240a-425">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-425">The domain for the directory tenant.</span></span> <span data-ttu-id="5240a-426">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-427">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="5240a-428">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5240a-429">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5240a-430">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="5240a-431">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5240a-432">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-433">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="5240a-434">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="5240a-435">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-436">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="5240a-437">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-437">Turns off HTTPS.</span></span> <span data-ttu-id="5240a-438">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5240a-439">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5240a-440">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-441">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="5240a-442">웹</span><span class="sxs-lookup"><span data-stu-id="5240a-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-443">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-444">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-445">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5240a-446">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-447">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-447">SDK version</span></span> | <span data-ttu-id="5240a-448">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-449">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-450">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5240a-451">2.1</span><span class="sxs-lookup"><span data-stu-id="5240a-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="5240a-452">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="5240a-453">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="5240a-454">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="5240a-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5240a-455">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-455">The type of authentication to use.</span></span> <span data-ttu-id="5240a-456">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-456">The possible values are:</span></span>

  - <span data-ttu-id="5240a-457">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="5240a-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5240a-458">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="5240a-459">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="5240a-460">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="5240a-461">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="5240a-462">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="5240a-463">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5240a-464">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-465">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="5240a-466">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5240a-467">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="5240a-468">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="5240a-469">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="5240a-470">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="5240a-471">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="5240a-472">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5240a-473">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5240a-474">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="5240a-475">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-475">The Client ID for this project.</span></span> <span data-ttu-id="5240a-476">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5240a-477">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="5240a-478">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-478">The domain for the directory tenant.</span></span> <span data-ttu-id="5240a-479">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-480">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="5240a-481">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5240a-482">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5240a-483">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="5240a-484">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5240a-485">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-486">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="5240a-487">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="5240a-488">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-489">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="5240a-490">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-490">Turns off HTTPS.</span></span> <span data-ttu-id="5240a-491">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5240a-492">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5240a-493">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-494">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-495">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="5240a-496">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-497">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-497">SDK version</span></span> | <span data-ttu-id="5240a-498">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-499">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-500">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="5240a-501">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="5240a-502">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="5240a-503">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="5240a-504">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="5240a-505">.NET Core 3.1.201 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="5240a-506">angular, react</span><span class="sxs-lookup"><span data-stu-id="5240a-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5240a-507">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-507">The type of authentication to use.</span></span> <span data-ttu-id="5240a-508">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="5240a-509">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-509">The possible values are:</span></span>

  - <span data-ttu-id="5240a-510">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="5240a-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5240a-511">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-512">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-513">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="5240a-514">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-514">Turns off HTTPS.</span></span> <span data-ttu-id="5240a-515">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5240a-516">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5240a-517">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-518">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-519">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-520">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5240a-521">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-522">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-522">SDK version</span></span> | <span data-ttu-id="5240a-523">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-524">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-525">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5240a-526">2.1</span><span class="sxs-lookup"><span data-stu-id="5240a-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="5240a-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="5240a-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-528">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-529">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-530">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5240a-531">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-532">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-532">SDK version</span></span> | <span data-ttu-id="5240a-533">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-534">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-535">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5240a-536">2.1</span><span class="sxs-lookup"><span data-stu-id="5240a-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="5240a-537">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="5240a-538">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="5240a-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="5240a-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="5240a-540">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="5240a-541">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="5240a-542">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="5240a-543">webapi</span><span class="sxs-lookup"><span data-stu-id="5240a-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5240a-544">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-544">The type of authentication to use.</span></span> <span data-ttu-id="5240a-545">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-545">The possible values are:</span></span>

  - <span data-ttu-id="5240a-546">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="5240a-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5240a-547">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="5240a-548">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="5240a-549">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="5240a-550">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5240a-551">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5240a-552">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="5240a-553">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5240a-554">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="5240a-555">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5240a-556">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5240a-557">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="5240a-558">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-558">The Client ID for this project.</span></span> <span data-ttu-id="5240a-559">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5240a-560">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="5240a-561">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-561">The domain for the directory tenant.</span></span> <span data-ttu-id="5240a-562">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5240a-563">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="5240a-564">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5240a-565">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5240a-566">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="5240a-567">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="5240a-568">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5240a-569">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="5240a-570">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-570">Turns off HTTPS.</span></span> <span data-ttu-id="5240a-571">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5240a-572">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5240a-573">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5240a-574">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5240a-575">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5240a-576">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5240a-577">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5240a-578">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="5240a-578">SDK version</span></span> | <span data-ttu-id="5240a-579">기본값</span><span class="sxs-lookup"><span data-stu-id="5240a-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5240a-580">3.1</span><span class="sxs-lookup"><span data-stu-id="5240a-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5240a-581">3.0</span><span class="sxs-lookup"><span data-stu-id="5240a-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5240a-582">2.1</span><span class="sxs-lookup"><span data-stu-id="5240a-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="5240a-583">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="5240a-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="5240a-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="5240a-585">*global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="5240a-586">예</span><span class="sxs-lookup"><span data-stu-id="5240a-586">Examples</span></span>

- <span data-ttu-id="5240a-587">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="5240a-588">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="5240a-589">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="5240a-590">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="5240a-591">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="5240a-592">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="5240a-593">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="5240a-594">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="5240a-595">*ng*와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5240a-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="5240a-596">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="5240a-597">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="5240a-598">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="5240a-599">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5240a-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="5240a-600">참조</span><span class="sxs-lookup"><span data-stu-id="5240a-600">See also</span></span>

- [<span data-ttu-id="5240a-601">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="5240a-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="5240a-602">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="5240a-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="5240a-603">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="5240a-603">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="5240a-604">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="5240a-604">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
