---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET 프로젝트를 만듭니다.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634457"
---
# <a name="dotnet-new"></a><span data-ttu-id="03079-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="03079-103">dotnet new</span></span>

<span data-ttu-id="03079-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="03079-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="03079-105">이름</span><span class="sxs-lookup"><span data-stu-id="03079-105">Name</span></span>

<span data-ttu-id="03079-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="03079-107">개요</span><span class="sxs-lookup"><span data-stu-id="03079-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="03079-108">설명</span><span class="sxs-lookup"><span data-stu-id="03079-108">Description</span></span>

<span data-ttu-id="03079-109">`dotnet new` 명령은 템플릿을 기반으로 .NET 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="03079-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="03079-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="03079-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="03079-112">인수</span><span class="sxs-lookup"><span data-stu-id="03079-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="03079-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="03079-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="03079-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="03079-116">`dotnet new --list` 또는 `dotnet new -l`을 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="03079-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="03079-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="03079-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="03079-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="03079-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="03079-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="03079-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="03079-122">다음 표에는 .NET SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="03079-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="03079-124">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="03079-125">템플릿</span><span class="sxs-lookup"><span data-stu-id="03079-125">Templates</span></span>                                    | <span data-ttu-id="03079-126">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="03079-126">Short name</span></span>                      | <span data-ttu-id="03079-127">언어</span><span class="sxs-lookup"><span data-stu-id="03079-127">Language</span></span>     | <span data-ttu-id="03079-128">Tags</span><span class="sxs-lookup"><span data-stu-id="03079-128">Tags</span></span>                                  | <span data-ttu-id="03079-129">도입</span><span class="sxs-lookup"><span data-stu-id="03079-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="03079-130">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="03079-130">Console Application</span></span>                          | [<span data-ttu-id="03079-131">콘솔</span><span class="sxs-lookup"><span data-stu-id="03079-131">console</span></span>](#console)             | <span data-ttu-id="03079-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="03079-132">[C#], F#, VB</span></span> | <span data-ttu-id="03079-133">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="03079-133">Common/Console</span></span>                        | <span data-ttu-id="03079-134">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-134">1.0</span></span>        |
| <span data-ttu-id="03079-135">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-135">Class library</span></span>                                | [<span data-ttu-id="03079-136">classlib</span><span class="sxs-lookup"><span data-stu-id="03079-136">classlib</span></span>](#classlib)           | <span data-ttu-id="03079-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="03079-137">[C#], F#, VB</span></span> | <span data-ttu-id="03079-138">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-138">Common/Library</span></span>                        | <span data-ttu-id="03079-139">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-139">1.0</span></span>        |
| <span data-ttu-id="03079-140">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="03079-140">WPF Application</span></span>                              | [<span data-ttu-id="03079-141">wpf</span><span class="sxs-lookup"><span data-stu-id="03079-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="03079-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="03079-142">[C#], VB</span></span>     | <span data-ttu-id="03079-143">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="03079-143">Common/WPF</span></span>                            | <span data-ttu-id="03079-144">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="03079-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="03079-145">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-145">WPF Class library</span></span>                            | [<span data-ttu-id="03079-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="03079-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="03079-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="03079-147">[C#], VB</span></span>     | <span data-ttu-id="03079-148">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="03079-148">Common/WPF</span></span>                            | <span data-ttu-id="03079-149">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="03079-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="03079-150">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="03079-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="03079-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="03079-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="03079-152">[C#], VB</span></span>     | <span data-ttu-id="03079-153">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="03079-153">Common/WPF</span></span>                            | <span data-ttu-id="03079-154">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="03079-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="03079-155">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="03079-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="03079-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="03079-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="03079-157">[C#], VB</span></span>     | <span data-ttu-id="03079-158">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="03079-158">Common/WPF</span></span>                            | <span data-ttu-id="03079-159">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="03079-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="03079-160">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="03079-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="03079-161">winforms</span><span class="sxs-lookup"><span data-stu-id="03079-161">winforms</span></span>](#winforms)           | <span data-ttu-id="03079-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="03079-162">[C#], VB</span></span>     | <span data-ttu-id="03079-163">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="03079-163">Common/WinForms</span></span>                       | <span data-ttu-id="03079-164">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="03079-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="03079-165">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="03079-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="03079-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="03079-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="03079-167">[C#], VB</span></span>     | <span data-ttu-id="03079-168">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="03079-168">Common/WinForms</span></span>                       | <span data-ttu-id="03079-169">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="03079-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="03079-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="03079-170">Worker Service</span></span>                               | [<span data-ttu-id="03079-171">worker</span><span class="sxs-lookup"><span data-stu-id="03079-171">worker</span></span>](#web-others)           | <span data-ttu-id="03079-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-172">[C#]</span></span>         | <span data-ttu-id="03079-173">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="03079-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="03079-174">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-174">3.0</span></span>        |
| <span data-ttu-id="03079-175">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="03079-175">Unit Test Project</span></span>                            | [<span data-ttu-id="03079-176">mstest</span><span class="sxs-lookup"><span data-stu-id="03079-176">mstest</span></span>](#test)                 | <span data-ttu-id="03079-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="03079-177">[C#], F#, VB</span></span> | <span data-ttu-id="03079-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="03079-178">Test/MSTest</span></span>                           | <span data-ttu-id="03079-179">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-179">1.0</span></span>        |
| <span data-ttu-id="03079-180">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="03079-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="03079-181">nunit</span><span class="sxs-lookup"><span data-stu-id="03079-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="03079-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="03079-182">[C#], F#, VB</span></span> | <span data-ttu-id="03079-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="03079-183">Test/NUnit</span></span>                            | <span data-ttu-id="03079-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="03079-184">2.1.400</span></span>    |
| <span data-ttu-id="03079-185">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="03079-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="03079-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="03079-186">[C#], F#, VB</span></span> | <span data-ttu-id="03079-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="03079-187">Test/NUnit</span></span>                            | <span data-ttu-id="03079-188">2.2</span><span class="sxs-lookup"><span data-stu-id="03079-188">2.2</span></span>        |
| <span data-ttu-id="03079-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="03079-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="03079-190">xunit</span><span class="sxs-lookup"><span data-stu-id="03079-190">xunit</span></span>](#test)                  | <span data-ttu-id="03079-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="03079-191">[C#], F#, VB</span></span> | <span data-ttu-id="03079-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="03079-192">Test/xUnit</span></span>                            | <span data-ttu-id="03079-193">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-193">1.0</span></span>        |
| <span data-ttu-id="03079-194">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="03079-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="03079-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-195">[C#]</span></span>         | <span data-ttu-id="03079-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="03079-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="03079-197">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-197">3.0</span></span>        |
| <span data-ttu-id="03079-198">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="03079-198">Razor Page</span></span>                                   | [<span data-ttu-id="03079-199">page</span><span class="sxs-lookup"><span data-stu-id="03079-199">page</span></span>](#page)                   | <span data-ttu-id="03079-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-200">[C#]</span></span>         | <span data-ttu-id="03079-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="03079-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="03079-202">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-202">2.0</span></span>        |
| <span data-ttu-id="03079-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="03079-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="03079-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="03079-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="03079-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-205">[C#]</span></span>         | <span data-ttu-id="03079-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="03079-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="03079-207">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-207">2.0</span></span>        |
| <span data-ttu-id="03079-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="03079-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="03079-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-209">[C#]</span></span>         | <span data-ttu-id="03079-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="03079-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="03079-211">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-211">2.0</span></span>        |
| <span data-ttu-id="03079-212">Blazor 서버 앱</span><span class="sxs-lookup"><span data-stu-id="03079-212">Blazor Server App</span></span>                            | [<span data-ttu-id="03079-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="03079-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="03079-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-214">[C#]</span></span>         | <span data-ttu-id="03079-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="03079-215">Web/Blazor</span></span>                            | <span data-ttu-id="03079-216">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-216">3.0</span></span>        |
| <span data-ttu-id="03079-217">Blazor WebAssembly 앱</span><span class="sxs-lookup"><span data-stu-id="03079-217">Blazor WebAssembly App</span></span>                       | [<span data-ttu-id="03079-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="03079-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="03079-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-219">[C#]</span></span>         | <span data-ttu-id="03079-220">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="03079-220">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="03079-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="03079-221">3.1.300</span></span>    |
| <span data-ttu-id="03079-222">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="03079-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="03079-223">web</span><span class="sxs-lookup"><span data-stu-id="03079-223">web</span></span>](#web)                     | <span data-ttu-id="03079-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="03079-224">[C#], F#</span></span>     | <span data-ttu-id="03079-225">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="03079-225">Web/Empty</span></span>                             | <span data-ttu-id="03079-226">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-226">1.0</span></span>        |
| <span data-ttu-id="03079-227">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="03079-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="03079-228">mvc</span><span class="sxs-lookup"><span data-stu-id="03079-228">mvc</span></span>](#web-options)             | <span data-ttu-id="03079-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="03079-229">[C#], F#</span></span>     | <span data-ttu-id="03079-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="03079-230">Web/MVC</span></span>                               | <span data-ttu-id="03079-231">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-231">1.0</span></span>        |
| <span data-ttu-id="03079-232">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="03079-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="03079-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="03079-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="03079-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-234">[C#]</span></span>         | <span data-ttu-id="03079-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="03079-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="03079-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="03079-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="03079-237">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="03079-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="03079-238">angular</span><span class="sxs-lookup"><span data-stu-id="03079-238">angular</span></span>](#spa)                 | <span data-ttu-id="03079-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-239">[C#]</span></span>         | <span data-ttu-id="03079-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="03079-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="03079-241">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-241">2.0</span></span>        |
| <span data-ttu-id="03079-242">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="03079-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="03079-243">react</span><span class="sxs-lookup"><span data-stu-id="03079-243">react</span></span>](#spa)                   | <span data-ttu-id="03079-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-244">[C#]</span></span>         | <span data-ttu-id="03079-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="03079-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="03079-246">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-246">2.0</span></span>        |
| <span data-ttu-id="03079-247">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="03079-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="03079-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="03079-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="03079-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-249">[C#]</span></span>         | <span data-ttu-id="03079-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="03079-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="03079-251">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-251">2.0</span></span>        |
| <span data-ttu-id="03079-252">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-252">Razor Class Library</span></span>                          | [<span data-ttu-id="03079-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="03079-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="03079-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-254">[C#]</span></span>         | <span data-ttu-id="03079-255">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="03079-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="03079-256">2.1</span><span class="sxs-lookup"><span data-stu-id="03079-256">2.1</span></span>        |
| <span data-ttu-id="03079-257">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="03079-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="03079-258">webapi</span><span class="sxs-lookup"><span data-stu-id="03079-258">webapi</span></span>](#webapi)               | <span data-ttu-id="03079-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="03079-259">[C#], F#</span></span>     | <span data-ttu-id="03079-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="03079-260">Web/WebAPI</span></span>                            | <span data-ttu-id="03079-261">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-261">1.0</span></span>        |
| <span data-ttu-id="03079-262">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="03079-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="03079-263">grpc</span><span class="sxs-lookup"><span data-stu-id="03079-263">grpc</span></span>](#web-others)             | <span data-ttu-id="03079-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="03079-264">[C#]</span></span>         | <span data-ttu-id="03079-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="03079-265">Web/gRPC</span></span>                              | <span data-ttu-id="03079-266">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-266">3.0</span></span>        |
| <span data-ttu-id="03079-267">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="03079-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="03079-268">Config</span><span class="sxs-lookup"><span data-stu-id="03079-268">Config</span></span>                                | <span data-ttu-id="03079-269">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-269">3.0</span></span>        |
| <span data-ttu-id="03079-270">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="03079-270">global.json file</span></span>                             | [<span data-ttu-id="03079-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="03079-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="03079-272">Config</span><span class="sxs-lookup"><span data-stu-id="03079-272">Config</span></span>                                | <span data-ttu-id="03079-273">2.0</span><span class="sxs-lookup"><span data-stu-id="03079-273">2.0</span></span>        |
| <span data-ttu-id="03079-274">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="03079-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="03079-275">Config</span><span class="sxs-lookup"><span data-stu-id="03079-275">Config</span></span>                                | <span data-ttu-id="03079-276">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-276">1.0</span></span>        |
| <span data-ttu-id="03079-277">Dotnet 로컬 도구 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="03079-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="03079-278">Config</span><span class="sxs-lookup"><span data-stu-id="03079-278">Config</span></span>                                | <span data-ttu-id="03079-279">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-279">3.0</span></span>        |
| <span data-ttu-id="03079-280">웹 구성</span><span class="sxs-lookup"><span data-stu-id="03079-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="03079-281">Config</span><span class="sxs-lookup"><span data-stu-id="03079-281">Config</span></span>                                | <span data-ttu-id="03079-282">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-282">1.0</span></span>        |
| <span data-ttu-id="03079-283">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="03079-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="03079-284">솔루션</span><span class="sxs-lookup"><span data-stu-id="03079-284">Solution</span></span>                              | <span data-ttu-id="03079-285">1.0</span><span class="sxs-lookup"><span data-stu-id="03079-285">1.0</span></span>        |
| <span data-ttu-id="03079-286">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="03079-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="03079-287">proto</span><span class="sxs-lookup"><span data-stu-id="03079-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="03079-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="03079-288">Web/gRPC</span></span>                              | <span data-ttu-id="03079-289">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="03079-290">옵션</span><span class="sxs-lookup"><span data-stu-id="03079-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="03079-291">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="03079-292">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="03079-293">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="03079-294">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="03079-295">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-295">Prints out help for the command.</span></span> <span data-ttu-id="03079-296">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="03079-297">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="03079-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="03079-298">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="03079-299">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="03079-300">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="03079-301">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="03079-302">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="03079-303">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="03079-304">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="03079-305">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="03079-306">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-306">The language of the template to create.</span></span> <span data-ttu-id="03079-307">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="03079-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="03079-308">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="03079-309">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="03079-310">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="03079-311">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="03079-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="03079-312">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-312">The name for the created output.</span></span> <span data-ttu-id="03079-313">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="03079-314">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-314">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="03079-315">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-315">Location to place the generated output.</span></span> <span data-ttu-id="03079-316">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="03079-317">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-317">Filters templates based on available types.</span></span> <span data-ttu-id="03079-318">미리 정의된 값은 `project` 및 `item`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="03079-319">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="03079-320">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="03079-321">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="03079-322">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="03079-323">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="03079-324">예를 들어 *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="03079-325">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="03079-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="03079-326">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="03079-327">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="03079-328">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="03079-329">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="03079-330">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="03079-330">Template options</span></span>

<span data-ttu-id="03079-331">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-331">Each project template may have additional options available.</span></span> <span data-ttu-id="03079-332">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="03079-333">콘솔</span><span class="sxs-lookup"><span data-stu-id="03079-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03079-334">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-335">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="03079-336">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-337">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-337">SDK version</span></span> | <span data-ttu-id="03079-338">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-339">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-339">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-340">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-341">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="03079-342">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="03079-343">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="03079-344">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-344">Not supported for F#.</span></span> <span data-ttu-id="03079-345">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="03079-346">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-347">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="03079-348">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="03079-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="03079-350">classlib</span><span class="sxs-lookup"><span data-stu-id="03079-350">classlib</span></span>

- <span data-ttu-id="03079-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="03079-352">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-353">값: `net5.0`, `netcoreapp<version>`(.NET 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="03079-353">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="03079-354">.NET 5.0 SDK의 기본값은 `net5.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-354">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="03079-355">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="03079-356">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="03079-357">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-357">Not supported for F#.</span></span> <span data-ttu-id="03079-358">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="03079-359">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-360">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="03079-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="03079-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="03079-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="03079-364">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-365">기본값은 `net5.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-365">The default value is `net5.0`.</span></span> <span data-ttu-id="03079-366">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="03079-367">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="03079-368">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="03079-369">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-370">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="03079-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="03079-372">winforms, winformslib</span></span>

- <span data-ttu-id="03079-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="03079-374">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="03079-375">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="03079-376">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03079-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-377">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="03079-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="03079-379">worker, grpc</span></span>

- <span data-ttu-id="03079-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="03079-381">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-382">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="03079-383">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="03079-384">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-385">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="03079-387">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="03079-387">mstest, xunit</span></span>

- <span data-ttu-id="03079-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="03079-389">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-390">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="03079-391">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-392">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-392">SDK version</span></span> | <span data-ttu-id="03079-393">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-394">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-394">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-395">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-395">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-396">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-396">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="03079-397">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-397">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-398">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-398">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-399">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-399">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="03079-400">nunit</span><span class="sxs-lookup"><span data-stu-id="03079-400">nunit</span></span>

- <span data-ttu-id="03079-401">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-401">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="03079-402">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-402">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="03079-403">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-403">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-404">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-404">SDK version</span></span> | <span data-ttu-id="03079-405">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-405">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-406">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-406">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-407">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-407">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-408">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-408">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="03079-409">2.2</span><span class="sxs-lookup"><span data-stu-id="03079-409">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="03079-410">2.1</span><span class="sxs-lookup"><span data-stu-id="03079-410">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="03079-411">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-411">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-412">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-412">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-413">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-413">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="03079-414">페이지</span><span class="sxs-lookup"><span data-stu-id="03079-414">page</span></span>

- <span data-ttu-id="03079-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="03079-416">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-416">Namespace for the generated code.</span></span> <span data-ttu-id="03079-417">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-417">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="03079-418">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-418">Creates the page without a PageModel.</span></span>

<span data-ttu-id="03079-419">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-419">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="03079-420">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="03079-420">viewimports, proto</span></span>

- <span data-ttu-id="03079-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="03079-422">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-422">Namespace for the generated code.</span></span> <span data-ttu-id="03079-423">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-423">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="03079-424">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-424">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="03079-425">blazorserver</span><span class="sxs-lookup"><span data-stu-id="03079-425">blazorserver</span></span>

- <span data-ttu-id="03079-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="03079-427">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-427">The type of authentication to use.</span></span> <span data-ttu-id="03079-428">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-428">The possible values are:</span></span>

  - <span data-ttu-id="03079-429">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="03079-429">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="03079-430">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-430">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="03079-431">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-431">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="03079-432">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-432">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="03079-433">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-433">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="03079-434">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-434">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="03079-435">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-435">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="03079-436">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-436">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-437">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-437">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="03079-438">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-438">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="03079-439">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-439">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="03079-440">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-440">The reset password policy ID for this project.</span></span> <span data-ttu-id="03079-441">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-441">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="03079-442">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-442">The edit profile policy ID for this project.</span></span> <span data-ttu-id="03079-443">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-443">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="03079-444">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-444">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="03079-445">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-445">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="03079-446">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-446">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="03079-447">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-447">The Client ID for this project.</span></span> <span data-ttu-id="03079-448">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-448">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="03079-449">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-449">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="03079-450">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-450">The domain for the directory tenant.</span></span> <span data-ttu-id="03079-451">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-451">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-452">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-452">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="03079-453">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-453">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="03079-454">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-454">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-455">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-455">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="03079-456">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-456">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="03079-457">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-457">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-458">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-458">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="03079-459">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-459">Allows this application read-access to the directory.</span></span> <span data-ttu-id="03079-460">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-460">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="03079-461">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-461">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-462">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-462">Turns off HTTPS.</span></span> <span data-ttu-id="03079-463">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-463">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="03079-464">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-464">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="03079-465">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-465">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-466">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-466">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-467">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-467">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="03079-468">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="03079-468">blazorwasm</span></span>

- <span data-ttu-id="03079-469">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-469">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="03079-470">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-470">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="03079-471">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-471">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-472">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-472">SDK version</span></span> | <span data-ttu-id="03079-473">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-473">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-474">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-474">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-475">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-475">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="03079-476">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="03079-477">Blazor WebAssembly 앱의 ASP.NET Core 호스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-477">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="03079-478">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-478">The type of authentication to use.</span></span> <span data-ttu-id="03079-479">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-479">The possible values are:</span></span>

  - <span data-ttu-id="03079-480">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="03079-480">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="03079-481">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-481">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="03079-482">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-482">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="03079-483">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-483">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="03079-484">OIDC 공급자의 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-484">The authority of the OIDC provider.</span></span> <span data-ttu-id="03079-485">`Individual` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-485">Use with `Individual` authentication.</span></span> <span data-ttu-id="03079-486">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-486">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="03079-487">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-487">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="03079-488">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-488">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-489">기본값은 `https://aadB2CInstance.b2clogin.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-489">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="03079-490">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-490">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="03079-491">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-491">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="03079-492">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-492">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="03079-493">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-493">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-494">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-494">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="03079-495">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-495">The Client ID for this project.</span></span> <span data-ttu-id="03079-496">`IndividualB2C`, `SingleOrg` 또는 독립 실행형 시나리오의 경우 `Individual` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-496">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="03079-497">기본값은 `33333333-3333-3333-33333333333333333`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-497">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="03079-498">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-498">The domain for the directory tenant.</span></span> <span data-ttu-id="03079-499">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-499">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-500">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-500">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="03079-501">호출하려는 서버 API의 앱 ID URI입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-501">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="03079-502">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-502">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-503">기본값은 `api.id.uri`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-503">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="03079-504">서버가 호스트하는 API의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-504">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="03079-505">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-506">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-506">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="03079-507">클라이언트가 액세스 토큰 프로비전을 요청하는 데 필요한 API 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-507">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="03079-508">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-508">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-509">기본값은 `user_impersonation`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-509">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="03079-510">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-510">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="03079-511">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-511">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-512">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-512">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="03079-513">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="03079-514">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-514">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="03079-515">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="03079-516">프로그레시브 웹 애플리케이션(PWA)을 생성하여 설치 및 오프라인 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-516">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-517">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-517">Turns off HTTPS.</span></span> <span data-ttu-id="03079-518">이 옵션은 `--auth`에 `Individual`, `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-518">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="03079-519">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-519">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="03079-520">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-520">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="03079-521">웹앱에서 호출할 API의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-521">URL of the API to call from the web app.</span></span> <span data-ttu-id="03079-522">ASP.NET Core 호스트가 지정되지 않은 `SingleOrg` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-522">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="03079-523">기본값은 `https://graph.microsoft.com/v1.0/me`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-523">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="03079-524">웹앱이 Microsoft Graph를 호출하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-524">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="03079-525">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-525">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="03079-526">웹앱에서 API를 호출하기 위해 요청할 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-526">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="03079-527">ASP.NET Core 호스트가 지정되지 않은 `SingleOrg` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-527">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="03079-528">기본값은 `user.read`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-528">The default is `user.read`.</span></span>

<span data-ttu-id="03079-529">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-529">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="03079-530">web</span><span class="sxs-lookup"><span data-stu-id="03079-530">web</span></span>

- <span data-ttu-id="03079-531">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-531">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="03079-532">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03079-533">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-534">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="03079-535">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-536">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-536">SDK version</span></span> | <span data-ttu-id="03079-537">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-538">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-538">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-539">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-539">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-540">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-540">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="03079-541">2.1</span><span class="sxs-lookup"><span data-stu-id="03079-541">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="03079-542">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-543">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-543">Turns off HTTPS.</span></span>

<span data-ttu-id="03079-544">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-544">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="03079-545">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="03079-545">mvc, webapp</span></span>

- <span data-ttu-id="03079-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="03079-547">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-547">The type of authentication to use.</span></span> <span data-ttu-id="03079-548">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-548">The possible values are:</span></span>

  - <span data-ttu-id="03079-549">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="03079-549">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="03079-550">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-550">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="03079-551">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="03079-552">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="03079-553">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-553">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="03079-554">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-554">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="03079-555">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-555">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="03079-556">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-556">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-557">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-557">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="03079-558">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-558">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="03079-559">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-559">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="03079-560">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-560">The reset password policy ID for this project.</span></span> <span data-ttu-id="03079-561">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-561">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="03079-562">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-562">The edit profile policy ID for this project.</span></span> <span data-ttu-id="03079-563">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-563">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="03079-564">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-564">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="03079-565">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-565">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="03079-566">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-566">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="03079-567">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-567">The Client ID for this project.</span></span> <span data-ttu-id="03079-568">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-568">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="03079-569">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-569">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="03079-570">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-570">The domain for the directory tenant.</span></span> <span data-ttu-id="03079-571">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-571">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-572">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-572">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="03079-573">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-573">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="03079-574">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-574">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-575">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-575">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="03079-576">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-576">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="03079-577">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-577">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-578">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-578">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="03079-579">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-579">Allows this application read-access to the directory.</span></span> <span data-ttu-id="03079-580">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-580">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="03079-581">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-581">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-582">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-582">Turns off HTTPS.</span></span> <span data-ttu-id="03079-583">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-583">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="03079-584">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-584">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="03079-585">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-585">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03079-586">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-586">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-587">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-587">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="03079-588">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-588">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-589">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-589">SDK version</span></span> | <span data-ttu-id="03079-590">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-590">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-591">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-591">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-592">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-592">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-593">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-593">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="03079-594">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-594">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="03079-595">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-595">Includes BrowserLink in the project.</span></span> <span data-ttu-id="03079-596">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-596">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="03079-597">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-597">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="03079-598">.NET Core 3.1.201 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-598">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="03079-599">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-599">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="03079-600">angular, react</span><span class="sxs-lookup"><span data-stu-id="03079-600">angular, react</span></span>

- <span data-ttu-id="03079-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="03079-602">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-602">The type of authentication to use.</span></span> <span data-ttu-id="03079-603">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-603">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="03079-604">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-604">The possible values are:</span></span>

  - <span data-ttu-id="03079-605">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="03079-605">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="03079-606">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-606">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="03079-607">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-607">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="03079-608">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-608">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-609">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-609">Turns off HTTPS.</span></span> <span data-ttu-id="03079-610">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-610">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="03079-611">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-611">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="03079-612">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-612">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-613">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-613">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03079-614">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-614">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-615">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-615">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="03079-616">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-616">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-617">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-617">SDK version</span></span> | <span data-ttu-id="03079-618">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-618">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-619">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-619">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-620">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-620">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-621">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-621">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="03079-622">2.1</span><span class="sxs-lookup"><span data-stu-id="03079-622">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="03079-623">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-623">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="03079-624">reactredux</span><span class="sxs-lookup"><span data-stu-id="03079-624">reactredux</span></span>

- <span data-ttu-id="03079-625">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-625">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="03079-626">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-626">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03079-627">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-627">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-628">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-628">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="03079-629">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-629">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-630">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-630">SDK version</span></span> | <span data-ttu-id="03079-631">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-631">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-632">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-632">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-633">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-633">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-634">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-634">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="03079-635">2.1</span><span class="sxs-lookup"><span data-stu-id="03079-635">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="03079-636">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-636">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-637">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-637">Turns off HTTPS.</span></span>

<span data-ttu-id="03079-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-638">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="03079-639">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="03079-639">razorclasslib</span></span>

- <span data-ttu-id="03079-640">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-640">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="03079-641">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-641">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="03079-642">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-642">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="03079-643">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-643">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="03079-644">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-644">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="03079-645">webapi</span><span class="sxs-lookup"><span data-stu-id="03079-645">webapi</span></span>

- <span data-ttu-id="03079-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="03079-647">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-647">The type of authentication to use.</span></span> <span data-ttu-id="03079-648">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-648">The possible values are:</span></span>

  - <span data-ttu-id="03079-649">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="03079-649">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="03079-650">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-650">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="03079-651">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-651">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="03079-652">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-652">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="03079-653">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-653">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="03079-654">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-654">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="03079-655">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-655">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="03079-656">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-656">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="03079-657">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-657">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="03079-658">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-658">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="03079-659">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-659">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-660">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-660">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="03079-661">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-661">The Client ID for this project.</span></span> <span data-ttu-id="03079-662">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-662">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-663">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-663">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="03079-664">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-664">The domain for the directory tenant.</span></span> <span data-ttu-id="03079-665">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-665">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-666">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-666">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="03079-667">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-667">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="03079-668">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-668">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="03079-669">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-669">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="03079-670">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-670">Allows this application read-access to the directory.</span></span> <span data-ttu-id="03079-671">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-671">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="03079-672">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-672">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="03079-673">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-673">Turns off HTTPS.</span></span> <span data-ttu-id="03079-674">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-674">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="03079-675">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-675">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="03079-676">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-676">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="03079-677">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-677">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="03079-678">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-678">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="03079-679">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="03079-679">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="03079-680">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-680">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="03079-681">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="03079-681">SDK version</span></span> | <span data-ttu-id="03079-682">기본값</span><span class="sxs-lookup"><span data-stu-id="03079-682">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="03079-683">5.0</span><span class="sxs-lookup"><span data-stu-id="03079-683">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="03079-684">3.1</span><span class="sxs-lookup"><span data-stu-id="03079-684">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="03079-685">3.0</span><span class="sxs-lookup"><span data-stu-id="03079-685">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="03079-686">2.1</span><span class="sxs-lookup"><span data-stu-id="03079-686">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="03079-687">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03079-687">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="03079-688">\*\*_</span><span class="sxs-lookup"><span data-stu-id="03079-688">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="03079-689">globaljson</span><span class="sxs-lookup"><span data-stu-id="03079-689">globaljson</span></span>

- <span data-ttu-id="03079-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="03079-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="03079-691">*global.json* 파일에서 사용할 .NET SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-691">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="03079-692">예</span><span class="sxs-lookup"><span data-stu-id="03079-692">Examples</span></span>

- <span data-ttu-id="03079-693">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-693">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="03079-694">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-694">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="03079-695">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-695">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="03079-696">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-696">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="03079-697">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-697">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="03079-698">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-698">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="03079-699">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-699">List all templates matching the *we* substring.</span></span> <span data-ttu-id="03079-700">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03079-700">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="03079-701">*ng* 와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="03079-701">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="03079-702">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-702">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="03079-703">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-703">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="03079-704">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="03079-704">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="03079-705">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json* 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03079-705">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="03079-706">참조</span><span class="sxs-lookup"><span data-stu-id="03079-706">See also</span></span>

- [<span data-ttu-id="03079-707">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="03079-707">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="03079-708">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="03079-708">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="03079-709">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="03079-709">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="03079-710">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="03079-710">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
