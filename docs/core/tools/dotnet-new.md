---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
ms.date: 02/13/2020
ms.openlocfilehash: f11512acf5a1fdc4bde49b3d1212ccf6335dff8b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451332"
---
# <a name="dotnet-new"></a><span data-ttu-id="ed1f5-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ed1f5-103">dotnet new</span></span>

<span data-ttu-id="ed1f5-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ed1f5-105">이름</span><span class="sxs-lookup"><span data-stu-id="ed1f5-105">Name</span></span>

<span data-ttu-id="ed1f5-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ed1f5-107">개요</span><span class="sxs-lookup"><span data-stu-id="ed1f5-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] 
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ed1f5-108">설명</span><span class="sxs-lookup"><span data-stu-id="ed1f5-108">Description</span></span>

<span data-ttu-id="ed1f5-109">`dotnet new` 명령은 템플릿을 기반으로 .NET Core 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="ed1f5-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="ed1f5-111">인수</span><span class="sxs-lookup"><span data-stu-id="ed1f5-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="ed1f5-112">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="ed1f5-113">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="ed1f5-114">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="ed1f5-115">`dotnet new --list`를 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="ed1f5-116">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="ed1f5-117">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="ed1f5-118">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="ed1f5-119">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="ed1f5-120">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="ed1f5-121">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-121">The command contains a default list of templates.</span></span> <span data-ttu-id="ed1f5-122">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="ed1f5-123">다음 표에는 .NET Core SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="ed1f5-124">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="ed1f5-125">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="ed1f5-126">템플릿</span><span class="sxs-lookup"><span data-stu-id="ed1f5-126">Templates</span></span>                                    | <span data-ttu-id="ed1f5-127">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="ed1f5-127">Short name</span></span>                      | <span data-ttu-id="ed1f5-128">언어</span><span class="sxs-lookup"><span data-stu-id="ed1f5-128">Language</span></span>     | <span data-ttu-id="ed1f5-129">Tags</span><span class="sxs-lookup"><span data-stu-id="ed1f5-129">Tags</span></span>                                  | <span data-ttu-id="ed1f5-130">도입</span><span class="sxs-lookup"><span data-stu-id="ed1f5-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="ed1f5-131">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ed1f5-131">Console Application</span></span>                          | [<span data-ttu-id="ed1f5-132">콘솔</span><span class="sxs-lookup"><span data-stu-id="ed1f5-132">console</span></span>](#console)             | <span data-ttu-id="ed1f5-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ed1f5-133">[C#], F#, VB</span></span> | <span data-ttu-id="ed1f5-134">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="ed1f5-134">Common/Console</span></span>                        | <span data-ttu-id="ed1f5-135">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-135">1.0</span></span>        |
| <span data-ttu-id="ed1f5-136">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-136">Class library</span></span>                                | [<span data-ttu-id="ed1f5-137">classlib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-137">classlib</span></span>](#classlib)           | <span data-ttu-id="ed1f5-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ed1f5-138">[C#], F#, VB</span></span> | <span data-ttu-id="ed1f5-139">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-139">Common/Library</span></span>                        | <span data-ttu-id="ed1f5-140">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-140">1.0</span></span>        |
| <span data-ttu-id="ed1f5-141">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ed1f5-141">WPF Application</span></span>                              | [<span data-ttu-id="ed1f5-142">wpf</span><span class="sxs-lookup"><span data-stu-id="ed1f5-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="ed1f5-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-143">[C#]</span></span>         | <span data-ttu-id="ed1f5-144">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="ed1f5-144">Common/WPF</span></span>                            | <span data-ttu-id="ed1f5-145">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-145">3.0</span></span>        |
| <span data-ttu-id="ed1f5-146">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-146">WPF Class library</span></span>                            | [<span data-ttu-id="ed1f5-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="ed1f5-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-148">[C#]</span></span>         | <span data-ttu-id="ed1f5-149">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="ed1f5-149">Common/WPF</span></span>                            | <span data-ttu-id="ed1f5-150">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-150">3.0</span></span>        |
| <span data-ttu-id="ed1f5-151">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="ed1f5-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="ed1f5-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-153">[C#]</span></span>         | <span data-ttu-id="ed1f5-154">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="ed1f5-154">Common/WPF</span></span>                            | <span data-ttu-id="ed1f5-155">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-155">3.0</span></span>        |
| <span data-ttu-id="ed1f5-156">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="ed1f5-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="ed1f5-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-158">[C#]</span></span>         | <span data-ttu-id="ed1f5-159">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="ed1f5-159">Common/WPF</span></span>                            | <span data-ttu-id="ed1f5-160">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-160">3.0</span></span>        |
| <span data-ttu-id="ed1f5-161">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ed1f5-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="ed1f5-162">winforms</span><span class="sxs-lookup"><span data-stu-id="ed1f5-162">winforms</span></span>](#winforms)           | <span data-ttu-id="ed1f5-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-163">[C#]</span></span>         | <span data-ttu-id="ed1f5-164">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="ed1f5-164">Common/WinForms</span></span>                       | <span data-ttu-id="ed1f5-165">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-165">3.0</span></span>        |
| <span data-ttu-id="ed1f5-166">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="ed1f5-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="ed1f5-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-168">[C#]</span></span>         | <span data-ttu-id="ed1f5-169">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="ed1f5-169">Common/WinForms</span></span>                       | <span data-ttu-id="ed1f5-170">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-170">3.0</span></span>        |
| <span data-ttu-id="ed1f5-171">Worker Service</span><span class="sxs-lookup"><span data-stu-id="ed1f5-171">Worker Service</span></span>                               | [<span data-ttu-id="ed1f5-172">worker</span><span class="sxs-lookup"><span data-stu-id="ed1f5-172">worker</span></span>](#web-others)           | <span data-ttu-id="ed1f5-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-173">[C#]</span></span>         | <span data-ttu-id="ed1f5-174">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="ed1f5-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="ed1f5-175">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-175">3.0</span></span>        |
| <span data-ttu-id="ed1f5-176">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ed1f5-176">Unit Test Project</span></span>                            | [<span data-ttu-id="ed1f5-177">mstest</span><span class="sxs-lookup"><span data-stu-id="ed1f5-177">mstest</span></span>](#test)                 | <span data-ttu-id="ed1f5-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ed1f5-178">[C#], F#, VB</span></span> | <span data-ttu-id="ed1f5-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="ed1f5-179">Test/MSTest</span></span>                           | <span data-ttu-id="ed1f5-180">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-180">1.0</span></span>        |
| <span data-ttu-id="ed1f5-181">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ed1f5-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="ed1f5-182">nunit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="ed1f5-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ed1f5-183">[C#], F#, VB</span></span> | <span data-ttu-id="ed1f5-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-184">Test/NUnit</span></span>                            | <span data-ttu-id="ed1f5-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="ed1f5-185">2.1.400</span></span>    |
| <span data-ttu-id="ed1f5-186">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="ed1f5-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="ed1f5-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ed1f5-187">[C#], F#, VB</span></span> | <span data-ttu-id="ed1f5-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-188">Test/NUnit</span></span>                            | <span data-ttu-id="ed1f5-189">2.2</span><span class="sxs-lookup"><span data-stu-id="ed1f5-189">2.2</span></span>        |
| <span data-ttu-id="ed1f5-190">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ed1f5-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="ed1f5-191">xunit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-191">xunit</span></span>](#test)                  | <span data-ttu-id="ed1f5-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ed1f5-192">[C#], F#, VB</span></span> | <span data-ttu-id="ed1f5-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-193">Test/xUnit</span></span>                            | <span data-ttu-id="ed1f5-194">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-194">1.0</span></span>        |
| <span data-ttu-id="ed1f5-195">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ed1f5-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="ed1f5-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-196">[C#]</span></span>         | <span data-ttu-id="ed1f5-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ed1f5-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="ed1f5-198">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-198">3.0</span></span>        |
| <span data-ttu-id="ed1f5-199">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="ed1f5-199">Razor Page</span></span>                                   | [<span data-ttu-id="ed1f5-200">page</span><span class="sxs-lookup"><span data-stu-id="ed1f5-200">page</span></span>](#page)                   | <span data-ttu-id="ed1f5-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-201">[C#]</span></span>         | <span data-ttu-id="ed1f5-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ed1f5-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="ed1f5-203">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-203">2.0</span></span>        |
| <span data-ttu-id="ed1f5-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="ed1f5-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="ed1f5-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="ed1f5-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="ed1f5-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-206">[C#]</span></span>         | <span data-ttu-id="ed1f5-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ed1f5-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="ed1f5-208">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-208">2.0</span></span>        |
| <span data-ttu-id="ed1f5-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="ed1f5-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="ed1f5-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-210">[C#]</span></span>         | <span data-ttu-id="ed1f5-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ed1f5-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="ed1f5-212">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-212">2.0</span></span>        |
| <span data-ttu-id="ed1f5-213">Blazor 서버 앱</span><span class="sxs-lookup"><span data-stu-id="ed1f5-213">Blazor Server App</span></span>                            | [<span data-ttu-id="ed1f5-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="ed1f5-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="ed1f5-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-215">[C#]</span></span>         | <span data-ttu-id="ed1f5-216">웹/Blazor</span><span class="sxs-lookup"><span data-stu-id="ed1f5-216">Web/Blazor</span></span>                            | <span data-ttu-id="ed1f5-217">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-217">3.0</span></span>        |
| <span data-ttu-id="ed1f5-218">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="ed1f5-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="ed1f5-219">web</span><span class="sxs-lookup"><span data-stu-id="ed1f5-219">web</span></span>](#web)                     | <span data-ttu-id="ed1f5-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ed1f5-220">[C#], F#</span></span>     | <span data-ttu-id="ed1f5-221">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="ed1f5-221">Web/Empty</span></span>                             | <span data-ttu-id="ed1f5-222">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-222">1.0</span></span>        |
| <span data-ttu-id="ed1f5-223">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="ed1f5-224">mvc</span><span class="sxs-lookup"><span data-stu-id="ed1f5-224">mvc</span></span>](#web-options)             | <span data-ttu-id="ed1f5-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ed1f5-225">[C#], F#</span></span>     | <span data-ttu-id="ed1f5-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="ed1f5-226">Web/MVC</span></span>                               | <span data-ttu-id="ed1f5-227">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-227">1.0</span></span>        |
| <span data-ttu-id="ed1f5-228">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="ed1f5-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="ed1f5-229">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="ed1f5-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="ed1f5-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-230">[C#]</span></span>         | <span data-ttu-id="ed1f5-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="ed1f5-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="ed1f5-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="ed1f5-233">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="ed1f5-234">angular</span><span class="sxs-lookup"><span data-stu-id="ed1f5-234">angular</span></span>](#spa)                 | <span data-ttu-id="ed1f5-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-235">[C#]</span></span>         | <span data-ttu-id="ed1f5-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ed1f5-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ed1f5-237">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-237">2.0</span></span>        |
| <span data-ttu-id="ed1f5-238">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="ed1f5-239">react</span><span class="sxs-lookup"><span data-stu-id="ed1f5-239">react</span></span>](#spa)                   | <span data-ttu-id="ed1f5-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-240">[C#]</span></span>         | <span data-ttu-id="ed1f5-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ed1f5-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ed1f5-242">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-242">2.0</span></span>        |
| <span data-ttu-id="ed1f5-243">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="ed1f5-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="ed1f5-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="ed1f5-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-245">[C#]</span></span>         | <span data-ttu-id="ed1f5-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ed1f5-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ed1f5-247">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-247">2.0</span></span>        |
| <span data-ttu-id="ed1f5-248">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-248">Razor Class Library</span></span>                          | [<span data-ttu-id="ed1f5-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="ed1f5-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-250">[C#]</span></span>         | <span data-ttu-id="ed1f5-251">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed1f5-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="ed1f5-252">2.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-252">2.1</span></span>        |
| <span data-ttu-id="ed1f5-253">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="ed1f5-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="ed1f5-254">webapi</span><span class="sxs-lookup"><span data-stu-id="ed1f5-254">webapi</span></span>](#webapi)               | <span data-ttu-id="ed1f5-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ed1f5-255">[C#], F#</span></span>     | <span data-ttu-id="ed1f5-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="ed1f5-256">Web/WebAPI</span></span>                            | <span data-ttu-id="ed1f5-257">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-257">1.0</span></span>        |
| <span data-ttu-id="ed1f5-258">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="ed1f5-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="ed1f5-259">grpc</span><span class="sxs-lookup"><span data-stu-id="ed1f5-259">grpc</span></span>](#web-others)             | <span data-ttu-id="ed1f5-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="ed1f5-260">[C#]</span></span>         | <span data-ttu-id="ed1f5-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="ed1f5-261">Web/gRPC</span></span>                              | <span data-ttu-id="ed1f5-262">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-262">3.0</span></span>        |
| <span data-ttu-id="ed1f5-263">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="ed1f5-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="ed1f5-264">proto</span><span class="sxs-lookup"><span data-stu-id="ed1f5-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="ed1f5-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="ed1f5-265">Web/gRPC</span></span>                              | <span data-ttu-id="ed1f5-266">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-266">3.0</span></span>        |
| <span data-ttu-id="ed1f5-267">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="ed1f5-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="ed1f5-268">Config</span><span class="sxs-lookup"><span data-stu-id="ed1f5-268">Config</span></span>                                | <span data-ttu-id="ed1f5-269">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-269">3.0</span></span>        |
| <span data-ttu-id="ed1f5-270">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="ed1f5-270">global.json file</span></span>                             | [<span data-ttu-id="ed1f5-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="ed1f5-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="ed1f5-272">Config</span><span class="sxs-lookup"><span data-stu-id="ed1f5-272">Config</span></span>                                | <span data-ttu-id="ed1f5-273">2.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-273">2.0</span></span>        |
| <span data-ttu-id="ed1f5-274">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="ed1f5-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="ed1f5-275">Config</span><span class="sxs-lookup"><span data-stu-id="ed1f5-275">Config</span></span>                                | <span data-ttu-id="ed1f5-276">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-276">1.0</span></span>        |
| <span data-ttu-id="ed1f5-277">dotnet local tool 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="ed1f5-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="ed1f5-278">Config</span><span class="sxs-lookup"><span data-stu-id="ed1f5-278">Config</span></span>                                | <span data-ttu-id="ed1f5-279">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-279">3.0</span></span>        |
| <span data-ttu-id="ed1f5-280">웹 구성</span><span class="sxs-lookup"><span data-stu-id="ed1f5-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="ed1f5-281">Config</span><span class="sxs-lookup"><span data-stu-id="ed1f5-281">Config</span></span>                                | <span data-ttu-id="ed1f5-282">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-282">1.0</span></span>        |
| <span data-ttu-id="ed1f5-283">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="ed1f5-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="ed1f5-284">솔루션</span><span class="sxs-lookup"><span data-stu-id="ed1f5-284">Solution</span></span>                              | <span data-ttu-id="ed1f5-285">1.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="ed1f5-286">옵션</span><span class="sxs-lookup"><span data-stu-id="ed1f5-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="ed1f5-287">지정된 명령이 실행될 경우 발생하는 동작에 대한 요약 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="ed1f5-288">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="ed1f5-289">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="ed1f5-290">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed1f5-291">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-291">Prints out help for the command.</span></span> <span data-ttu-id="ed1f5-292">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="ed1f5-293">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="ed1f5-294">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ed1f5-295">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="ed1f5-296">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="ed1f5-297">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="ed1f5-298">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="ed1f5-299">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="ed1f5-300">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="ed1f5-301">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="ed1f5-302">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-302">The language of the template to create.</span></span> <span data-ttu-id="ed1f5-303">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="ed1f5-304">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ed1f5-305">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="ed1f5-306">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="ed1f5-307">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="ed1f5-308">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-308">The name for the created output.</span></span> <span data-ttu-id="ed1f5-309">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="ed1f5-310">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="ed1f5-311">.NET Core 2.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="ed1f5-312">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-312">Location to place the generated output.</span></span> <span data-ttu-id="ed1f5-313">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="ed1f5-314">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-314">Filters templates based on available types.</span></span> <span data-ttu-id="ed1f5-315">미리 정의된 값은 "project", "item" 또는 "other"입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="ed1f5-316">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ed1f5-317">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="ed1f5-318">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="ed1f5-319">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ed1f5-320">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="ed1f5-321">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="ed1f5-322">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="ed1f5-323">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="ed1f5-324">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="ed1f5-325">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="ed1f5-326">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="ed1f5-327">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="ed1f5-327">Template options</span></span>

<span data-ttu-id="ed1f5-328">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-328">Each project template may have additional options available.</span></span> <span data-ttu-id="ed1f5-329">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="ed1f5-330">콘솔</span><span class="sxs-lookup"><span data-stu-id="ed1f5-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-331">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-332">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ed1f5-333">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-334">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-334">SDK version</span></span> | <span data-ttu-id="ed1f5-335">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-336">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-337">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ed1f5-338">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ed1f5-339">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="ed1f5-340">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-340">Not supported for F#.</span></span> <span data-ttu-id="ed1f5-341">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ed1f5-342">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`** 

  <span data-ttu-id="ed1f5-343">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="ed1f5-344">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="ed1f5-345">classlib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-346">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-347">값: `netcoreapp<version>`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="ed1f5-348">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ed1f5-349">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ed1f5-350">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="ed1f5-351">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-351">Not supported for F#.</span></span> <span data-ttu-id="ed1f5-352">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ed1f5-353">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-354">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="ed1f5-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-356">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-357">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="ed1f5-358">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-358">Available since .NET Core 3.1 SDK.</span></span> 

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ed1f5-359">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ed1f5-360">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="ed1f5-361">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-362">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="ed1f5-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ed1f5-364">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ed1f5-365">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="ed1f5-366">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-367">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="ed1f5-368">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="ed1f5-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-369">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-370">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="ed1f5-371">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-371">Available since .NET Core 3.1 SDK.</span></span> 

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-372">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-373">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a> <span data-ttu-id="ed1f5-374">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-375">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-376">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ed1f5-377">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-378">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-378">SDK version</span></span> | <span data-ttu-id="ed1f5-379">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-380">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-381">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="ed1f5-382">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-383">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="ed1f5-384">nunit</span><span class="sxs-lookup"><span data-stu-id="ed1f5-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-385">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="ed1f5-386">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-387">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-387">SDK version</span></span> | <span data-ttu-id="ed1f5-388">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-389">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-390">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ed1f5-391">2.2</span><span class="sxs-lookup"><span data-stu-id="ed1f5-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="ed1f5-392">2.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="ed1f5-393">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-394">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="ed1f5-395">페이지</span><span class="sxs-lookup"><span data-stu-id="ed1f5-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="ed1f5-396">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-396">Namespace for the generated code.</span></span> <span data-ttu-id="ed1f5-397">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="ed1f5-398">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="ed1f5-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="ed1f5-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="ed1f5-400">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-400">Namespace for the generated code.</span></span> <span data-ttu-id="ed1f5-401">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="ed1f5-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="ed1f5-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ed1f5-403">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-403">The type of authentication to use.</span></span> <span data-ttu-id="ed1f5-404">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-404">The possible values are:</span></span>

  - <span data-ttu-id="ed1f5-405">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ed1f5-406">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="ed1f5-407">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ed1f5-408">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ed1f5-409">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="ed1f5-410">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ed1f5-411">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ed1f5-412">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-413">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ed1f5-414">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ed1f5-415">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="ed1f5-416">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="ed1f5-417">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="ed1f5-418">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="ed1f5-419">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ed1f5-420">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ed1f5-421">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ed1f5-422">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ed1f5-423">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-423">The Client ID for this project.</span></span> <span data-ttu-id="ed1f5-424">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ed1f5-425">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ed1f5-426">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-426">The domain for the directory tenant.</span></span> <span data-ttu-id="ed1f5-427">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-428">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ed1f5-429">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ed1f5-430">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ed1f5-431">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="ed1f5-432">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ed1f5-433">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-434">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ed1f5-435">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ed1f5-436">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-437">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ed1f5-438">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-438">Turns off HTTPS.</span></span> <span data-ttu-id="ed1f5-439">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ed1f5-440">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ed1f5-441">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-442">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="ed1f5-443">웹</span><span class="sxs-lookup"><span data-stu-id="ed1f5-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-444">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-445">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-446">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ed1f5-447">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-448">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-448">SDK version</span></span> | <span data-ttu-id="ed1f5-449">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-450">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-451">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ed1f5-452">2.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="ed1f5-453">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ed1f5-454">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="ed1f5-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="ed1f5-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ed1f5-456">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-456">The type of authentication to use.</span></span> <span data-ttu-id="ed1f5-457">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-457">The possible values are:</span></span>

  - <span data-ttu-id="ed1f5-458">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ed1f5-459">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="ed1f5-460">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ed1f5-461">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ed1f5-462">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="ed1f5-463">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ed1f5-464">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ed1f5-465">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-466">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ed1f5-467">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ed1f5-468">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="ed1f5-469">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="ed1f5-470">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="ed1f5-471">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="ed1f5-472">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ed1f5-473">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ed1f5-474">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ed1f5-475">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ed1f5-476">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-476">The Client ID for this project.</span></span> <span data-ttu-id="ed1f5-477">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ed1f5-478">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ed1f5-479">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-479">The domain for the directory tenant.</span></span> <span data-ttu-id="ed1f5-480">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-481">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ed1f5-482">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ed1f5-483">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ed1f5-484">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="ed1f5-485">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ed1f5-486">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-487">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ed1f5-488">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ed1f5-489">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-490">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ed1f5-491">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-491">Turns off HTTPS.</span></span> <span data-ttu-id="ed1f5-492">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ed1f5-493">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ed1f5-494">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-495">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-496">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ed1f5-497">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-498">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-498">SDK version</span></span> | <span data-ttu-id="ed1f5-499">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-500">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-501">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="ed1f5-502">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="ed1f5-503">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="ed1f5-504">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="ed1f5-505">angular, react</span><span class="sxs-lookup"><span data-stu-id="ed1f5-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ed1f5-506">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-506">The type of authentication to use.</span></span> <span data-ttu-id="ed1f5-507">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-507">Available since .NET Core 3.0 SDK.</span></span> 
  
  <span data-ttu-id="ed1f5-508">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-508">The possible values are:</span></span>

  - <span data-ttu-id="ed1f5-509">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ed1f5-510">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-511">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-511">Excludes *launchSettings.json* from the generated template.</span></span> 

- **`--no-restore`**

  <span data-ttu-id="ed1f5-512">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ed1f5-513">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-513">Turns off HTTPS.</span></span> <span data-ttu-id="ed1f5-514">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ed1f5-515">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ed1f5-516">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-517">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-518">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-519">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ed1f5-520">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-521">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-521">SDK version</span></span> | <span data-ttu-id="ed1f5-522">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-523">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-524">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ed1f5-525">2.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="ed1f5-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="ed1f5-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-527">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-527">Excludes *launchSettings.json* from the generated template.</span></span> 

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-528">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-529">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ed1f5-530">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-531">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-531">SDK version</span></span> | <span data-ttu-id="ed1f5-532">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-533">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-534">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ed1f5-535">2.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="ed1f5-536">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ed1f5-537">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="ed1f5-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="ed1f5-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed1f5-539">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="ed1f5-540">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="ed1f5-541">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="ed1f5-542">webapi</span><span class="sxs-lookup"><span data-stu-id="ed1f5-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ed1f5-543">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-543">The type of authentication to use.</span></span> <span data-ttu-id="ed1f5-544">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-544">The possible values are:</span></span>

  - <span data-ttu-id="ed1f5-545">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ed1f5-546">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ed1f5-547">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ed1f5-548">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ed1f5-549">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ed1f5-550">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ed1f5-551">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ed1f5-552">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ed1f5-553">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ed1f5-554">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ed1f5-555">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ed1f5-556">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ed1f5-557">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-557">The Client ID for this project.</span></span> <span data-ttu-id="ed1f5-558">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ed1f5-559">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ed1f5-560">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-560">The domain for the directory tenant.</span></span> <span data-ttu-id="ed1f5-561">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ed1f5-562">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ed1f5-563">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ed1f5-564">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ed1f5-565">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ed1f5-566">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ed1f5-567">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ed1f5-568">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ed1f5-569">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-569">Turns off HTTPS.</span></span> <span data-ttu-id="ed1f5-570">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="ed1f5-571">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ed1f5-572">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ed1f5-573">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed1f5-574">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ed1f5-575">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ed1f5-576">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ed1f5-577">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ed1f5-577">SDK version</span></span> | <span data-ttu-id="ed1f5-578">기본값</span><span class="sxs-lookup"><span data-stu-id="ed1f5-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ed1f5-579">3.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ed1f5-580">3.0</span><span class="sxs-lookup"><span data-stu-id="ed1f5-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ed1f5-581">2.1</span><span class="sxs-lookup"><span data-stu-id="ed1f5-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="ed1f5-582">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="ed1f5-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="ed1f5-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="ed1f5-584">*global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="ed1f5-585">예</span><span class="sxs-lookup"><span data-stu-id="ed1f5-585">Examples</span></span>

- <span data-ttu-id="ed1f5-586">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="ed1f5-587">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="ed1f5-588">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="ed1f5-589">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="ed1f5-590">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="ed1f5-591">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="ed1f5-592">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="ed1f5-593">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="ed1f5-594">*ng*와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="ed1f5-595">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="ed1f5-596">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="ed1f5-597">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="ed1f5-598">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="ed1f5-599">참조</span><span class="sxs-lookup"><span data-stu-id="ed1f5-599">See also</span></span>

- [<span data-ttu-id="ed1f5-600">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="ed1f5-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="ed1f5-601">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="ed1f5-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="ed1f5-602">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-602">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="ed1f5-603">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-603">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
