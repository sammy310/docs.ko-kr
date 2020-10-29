---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/01/2020
ms.openlocfilehash: 4a4c8e2806fee663b5f6aa255a6f24250a072a85
ms.sourcegitcommit: 532b03d5bbab764d63356193b04cd2281bc01239
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2020
ms.locfileid: "92526613"
---
# <a name="dotnet-new"></a><span data-ttu-id="fcdeb-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fcdeb-103">dotnet new</span></span>

<span data-ttu-id="fcdeb-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fcdeb-105">이름</span><span class="sxs-lookup"><span data-stu-id="fcdeb-105">Name</span></span>

<span data-ttu-id="fcdeb-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fcdeb-107">개요</span><span class="sxs-lookup"><span data-stu-id="fcdeb-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="fcdeb-108">설명</span><span class="sxs-lookup"><span data-stu-id="fcdeb-108">Description</span></span>

<span data-ttu-id="fcdeb-109">`dotnet new` 명령은 템플릿을 기반으로 .NET Core 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="fcdeb-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="fcdeb-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="fcdeb-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="fcdeb-112">인수</span><span class="sxs-lookup"><span data-stu-id="fcdeb-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="fcdeb-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="fcdeb-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="fcdeb-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="fcdeb-116">`dotnet new --list` 또는 `dotnet new -l`을 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="fcdeb-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="fcdeb-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="fcdeb-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="fcdeb-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="fcdeb-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="fcdeb-122">다음 표에는 .NET Core SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="fcdeb-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="fcdeb-124">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="fcdeb-125">템플릿</span><span class="sxs-lookup"><span data-stu-id="fcdeb-125">Templates</span></span>                                    | <span data-ttu-id="fcdeb-126">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="fcdeb-126">Short name</span></span>                      | <span data-ttu-id="fcdeb-127">언어</span><span class="sxs-lookup"><span data-stu-id="fcdeb-127">Language</span></span>     | <span data-ttu-id="fcdeb-128">Tags</span><span class="sxs-lookup"><span data-stu-id="fcdeb-128">Tags</span></span>                                  | <span data-ttu-id="fcdeb-129">도입</span><span class="sxs-lookup"><span data-stu-id="fcdeb-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="fcdeb-130">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="fcdeb-130">Console Application</span></span>                          | [<span data-ttu-id="fcdeb-131">콘솔</span><span class="sxs-lookup"><span data-stu-id="fcdeb-131">console</span></span>](#console)             | <span data-ttu-id="fcdeb-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-132">[C#], F#, VB</span></span> | <span data-ttu-id="fcdeb-133">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="fcdeb-133">Common/Console</span></span>                        | <span data-ttu-id="fcdeb-134">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-134">1.0</span></span>        |
| <span data-ttu-id="fcdeb-135">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-135">Class library</span></span>                                | [<span data-ttu-id="fcdeb-136">classlib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-136">classlib</span></span>](#classlib)           | <span data-ttu-id="fcdeb-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-137">[C#], F#, VB</span></span> | <span data-ttu-id="fcdeb-138">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-138">Common/Library</span></span>                        | <span data-ttu-id="fcdeb-139">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-139">1.0</span></span>        |
| <span data-ttu-id="fcdeb-140">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="fcdeb-140">WPF Application</span></span>                              | [<span data-ttu-id="fcdeb-141">wpf</span><span class="sxs-lookup"><span data-stu-id="fcdeb-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="fcdeb-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-142">[C#], VB</span></span>     | <span data-ttu-id="fcdeb-143">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="fcdeb-143">Common/WPF</span></span>                            | <span data-ttu-id="fcdeb-144">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fcdeb-145">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-145">WPF Class library</span></span>                            | [<span data-ttu-id="fcdeb-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="fcdeb-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-147">[C#], VB</span></span>     | <span data-ttu-id="fcdeb-148">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="fcdeb-148">Common/WPF</span></span>                            | <span data-ttu-id="fcdeb-149">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fcdeb-150">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="fcdeb-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="fcdeb-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-152">[C#], VB</span></span>     | <span data-ttu-id="fcdeb-153">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="fcdeb-153">Common/WPF</span></span>                            | <span data-ttu-id="fcdeb-154">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fcdeb-155">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="fcdeb-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="fcdeb-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-157">[C#], VB</span></span>     | <span data-ttu-id="fcdeb-158">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="fcdeb-158">Common/WPF</span></span>                            | <span data-ttu-id="fcdeb-159">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fcdeb-160">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="fcdeb-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="fcdeb-161">winforms</span><span class="sxs-lookup"><span data-stu-id="fcdeb-161">winforms</span></span>](#winforms)           | <span data-ttu-id="fcdeb-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-162">[C#], VB</span></span>     | <span data-ttu-id="fcdeb-163">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="fcdeb-163">Common/WinForms</span></span>                       | <span data-ttu-id="fcdeb-164">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fcdeb-165">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="fcdeb-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="fcdeb-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-167">[C#], VB</span></span>     | <span data-ttu-id="fcdeb-168">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="fcdeb-168">Common/WinForms</span></span>                       | <span data-ttu-id="fcdeb-169">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fcdeb-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="fcdeb-170">Worker Service</span></span>                               | [<span data-ttu-id="fcdeb-171">worker</span><span class="sxs-lookup"><span data-stu-id="fcdeb-171">worker</span></span>](#web-others)           | <span data-ttu-id="fcdeb-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-172">[C#]</span></span>         | <span data-ttu-id="fcdeb-173">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="fcdeb-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="fcdeb-174">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-174">3.0</span></span>        |
| <span data-ttu-id="fcdeb-175">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="fcdeb-175">Unit Test Project</span></span>                            | [<span data-ttu-id="fcdeb-176">mstest</span><span class="sxs-lookup"><span data-stu-id="fcdeb-176">mstest</span></span>](#test)                 | <span data-ttu-id="fcdeb-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-177">[C#], F#, VB</span></span> | <span data-ttu-id="fcdeb-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="fcdeb-178">Test/MSTest</span></span>                           | <span data-ttu-id="fcdeb-179">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-179">1.0</span></span>        |
| <span data-ttu-id="fcdeb-180">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="fcdeb-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="fcdeb-181">nunit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="fcdeb-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-182">[C#], F#, VB</span></span> | <span data-ttu-id="fcdeb-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-183">Test/NUnit</span></span>                            | <span data-ttu-id="fcdeb-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="fcdeb-184">2.1.400</span></span>    |
| <span data-ttu-id="fcdeb-185">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="fcdeb-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="fcdeb-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-186">[C#], F#, VB</span></span> | <span data-ttu-id="fcdeb-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-187">Test/NUnit</span></span>                            | <span data-ttu-id="fcdeb-188">2.2</span><span class="sxs-lookup"><span data-stu-id="fcdeb-188">2.2</span></span>        |
| <span data-ttu-id="fcdeb-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="fcdeb-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="fcdeb-190">xunit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-190">xunit</span></span>](#test)                  | <span data-ttu-id="fcdeb-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fcdeb-191">[C#], F#, VB</span></span> | <span data-ttu-id="fcdeb-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-192">Test/xUnit</span></span>                            | <span data-ttu-id="fcdeb-193">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-193">1.0</span></span>        |
| <span data-ttu-id="fcdeb-194">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fcdeb-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="fcdeb-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-195">[C#]</span></span>         | <span data-ttu-id="fcdeb-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fcdeb-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="fcdeb-197">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-197">3.0</span></span>        |
| <span data-ttu-id="fcdeb-198">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="fcdeb-198">Razor Page</span></span>                                   | [<span data-ttu-id="fcdeb-199">page</span><span class="sxs-lookup"><span data-stu-id="fcdeb-199">page</span></span>](#page)                   | <span data-ttu-id="fcdeb-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-200">[C#]</span></span>         | <span data-ttu-id="fcdeb-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fcdeb-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="fcdeb-202">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-202">2.0</span></span>        |
| <span data-ttu-id="fcdeb-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="fcdeb-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="fcdeb-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="fcdeb-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="fcdeb-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-205">[C#]</span></span>         | <span data-ttu-id="fcdeb-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fcdeb-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="fcdeb-207">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-207">2.0</span></span>        |
| <span data-ttu-id="fcdeb-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="fcdeb-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="fcdeb-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-209">[C#]</span></span>         | <span data-ttu-id="fcdeb-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fcdeb-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="fcdeb-211">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-211">2.0</span></span>        |
| <span data-ttu-id="fcdeb-212">:::no-loc(Blazor)::: 서버 앱</span><span class="sxs-lookup"><span data-stu-id="fcdeb-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="fcdeb-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="fcdeb-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="fcdeb-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-214">[C#]</span></span>         | <span data-ttu-id="fcdeb-215">Web/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="fcdeb-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="fcdeb-216">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-216">3.0</span></span>        |
| <span data-ttu-id="fcdeb-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: 앱</span><span class="sxs-lookup"><span data-stu-id="fcdeb-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="fcdeb-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-218">[C#]</span></span>         | <span data-ttu-id="fcdeb-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="fcdeb-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="fcdeb-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="fcdeb-220">3.1.300</span></span>    |
| <span data-ttu-id="fcdeb-221">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="fcdeb-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="fcdeb-222">web</span><span class="sxs-lookup"><span data-stu-id="fcdeb-222">web</span></span>](#web)                     | <span data-ttu-id="fcdeb-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fcdeb-223">[C#], F#</span></span>     | <span data-ttu-id="fcdeb-224">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="fcdeb-224">Web/Empty</span></span>                             | <span data-ttu-id="fcdeb-225">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-225">1.0</span></span>        |
| <span data-ttu-id="fcdeb-226">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="fcdeb-227">mvc</span><span class="sxs-lookup"><span data-stu-id="fcdeb-227">mvc</span></span>](#web-options)             | <span data-ttu-id="fcdeb-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fcdeb-228">[C#], F#</span></span>     | <span data-ttu-id="fcdeb-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="fcdeb-229">Web/MVC</span></span>                               | <span data-ttu-id="fcdeb-230">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-230">1.0</span></span>        |
| <span data-ttu-id="fcdeb-231">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="fcdeb-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="fcdeb-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="fcdeb-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="fcdeb-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-233">[C#]</span></span>         | <span data-ttu-id="fcdeb-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="fcdeb-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="fcdeb-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="fcdeb-236">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="fcdeb-237">angular</span><span class="sxs-lookup"><span data-stu-id="fcdeb-237">angular</span></span>](#spa)                 | <span data-ttu-id="fcdeb-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-238">[C#]</span></span>         | <span data-ttu-id="fcdeb-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="fcdeb-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="fcdeb-240">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-240">2.0</span></span>        |
| <span data-ttu-id="fcdeb-241">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="fcdeb-242">react</span><span class="sxs-lookup"><span data-stu-id="fcdeb-242">react</span></span>](#spa)                   | <span data-ttu-id="fcdeb-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-243">[C#]</span></span>         | <span data-ttu-id="fcdeb-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="fcdeb-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="fcdeb-245">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-245">2.0</span></span>        |
| <span data-ttu-id="fcdeb-246">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="fcdeb-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="fcdeb-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="fcdeb-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-248">[C#]</span></span>         | <span data-ttu-id="fcdeb-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="fcdeb-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="fcdeb-250">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-250">2.0</span></span>        |
| <span data-ttu-id="fcdeb-251">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-251">Razor Class Library</span></span>                          | [<span data-ttu-id="fcdeb-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="fcdeb-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-253">[C#]</span></span>         | <span data-ttu-id="fcdeb-254">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fcdeb-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="fcdeb-255">2.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-255">2.1</span></span>        |
| <span data-ttu-id="fcdeb-256">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="fcdeb-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="fcdeb-257">webapi</span><span class="sxs-lookup"><span data-stu-id="fcdeb-257">webapi</span></span>](#webapi)               | <span data-ttu-id="fcdeb-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fcdeb-258">[C#], F#</span></span>     | <span data-ttu-id="fcdeb-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="fcdeb-259">Web/WebAPI</span></span>                            | <span data-ttu-id="fcdeb-260">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-260">1.0</span></span>        |
| <span data-ttu-id="fcdeb-261">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="fcdeb-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="fcdeb-262">grpc</span><span class="sxs-lookup"><span data-stu-id="fcdeb-262">grpc</span></span>](#web-others)             | <span data-ttu-id="fcdeb-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="fcdeb-263">[C#]</span></span>         | <span data-ttu-id="fcdeb-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="fcdeb-264">Web/gRPC</span></span>                              | <span data-ttu-id="fcdeb-265">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-265">3.0</span></span>        |
| <span data-ttu-id="fcdeb-266">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="fcdeb-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="fcdeb-267">Config</span><span class="sxs-lookup"><span data-stu-id="fcdeb-267">Config</span></span>                                | <span data-ttu-id="fcdeb-268">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-268">3.0</span></span>        |
| <span data-ttu-id="fcdeb-269">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="fcdeb-269">global.json file</span></span>                             | [<span data-ttu-id="fcdeb-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="fcdeb-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="fcdeb-271">Config</span><span class="sxs-lookup"><span data-stu-id="fcdeb-271">Config</span></span>                                | <span data-ttu-id="fcdeb-272">2.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-272">2.0</span></span>        |
| <span data-ttu-id="fcdeb-273">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="fcdeb-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="fcdeb-274">Config</span><span class="sxs-lookup"><span data-stu-id="fcdeb-274">Config</span></span>                                | <span data-ttu-id="fcdeb-275">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-275">1.0</span></span>        |
| <span data-ttu-id="fcdeb-276">Dotnet 로컬 도구 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="fcdeb-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="fcdeb-277">Config</span><span class="sxs-lookup"><span data-stu-id="fcdeb-277">Config</span></span>                                | <span data-ttu-id="fcdeb-278">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-278">3.0</span></span>        |
| <span data-ttu-id="fcdeb-279">웹 구성</span><span class="sxs-lookup"><span data-stu-id="fcdeb-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="fcdeb-280">Config</span><span class="sxs-lookup"><span data-stu-id="fcdeb-280">Config</span></span>                                | <span data-ttu-id="fcdeb-281">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-281">1.0</span></span>        |
| <span data-ttu-id="fcdeb-282">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="fcdeb-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="fcdeb-283">솔루션</span><span class="sxs-lookup"><span data-stu-id="fcdeb-283">Solution</span></span>                              | <span data-ttu-id="fcdeb-284">1.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-284">1.0</span></span>        |
| <span data-ttu-id="fcdeb-285">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="fcdeb-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="fcdeb-286">proto</span><span class="sxs-lookup"><span data-stu-id="fcdeb-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="fcdeb-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="fcdeb-287">Web/gRPC</span></span>                              | <span data-ttu-id="fcdeb-288">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="fcdeb-289">옵션</span><span class="sxs-lookup"><span data-stu-id="fcdeb-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="fcdeb-290">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="fcdeb-291">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="fcdeb-292">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="fcdeb-293">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="fcdeb-294">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-294">Prints out help for the command.</span></span> <span data-ttu-id="fcdeb-295">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="fcdeb-296">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="fcdeb-297">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="fcdeb-298">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="fcdeb-299">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="fcdeb-300">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="fcdeb-301">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="fcdeb-302">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="fcdeb-303">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="fcdeb-304">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="fcdeb-305">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-305">The language of the template to create.</span></span> <span data-ttu-id="fcdeb-306">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="fcdeb-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="fcdeb-307">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fcdeb-308">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="fcdeb-309">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="fcdeb-310">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="fcdeb-311">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-311">The name for the created output.</span></span> <span data-ttu-id="fcdeb-312">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="fcdeb-313">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="fcdeb-314">.NET Core 2.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="fcdeb-315">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-315">Location to place the generated output.</span></span> <span data-ttu-id="fcdeb-316">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="fcdeb-317">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-317">Filters templates based on available types.</span></span> <span data-ttu-id="fcdeb-318">미리 정의된 값은 `project` 및 `item`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="fcdeb-319">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="fcdeb-320">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="fcdeb-321">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="fcdeb-322">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fcdeb-323">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="fcdeb-324">예를 들어 *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="fcdeb-325">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="fcdeb-326">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="fcdeb-327">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="fcdeb-328">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="fcdeb-329">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="fcdeb-330">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="fcdeb-330">Template options</span></span>

<span data-ttu-id="fcdeb-331">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-331">Each project template may have additional options available.</span></span> <span data-ttu-id="fcdeb-332">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="fcdeb-333">콘솔</span><span class="sxs-lookup"><span data-stu-id="fcdeb-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fcdeb-334">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-335">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="fcdeb-336">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-337">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-337">SDK version</span></span> | <span data-ttu-id="fcdeb-338">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-339">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-340">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="fcdeb-341">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fcdeb-342">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="fcdeb-343">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-343">Not supported for F#.</span></span> <span data-ttu-id="fcdeb-344">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fcdeb-345">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-346">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="fcdeb-347">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-347">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="fcdeb-348">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-348">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="fcdeb-349">classlib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-349">classlib</span></span>

- <span data-ttu-id="fcdeb-350">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-350">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fcdeb-351">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-351">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-352">값: `netcoreapp<version>`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="fcdeb-352">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="fcdeb-353">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-353">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="fcdeb-354">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-354">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fcdeb-355">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-355">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="fcdeb-356">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-356">Not supported for F#.</span></span> <span data-ttu-id="fcdeb-357">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-357">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fcdeb-358">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-358">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-359">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-359">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-360">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-360">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="fcdeb-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="fcdeb-362">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-362">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fcdeb-363">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-363">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-364">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-364">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="fcdeb-365">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-365">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="fcdeb-366">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-366">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fcdeb-367">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-367">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="fcdeb-368">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-368">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-369">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-369">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-370">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-370">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="fcdeb-371">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-371">winforms, winformslib</span></span>

- <span data-ttu-id="fcdeb-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="fcdeb-373">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-373">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fcdeb-374">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-374">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="fcdeb-375">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-375">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-376">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-376">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-377">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-377">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="fcdeb-378">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="fcdeb-378">worker, grpc</span></span>

- <span data-ttu-id="fcdeb-379">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-379">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fcdeb-380">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-380">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-381">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-381">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="fcdeb-382">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-382">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fcdeb-383">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-383">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-384">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-384">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-385">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-385">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="fcdeb-386">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-386">mstest, xunit</span></span>

- <span data-ttu-id="fcdeb-387">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-387">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fcdeb-388">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-389">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-389">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="fcdeb-390">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-390">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-391">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-391">SDK version</span></span> | <span data-ttu-id="fcdeb-392">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-392">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-393">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-393">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-394">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-394">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="fcdeb-395">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-395">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-396">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-396">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-397">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-397">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="fcdeb-398">nunit</span><span class="sxs-lookup"><span data-stu-id="fcdeb-398">nunit</span></span>

- <span data-ttu-id="fcdeb-399">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-399">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fcdeb-400">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-400">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="fcdeb-401">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-401">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-402">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-402">SDK version</span></span> | <span data-ttu-id="fcdeb-403">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-403">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-404">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-404">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-405">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-405">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fcdeb-406">2.2</span><span class="sxs-lookup"><span data-stu-id="fcdeb-406">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="fcdeb-407">2.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-407">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="fcdeb-408">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-408">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-409">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-409">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-410">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-410">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="fcdeb-411">페이지</span><span class="sxs-lookup"><span data-stu-id="fcdeb-411">page</span></span>

- <span data-ttu-id="fcdeb-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="fcdeb-413">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-413">Namespace for the generated code.</span></span> <span data-ttu-id="fcdeb-414">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-414">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="fcdeb-415">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-415">Creates the page without a PageModel.</span></span>

<span data-ttu-id="fcdeb-416">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-416">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="fcdeb-417">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="fcdeb-417">viewimports, proto</span></span>

- <span data-ttu-id="fcdeb-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="fcdeb-419">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-419">Namespace for the generated code.</span></span> <span data-ttu-id="fcdeb-420">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-420">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="fcdeb-421">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-421">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="fcdeb-422">blazorserver</span><span class="sxs-lookup"><span data-stu-id="fcdeb-422">blazorserver</span></span>

- <span data-ttu-id="fcdeb-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fcdeb-424">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-424">The type of authentication to use.</span></span> <span data-ttu-id="fcdeb-425">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-425">The possible values are:</span></span>

  - <span data-ttu-id="fcdeb-426">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="fcdeb-426">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fcdeb-427">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-427">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="fcdeb-428">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-428">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fcdeb-429">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-429">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="fcdeb-430">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-430">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="fcdeb-431">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-431">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fcdeb-432">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-432">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fcdeb-433">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-433">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-434">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-434">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fcdeb-435">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-435">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fcdeb-436">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-436">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="fcdeb-437">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-437">The reset password policy ID for this project.</span></span> <span data-ttu-id="fcdeb-438">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-438">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="fcdeb-439">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-439">The edit profile policy ID for this project.</span></span> <span data-ttu-id="fcdeb-440">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-440">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fcdeb-441">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-441">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fcdeb-442">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-442">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="fcdeb-443">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-443">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fcdeb-444">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-444">The Client ID for this project.</span></span> <span data-ttu-id="fcdeb-445">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-445">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="fcdeb-446">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-446">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fcdeb-447">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-447">The domain for the directory tenant.</span></span> <span data-ttu-id="fcdeb-448">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-448">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-449">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-449">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fcdeb-450">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-450">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fcdeb-451">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-451">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fcdeb-452">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-452">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="fcdeb-453">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-453">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="fcdeb-454">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-454">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-455">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-455">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fcdeb-456">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-456">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fcdeb-457">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-457">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fcdeb-458">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-458">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="fcdeb-459">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-459">Turns off HTTPS.</span></span> <span data-ttu-id="fcdeb-460">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-460">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fcdeb-461">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-461">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fcdeb-462">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-462">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-463">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-463">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-464">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-464">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="fcdeb-465">web</span><span class="sxs-lookup"><span data-stu-id="fcdeb-465">web</span></span>

- <span data-ttu-id="fcdeb-466">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-466">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="fcdeb-467">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-467">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fcdeb-468">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-469">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-469">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fcdeb-470">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-470">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-471">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-471">SDK version</span></span> | <span data-ttu-id="fcdeb-472">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-472">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-473">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-473">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-474">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-474">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fcdeb-475">2.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-475">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="fcdeb-476">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="fcdeb-477">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-477">Turns off HTTPS.</span></span>

<span data-ttu-id="fcdeb-478">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-478">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="fcdeb-479">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="fcdeb-479">mvc, webapp</span></span>

- <span data-ttu-id="fcdeb-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fcdeb-481">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-481">The type of authentication to use.</span></span> <span data-ttu-id="fcdeb-482">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-482">The possible values are:</span></span>

  - <span data-ttu-id="fcdeb-483">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="fcdeb-483">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fcdeb-484">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-484">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="fcdeb-485">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-485">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fcdeb-486">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-486">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="fcdeb-487">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-487">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="fcdeb-488">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-488">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fcdeb-489">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-489">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fcdeb-490">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-490">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-491">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-491">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fcdeb-492">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-492">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fcdeb-493">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-493">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="fcdeb-494">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-494">The reset password policy ID for this project.</span></span> <span data-ttu-id="fcdeb-495">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-495">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="fcdeb-496">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-496">The edit profile policy ID for this project.</span></span> <span data-ttu-id="fcdeb-497">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-497">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fcdeb-498">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-498">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fcdeb-499">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-499">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="fcdeb-500">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-500">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fcdeb-501">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-501">The Client ID for this project.</span></span> <span data-ttu-id="fcdeb-502">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-502">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="fcdeb-503">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-503">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fcdeb-504">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-504">The domain for the directory tenant.</span></span> <span data-ttu-id="fcdeb-505">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-506">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-506">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fcdeb-507">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-507">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fcdeb-508">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-508">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fcdeb-509">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-509">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="fcdeb-510">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-510">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="fcdeb-511">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-511">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-512">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-512">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fcdeb-513">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fcdeb-514">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-514">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fcdeb-515">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="fcdeb-516">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-516">Turns off HTTPS.</span></span> <span data-ttu-id="fcdeb-517">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-517">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fcdeb-518">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fcdeb-519">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fcdeb-520">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-521">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-521">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="fcdeb-522">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-523">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-523">SDK version</span></span> | <span data-ttu-id="fcdeb-524">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-525">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-526">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-526">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="fcdeb-527">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-527">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="fcdeb-528">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-528">Includes BrowserLink in the project.</span></span> <span data-ttu-id="fcdeb-529">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-529">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="fcdeb-530">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-530">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="fcdeb-531">.NET Core 3.1.201 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-531">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="fcdeb-532">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-532">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="fcdeb-533">angular, react</span><span class="sxs-lookup"><span data-stu-id="fcdeb-533">angular, react</span></span>

- <span data-ttu-id="fcdeb-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fcdeb-535">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-535">The type of authentication to use.</span></span> <span data-ttu-id="fcdeb-536">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-536">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="fcdeb-537">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-537">The possible values are:</span></span>

  - <span data-ttu-id="fcdeb-538">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="fcdeb-538">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fcdeb-539">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-539">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fcdeb-540">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-540">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fcdeb-541">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="fcdeb-542">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-542">Turns off HTTPS.</span></span> <span data-ttu-id="fcdeb-543">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-543">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fcdeb-544">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-544">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fcdeb-545">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-545">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-546">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-546">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fcdeb-547">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-547">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-548">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-548">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fcdeb-549">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-549">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-550">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-550">SDK version</span></span> | <span data-ttu-id="fcdeb-551">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-551">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-552">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-552">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-553">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-553">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fcdeb-554">2.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-554">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="fcdeb-555">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-555">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="fcdeb-556">reactredux</span><span class="sxs-lookup"><span data-stu-id="fcdeb-556">reactredux</span></span>

- <span data-ttu-id="fcdeb-557">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-557">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="fcdeb-558">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-558">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fcdeb-559">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-559">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-560">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-560">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fcdeb-561">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-561">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-562">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-562">SDK version</span></span> | <span data-ttu-id="fcdeb-563">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-563">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-564">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-564">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-565">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-565">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fcdeb-566">2.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-566">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="fcdeb-567">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-567">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="fcdeb-568">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-568">Turns off HTTPS.</span></span>

<span data-ttu-id="fcdeb-569">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-569">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="fcdeb-570">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="fcdeb-570">razorclasslib</span></span>

- <span data-ttu-id="fcdeb-571">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-571">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="fcdeb-572">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-572">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="fcdeb-573">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-573">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="fcdeb-574">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-574">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="fcdeb-575">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-575">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="fcdeb-576">webapi</span><span class="sxs-lookup"><span data-stu-id="fcdeb-576">webapi</span></span>

- <span data-ttu-id="fcdeb-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fcdeb-578">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-578">The type of authentication to use.</span></span> <span data-ttu-id="fcdeb-579">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-579">The possible values are:</span></span>

  - <span data-ttu-id="fcdeb-580">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="fcdeb-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fcdeb-581">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fcdeb-582">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="fcdeb-583">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fcdeb-584">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fcdeb-585">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fcdeb-586">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fcdeb-587">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fcdeb-588">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fcdeb-589">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fcdeb-590">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fcdeb-591">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fcdeb-592">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-592">The Client ID for this project.</span></span> <span data-ttu-id="fcdeb-593">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="fcdeb-594">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fcdeb-595">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-595">The domain for the directory tenant.</span></span> <span data-ttu-id="fcdeb-596">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="fcdeb-597">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fcdeb-598">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fcdeb-599">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fcdeb-600">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fcdeb-601">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fcdeb-602">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fcdeb-603">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="fcdeb-604">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-604">Turns off HTTPS.</span></span> <span data-ttu-id="fcdeb-605">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="fcdeb-606">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fcdeb-607">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fcdeb-608">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fcdeb-609">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fcdeb-610">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fcdeb-611">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fcdeb-612">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="fcdeb-612">SDK version</span></span> | <span data-ttu-id="fcdeb-613">기본값</span><span class="sxs-lookup"><span data-stu-id="fcdeb-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fcdeb-614">3.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-614">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fcdeb-615">3.0</span><span class="sxs-lookup"><span data-stu-id="fcdeb-615">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fcdeb-616">2.1</span><span class="sxs-lookup"><span data-stu-id="fcdeb-616">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="fcdeb-617">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-617">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fcdeb-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fcdeb-618">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="fcdeb-619">globaljson</span><span class="sxs-lookup"><span data-stu-id="fcdeb-619">globaljson</span></span>

- <span data-ttu-id="fcdeb-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="fcdeb-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="fcdeb-621">*global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-621">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="fcdeb-622">예</span><span class="sxs-lookup"><span data-stu-id="fcdeb-622">Examples</span></span>

- <span data-ttu-id="fcdeb-623">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-623">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="fcdeb-624">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-624">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="fcdeb-625">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-625">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="fcdeb-626">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-626">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="fcdeb-627">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-627">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="fcdeb-628">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-628">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="fcdeb-629">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-629">List all templates matching the *we* substring.</span></span> <span data-ttu-id="fcdeb-630">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-630">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="fcdeb-631">*ng* 와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-631">Attempt to invoke the template matching *ng* .</span></span> <span data-ttu-id="fcdeb-632">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-632">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="fcdeb-633">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-633">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="fcdeb-634">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-634">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="fcdeb-635">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json* 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdeb-635">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="fcdeb-636">참조</span><span class="sxs-lookup"><span data-stu-id="fcdeb-636">See also</span></span>

- [<span data-ttu-id="fcdeb-637">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="fcdeb-637">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="fcdeb-638">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="fcdeb-638">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="fcdeb-639">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-639">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="fcdeb-640">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="fcdeb-640">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
