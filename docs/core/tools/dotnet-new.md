---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102829"
---
# <a name="dotnet-new"></a><span data-ttu-id="3e794-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3e794-103">dotnet new</span></span>

<span data-ttu-id="3e794-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3e794-105">이름</span><span class="sxs-lookup"><span data-stu-id="3e794-105">Name</span></span>

<span data-ttu-id="3e794-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3e794-107">개요</span><span class="sxs-lookup"><span data-stu-id="3e794-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="3e794-108">설명</span><span class="sxs-lookup"><span data-stu-id="3e794-108">Description</span></span>

<span data-ttu-id="3e794-109">`dotnet new` 명령은 템플릿을 기반으로 .NET Core 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="3e794-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="3e794-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="3e794-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="3e794-112">인수</span><span class="sxs-lookup"><span data-stu-id="3e794-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="3e794-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="3e794-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="3e794-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="3e794-116">`dotnet new --list`를 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="3e794-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="3e794-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="3e794-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="3e794-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="3e794-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="3e794-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="3e794-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="3e794-122">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-122">The command contains a default list of templates.</span></span> <span data-ttu-id="3e794-123">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="3e794-124">다음 표에는 .NET Core SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="3e794-125">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="3e794-126">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="3e794-127">템플릿</span><span class="sxs-lookup"><span data-stu-id="3e794-127">Templates</span></span>                                    | <span data-ttu-id="3e794-128">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="3e794-128">Short name</span></span>                      | <span data-ttu-id="3e794-129">언어</span><span class="sxs-lookup"><span data-stu-id="3e794-129">Language</span></span>     | <span data-ttu-id="3e794-130">Tags</span><span class="sxs-lookup"><span data-stu-id="3e794-130">Tags</span></span>                                  | <span data-ttu-id="3e794-131">도입</span><span class="sxs-lookup"><span data-stu-id="3e794-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="3e794-132">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="3e794-132">Console Application</span></span>                          | [<span data-ttu-id="3e794-133">콘솔</span><span class="sxs-lookup"><span data-stu-id="3e794-133">console</span></span>](#console)             | <span data-ttu-id="3e794-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3e794-134">[C#], F#, VB</span></span> | <span data-ttu-id="3e794-135">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="3e794-135">Common/Console</span></span>                        | <span data-ttu-id="3e794-136">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-136">1.0</span></span>        |
| <span data-ttu-id="3e794-137">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-137">Class library</span></span>                                | [<span data-ttu-id="3e794-138">classlib</span><span class="sxs-lookup"><span data-stu-id="3e794-138">classlib</span></span>](#classlib)           | <span data-ttu-id="3e794-139">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3e794-139">[C#], F#, VB</span></span> | <span data-ttu-id="3e794-140">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-140">Common/Library</span></span>                        | <span data-ttu-id="3e794-141">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-141">1.0</span></span>        |
| <span data-ttu-id="3e794-142">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="3e794-142">WPF Application</span></span>                              | [<span data-ttu-id="3e794-143">wpf</span><span class="sxs-lookup"><span data-stu-id="3e794-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="3e794-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-144">[C#]</span></span>         | <span data-ttu-id="3e794-145">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="3e794-145">Common/WPF</span></span>                            | <span data-ttu-id="3e794-146">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-146">3.0</span></span>        |
| <span data-ttu-id="3e794-147">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-147">WPF Class library</span></span>                            | [<span data-ttu-id="3e794-148">wpflib</span><span class="sxs-lookup"><span data-stu-id="3e794-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="3e794-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-149">[C#]</span></span>         | <span data-ttu-id="3e794-150">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="3e794-150">Common/WPF</span></span>                            | <span data-ttu-id="3e794-151">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-151">3.0</span></span>        |
| <span data-ttu-id="3e794-152">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="3e794-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="3e794-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="3e794-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-154">[C#]</span></span>         | <span data-ttu-id="3e794-155">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="3e794-155">Common/WPF</span></span>                            | <span data-ttu-id="3e794-156">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-156">3.0</span></span>        |
| <span data-ttu-id="3e794-157">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="3e794-158">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="3e794-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="3e794-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-159">[C#]</span></span>         | <span data-ttu-id="3e794-160">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="3e794-160">Common/WPF</span></span>                            | <span data-ttu-id="3e794-161">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-161">3.0</span></span>        |
| <span data-ttu-id="3e794-162">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="3e794-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="3e794-163">winforms</span><span class="sxs-lookup"><span data-stu-id="3e794-163">winforms</span></span>](#winforms)           | <span data-ttu-id="3e794-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-164">[C#]</span></span>         | <span data-ttu-id="3e794-165">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="3e794-165">Common/WinForms</span></span>                       | <span data-ttu-id="3e794-166">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-166">3.0</span></span>        |
| <span data-ttu-id="3e794-167">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="3e794-168">winformslib</span><span class="sxs-lookup"><span data-stu-id="3e794-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="3e794-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-169">[C#]</span></span>         | <span data-ttu-id="3e794-170">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="3e794-170">Common/WinForms</span></span>                       | <span data-ttu-id="3e794-171">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-171">3.0</span></span>        |
| <span data-ttu-id="3e794-172">Worker Service</span><span class="sxs-lookup"><span data-stu-id="3e794-172">Worker Service</span></span>                               | [<span data-ttu-id="3e794-173">worker</span><span class="sxs-lookup"><span data-stu-id="3e794-173">worker</span></span>](#web-others)           | <span data-ttu-id="3e794-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-174">[C#]</span></span>         | <span data-ttu-id="3e794-175">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="3e794-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="3e794-176">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-176">3.0</span></span>        |
| <span data-ttu-id="3e794-177">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="3e794-177">Unit Test Project</span></span>                            | [<span data-ttu-id="3e794-178">mstest</span><span class="sxs-lookup"><span data-stu-id="3e794-178">mstest</span></span>](#test)                 | <span data-ttu-id="3e794-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3e794-179">[C#], F#, VB</span></span> | <span data-ttu-id="3e794-180">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="3e794-180">Test/MSTest</span></span>                           | <span data-ttu-id="3e794-181">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-181">1.0</span></span>        |
| <span data-ttu-id="3e794-182">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="3e794-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="3e794-183">nunit</span><span class="sxs-lookup"><span data-stu-id="3e794-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="3e794-184">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3e794-184">[C#], F#, VB</span></span> | <span data-ttu-id="3e794-185">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="3e794-185">Test/NUnit</span></span>                            | <span data-ttu-id="3e794-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="3e794-186">2.1.400</span></span>    |
| <span data-ttu-id="3e794-187">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="3e794-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="3e794-188">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3e794-188">[C#], F#, VB</span></span> | <span data-ttu-id="3e794-189">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="3e794-189">Test/NUnit</span></span>                            | <span data-ttu-id="3e794-190">2.2</span><span class="sxs-lookup"><span data-stu-id="3e794-190">2.2</span></span>        |
| <span data-ttu-id="3e794-191">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="3e794-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="3e794-192">xunit</span><span class="sxs-lookup"><span data-stu-id="3e794-192">xunit</span></span>](#test)                  | <span data-ttu-id="3e794-193">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3e794-193">[C#], F#, VB</span></span> | <span data-ttu-id="3e794-194">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="3e794-194">Test/xUnit</span></span>                            | <span data-ttu-id="3e794-195">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-195">1.0</span></span>        |
| <span data-ttu-id="3e794-196">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3e794-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="3e794-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-197">[C#]</span></span>         | <span data-ttu-id="3e794-198">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3e794-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="3e794-199">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-199">3.0</span></span>        |
| <span data-ttu-id="3e794-200">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="3e794-200">Razor Page</span></span>                                   | [<span data-ttu-id="3e794-201">page</span><span class="sxs-lookup"><span data-stu-id="3e794-201">page</span></span>](#page)                   | <span data-ttu-id="3e794-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-202">[C#]</span></span>         | <span data-ttu-id="3e794-203">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3e794-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="3e794-204">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-204">2.0</span></span>        |
| <span data-ttu-id="3e794-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3e794-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="3e794-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="3e794-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="3e794-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-207">[C#]</span></span>         | <span data-ttu-id="3e794-208">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3e794-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="3e794-209">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-209">2.0</span></span>        |
| <span data-ttu-id="3e794-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3e794-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="3e794-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-211">[C#]</span></span>         | <span data-ttu-id="3e794-212">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3e794-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="3e794-213">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-213">2.0</span></span>        |
| <span data-ttu-id="3e794-214">Blazor 서버 앱</span><span class="sxs-lookup"><span data-stu-id="3e794-214">Blazor Server App</span></span>                            | [<span data-ttu-id="3e794-215">blazorserver</span><span class="sxs-lookup"><span data-stu-id="3e794-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="3e794-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-216">[C#]</span></span>         | <span data-ttu-id="3e794-217">웹/Blazor</span><span class="sxs-lookup"><span data-stu-id="3e794-217">Web/Blazor</span></span>                            | <span data-ttu-id="3e794-218">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-218">3.0</span></span>        |
| <span data-ttu-id="3e794-219">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="3e794-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="3e794-220">web</span><span class="sxs-lookup"><span data-stu-id="3e794-220">web</span></span>](#web)                     | <span data-ttu-id="3e794-221">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3e794-221">[C#], F#</span></span>     | <span data-ttu-id="3e794-222">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="3e794-222">Web/Empty</span></span>                             | <span data-ttu-id="3e794-223">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-223">1.0</span></span>        |
| <span data-ttu-id="3e794-224">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="3e794-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="3e794-225">mvc</span><span class="sxs-lookup"><span data-stu-id="3e794-225">mvc</span></span>](#web-options)             | <span data-ttu-id="3e794-226">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3e794-226">[C#], F#</span></span>     | <span data-ttu-id="3e794-227">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="3e794-227">Web/MVC</span></span>                               | <span data-ttu-id="3e794-228">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-228">1.0</span></span>        |
| <span data-ttu-id="3e794-229">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="3e794-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="3e794-230">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="3e794-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="3e794-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-231">[C#]</span></span>         | <span data-ttu-id="3e794-232">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="3e794-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="3e794-233">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="3e794-234">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="3e794-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="3e794-235">angular</span><span class="sxs-lookup"><span data-stu-id="3e794-235">angular</span></span>](#spa)                 | <span data-ttu-id="3e794-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-236">[C#]</span></span>         | <span data-ttu-id="3e794-237">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3e794-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="3e794-238">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-238">2.0</span></span>        |
| <span data-ttu-id="3e794-239">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="3e794-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="3e794-240">react</span><span class="sxs-lookup"><span data-stu-id="3e794-240">react</span></span>](#spa)                   | <span data-ttu-id="3e794-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-241">[C#]</span></span>         | <span data-ttu-id="3e794-242">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3e794-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="3e794-243">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-243">2.0</span></span>        |
| <span data-ttu-id="3e794-244">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="3e794-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="3e794-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="3e794-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="3e794-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-246">[C#]</span></span>         | <span data-ttu-id="3e794-247">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3e794-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="3e794-248">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-248">2.0</span></span>        |
| <span data-ttu-id="3e794-249">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-249">Razor Class Library</span></span>                          | [<span data-ttu-id="3e794-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="3e794-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="3e794-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-251">[C#]</span></span>         | <span data-ttu-id="3e794-252">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e794-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="3e794-253">2.1</span><span class="sxs-lookup"><span data-stu-id="3e794-253">2.1</span></span>        |
| <span data-ttu-id="3e794-254">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="3e794-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="3e794-255">webapi</span><span class="sxs-lookup"><span data-stu-id="3e794-255">webapi</span></span>](#webapi)               | <span data-ttu-id="3e794-256">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3e794-256">[C#], F#</span></span>     | <span data-ttu-id="3e794-257">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="3e794-257">Web/WebAPI</span></span>                            | <span data-ttu-id="3e794-258">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-258">1.0</span></span>        |
| <span data-ttu-id="3e794-259">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="3e794-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="3e794-260">grpc</span><span class="sxs-lookup"><span data-stu-id="3e794-260">grpc</span></span>](#web-others)             | <span data-ttu-id="3e794-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="3e794-261">[C#]</span></span>         | <span data-ttu-id="3e794-262">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="3e794-262">Web/gRPC</span></span>                              | <span data-ttu-id="3e794-263">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-263">3.0</span></span>        |
| <span data-ttu-id="3e794-264">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="3e794-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="3e794-265">proto</span><span class="sxs-lookup"><span data-stu-id="3e794-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="3e794-266">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="3e794-266">Web/gRPC</span></span>                              | <span data-ttu-id="3e794-267">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-267">3.0</span></span>        |
| <span data-ttu-id="3e794-268">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="3e794-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="3e794-269">Config</span><span class="sxs-lookup"><span data-stu-id="3e794-269">Config</span></span>                                | <span data-ttu-id="3e794-270">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-270">3.0</span></span>        |
| <span data-ttu-id="3e794-271">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="3e794-271">global.json file</span></span>                             | [<span data-ttu-id="3e794-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="3e794-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="3e794-273">Config</span><span class="sxs-lookup"><span data-stu-id="3e794-273">Config</span></span>                                | <span data-ttu-id="3e794-274">2.0</span><span class="sxs-lookup"><span data-stu-id="3e794-274">2.0</span></span>        |
| <span data-ttu-id="3e794-275">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="3e794-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="3e794-276">Config</span><span class="sxs-lookup"><span data-stu-id="3e794-276">Config</span></span>                                | <span data-ttu-id="3e794-277">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-277">1.0</span></span>        |
| <span data-ttu-id="3e794-278">dotnet local tool 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="3e794-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="3e794-279">Config</span><span class="sxs-lookup"><span data-stu-id="3e794-279">Config</span></span>                                | <span data-ttu-id="3e794-280">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-280">3.0</span></span>        |
| <span data-ttu-id="3e794-281">웹 구성</span><span class="sxs-lookup"><span data-stu-id="3e794-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="3e794-282">Config</span><span class="sxs-lookup"><span data-stu-id="3e794-282">Config</span></span>                                | <span data-ttu-id="3e794-283">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-283">1.0</span></span>        |
| <span data-ttu-id="3e794-284">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="3e794-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="3e794-285">솔루션</span><span class="sxs-lookup"><span data-stu-id="3e794-285">Solution</span></span>                              | <span data-ttu-id="3e794-286">1.0</span><span class="sxs-lookup"><span data-stu-id="3e794-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="3e794-287">옵션</span><span class="sxs-lookup"><span data-stu-id="3e794-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="3e794-288">지정된 명령이 실행될 경우 발생하는 동작에 대한 요약 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="3e794-289">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="3e794-290">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3e794-291">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3e794-292">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-292">Prints out help for the command.</span></span> <span data-ttu-id="3e794-293">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="3e794-294">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="3e794-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="3e794-295">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3e794-296">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3e794-297">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="3e794-298">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="3e794-299">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="3e794-300">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="3e794-301">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="3e794-302">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="3e794-303">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-303">The language of the template to create.</span></span> <span data-ttu-id="3e794-304">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="3e794-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3e794-305">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3e794-306">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3e794-307">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="3e794-308">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="3e794-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="3e794-309">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-309">The name for the created output.</span></span> <span data-ttu-id="3e794-310">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="3e794-311">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="3e794-312">.NET Core 2.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3e794-313">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-313">Location to place the generated output.</span></span> <span data-ttu-id="3e794-314">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="3e794-315">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-315">Filters templates based on available types.</span></span> <span data-ttu-id="3e794-316">미리 정의된 값은 `project`, `item` 또는 `other`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="3e794-317">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3e794-318">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="3e794-319">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="3e794-320">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3e794-321">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3e794-322">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="3e794-323">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="3e794-324">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="3e794-325">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="3e794-326">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="3e794-327">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="3e794-328">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="3e794-328">Template options</span></span>

<span data-ttu-id="3e794-329">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-329">Each project template may have additional options available.</span></span> <span data-ttu-id="3e794-330">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="3e794-331">콘솔</span><span class="sxs-lookup"><span data-stu-id="3e794-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-332">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-333">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3e794-334">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-335">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-335">SDK version</span></span> | <span data-ttu-id="3e794-336">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-337">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-338">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3e794-339">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3e794-340">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="3e794-341">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-341">Not supported for F#.</span></span> <span data-ttu-id="3e794-342">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3e794-343">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-344">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="3e794-345">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="3e794-346">classlib</span><span class="sxs-lookup"><span data-stu-id="3e794-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-347">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-348">값: `netcoreapp<version>`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="3e794-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3e794-349">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3e794-350">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3e794-351">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="3e794-352">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-352">Not supported for F#.</span></span> <span data-ttu-id="3e794-353">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3e794-354">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-355">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="3e794-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="3e794-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-357">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-358">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="3e794-359">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3e794-360">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3e794-361">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="3e794-362">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-363">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="3e794-364">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="3e794-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3e794-365">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3e794-366">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="3e794-367">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-368">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="3e794-369">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="3e794-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-370">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-371">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="3e794-372">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-373">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-374">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="3e794-375">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="3e794-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-376">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-377">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3e794-378">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-379">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-379">SDK version</span></span> | <span data-ttu-id="3e794-380">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-381">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-382">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="3e794-383">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-384">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="3e794-385">nunit</span><span class="sxs-lookup"><span data-stu-id="3e794-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-386">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="3e794-387">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-388">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-388">SDK version</span></span> | <span data-ttu-id="3e794-389">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-390">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-391">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3e794-392">2.2</span><span class="sxs-lookup"><span data-stu-id="3e794-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="3e794-393">2.1</span><span class="sxs-lookup"><span data-stu-id="3e794-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="3e794-394">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-395">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="3e794-396">페이지</span><span class="sxs-lookup"><span data-stu-id="3e794-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="3e794-397">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-397">Namespace for the generated code.</span></span> <span data-ttu-id="3e794-398">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="3e794-399">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="3e794-400">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="3e794-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="3e794-401">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-401">Namespace for the generated code.</span></span> <span data-ttu-id="3e794-402">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="3e794-403">blazorserver</span><span class="sxs-lookup"><span data-stu-id="3e794-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3e794-404">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-404">The type of authentication to use.</span></span> <span data-ttu-id="3e794-405">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-405">The possible values are:</span></span>

  - <span data-ttu-id="3e794-406">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="3e794-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3e794-407">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="3e794-408">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="3e794-409">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="3e794-410">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="3e794-411">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="3e794-412">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3e794-413">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-414">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="3e794-415">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3e794-416">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="3e794-417">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="3e794-418">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="3e794-419">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="3e794-420">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="3e794-421">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3e794-422">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3e794-423">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="3e794-424">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-424">The Client ID for this project.</span></span> <span data-ttu-id="3e794-425">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3e794-426">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="3e794-427">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-427">The domain for the directory tenant.</span></span> <span data-ttu-id="3e794-428">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-429">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="3e794-430">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3e794-431">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3e794-432">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="3e794-433">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3e794-434">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-435">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="3e794-436">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="3e794-437">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-438">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="3e794-439">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-439">Turns off HTTPS.</span></span> <span data-ttu-id="3e794-440">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3e794-441">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3e794-442">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-443">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="3e794-444">웹</span><span class="sxs-lookup"><span data-stu-id="3e794-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-445">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-446">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-447">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3e794-448">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-449">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-449">SDK version</span></span> | <span data-ttu-id="3e794-450">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-451">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-452">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3e794-453">2.1</span><span class="sxs-lookup"><span data-stu-id="3e794-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="3e794-454">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="3e794-455">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="3e794-456">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="3e794-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3e794-457">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-457">The type of authentication to use.</span></span> <span data-ttu-id="3e794-458">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-458">The possible values are:</span></span>

  - <span data-ttu-id="3e794-459">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="3e794-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3e794-460">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="3e794-461">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="3e794-462">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="3e794-463">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="3e794-464">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="3e794-465">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3e794-466">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-467">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="3e794-468">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3e794-469">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="3e794-470">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="3e794-471">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="3e794-472">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="3e794-473">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="3e794-474">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3e794-475">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3e794-476">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="3e794-477">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-477">The Client ID for this project.</span></span> <span data-ttu-id="3e794-478">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3e794-479">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="3e794-480">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-480">The domain for the directory tenant.</span></span> <span data-ttu-id="3e794-481">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-482">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="3e794-483">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3e794-484">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3e794-485">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="3e794-486">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3e794-487">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-488">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="3e794-489">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="3e794-490">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-491">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="3e794-492">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-492">Turns off HTTPS.</span></span> <span data-ttu-id="3e794-493">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3e794-494">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3e794-495">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-496">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-497">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3e794-498">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-499">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-499">SDK version</span></span> | <span data-ttu-id="3e794-500">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-501">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-502">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="3e794-503">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="3e794-504">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="3e794-505">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="3e794-506">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="3e794-507">.NET Core 3.1 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="3e794-508">angular, react</span><span class="sxs-lookup"><span data-stu-id="3e794-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3e794-509">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-509">The type of authentication to use.</span></span> <span data-ttu-id="3e794-510">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="3e794-511">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-511">The possible values are:</span></span>

  - <span data-ttu-id="3e794-512">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="3e794-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3e794-513">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-514">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-515">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="3e794-516">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-516">Turns off HTTPS.</span></span> <span data-ttu-id="3e794-517">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3e794-518">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3e794-519">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-520">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-521">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-522">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3e794-523">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-524">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-524">SDK version</span></span> | <span data-ttu-id="3e794-525">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-526">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-527">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3e794-528">2.1</span><span class="sxs-lookup"><span data-stu-id="3e794-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="3e794-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="3e794-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-530">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-531">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-532">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3e794-533">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-534">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-534">SDK version</span></span> | <span data-ttu-id="3e794-535">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-536">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-537">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3e794-538">2.1</span><span class="sxs-lookup"><span data-stu-id="3e794-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="3e794-539">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="3e794-540">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="3e794-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="3e794-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="3e794-542">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="3e794-543">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="3e794-544">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="3e794-545">webapi</span><span class="sxs-lookup"><span data-stu-id="3e794-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3e794-546">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-546">The type of authentication to use.</span></span> <span data-ttu-id="3e794-547">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-547">The possible values are:</span></span>

  - <span data-ttu-id="3e794-548">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="3e794-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3e794-549">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="3e794-550">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="3e794-551">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="3e794-552">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3e794-553">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3e794-554">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="3e794-555">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3e794-556">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="3e794-557">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3e794-558">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3e794-559">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="3e794-560">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-560">The Client ID for this project.</span></span> <span data-ttu-id="3e794-561">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3e794-562">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="3e794-563">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-563">The domain for the directory tenant.</span></span> <span data-ttu-id="3e794-564">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3e794-565">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="3e794-566">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3e794-567">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3e794-568">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="3e794-569">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="3e794-570">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3e794-571">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="3e794-572">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-572">Turns off HTTPS.</span></span> <span data-ttu-id="3e794-573">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3e794-574">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3e794-575">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3e794-576">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3e794-577">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3e794-578">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3e794-579">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3e794-580">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="3e794-580">SDK version</span></span> | <span data-ttu-id="3e794-581">기본값</span><span class="sxs-lookup"><span data-stu-id="3e794-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3e794-582">3.1</span><span class="sxs-lookup"><span data-stu-id="3e794-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3e794-583">3.0</span><span class="sxs-lookup"><span data-stu-id="3e794-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3e794-584">2.1</span><span class="sxs-lookup"><span data-stu-id="3e794-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="3e794-585">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="3e794-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="3e794-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="3e794-587">*global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="3e794-588">예</span><span class="sxs-lookup"><span data-stu-id="3e794-588">Examples</span></span>

- <span data-ttu-id="3e794-589">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="3e794-590">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="3e794-591">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="3e794-592">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="3e794-593">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="3e794-594">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="3e794-595">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="3e794-596">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="3e794-597">*ng*와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="3e794-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="3e794-598">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="3e794-599">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="3e794-600">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="3e794-601">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e794-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="3e794-602">참조</span><span class="sxs-lookup"><span data-stu-id="3e794-602">See also</span></span>

- [<span data-ttu-id="3e794-603">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="3e794-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="3e794-604">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="3e794-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="3e794-605">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="3e794-605">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="3e794-606">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="3e794-606">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
