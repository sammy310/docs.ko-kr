---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
ms.date: 04/10/2020
ms.openlocfilehash: 39301ad95761848b60b45cb5c18ede937f70c32c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283977"
---
# <a name="dotnet-new"></a><span data-ttu-id="0d65d-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="0d65d-103">dotnet new</span></span>

<span data-ttu-id="0d65d-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0d65d-105">이름</span><span class="sxs-lookup"><span data-stu-id="0d65d-105">Name</span></span>

<span data-ttu-id="0d65d-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0d65d-107">개요</span><span class="sxs-lookup"><span data-stu-id="0d65d-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="0d65d-108">설명</span><span class="sxs-lookup"><span data-stu-id="0d65d-108">Description</span></span>

<span data-ttu-id="0d65d-109">`dotnet new` 명령은 템플릿을 기반으로 .NET Core 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="0d65d-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="0d65d-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="0d65d-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="0d65d-112">인수</span><span class="sxs-lookup"><span data-stu-id="0d65d-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="0d65d-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="0d65d-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="0d65d-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="0d65d-116">`dotnet new --list` 또는 `dotnet new -l`을 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="0d65d-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="0d65d-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="0d65d-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="0d65d-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="0d65d-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="0d65d-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="0d65d-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="0d65d-122">다음 표에는 .NET Core SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="0d65d-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="0d65d-124">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="0d65d-125">템플릿</span><span class="sxs-lookup"><span data-stu-id="0d65d-125">Templates</span></span>                                    | <span data-ttu-id="0d65d-126">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="0d65d-126">Short name</span></span>                      | <span data-ttu-id="0d65d-127">언어</span><span class="sxs-lookup"><span data-stu-id="0d65d-127">Language</span></span>     | <span data-ttu-id="0d65d-128">Tags</span><span class="sxs-lookup"><span data-stu-id="0d65d-128">Tags</span></span>                                  | <span data-ttu-id="0d65d-129">도입</span><span class="sxs-lookup"><span data-stu-id="0d65d-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="0d65d-130">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="0d65d-130">Console Application</span></span>                          | [<span data-ttu-id="0d65d-131">콘솔</span><span class="sxs-lookup"><span data-stu-id="0d65d-131">console</span></span>](#console)             | <span data-ttu-id="0d65d-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0d65d-132">[C#], F#, VB</span></span> | <span data-ttu-id="0d65d-133">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="0d65d-133">Common/Console</span></span>                        | <span data-ttu-id="0d65d-134">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-134">1.0</span></span>        |
| <span data-ttu-id="0d65d-135">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-135">Class library</span></span>                                | [<span data-ttu-id="0d65d-136">classlib</span><span class="sxs-lookup"><span data-stu-id="0d65d-136">classlib</span></span>](#classlib)           | <span data-ttu-id="0d65d-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0d65d-137">[C#], F#, VB</span></span> | <span data-ttu-id="0d65d-138">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-138">Common/Library</span></span>                        | <span data-ttu-id="0d65d-139">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-139">1.0</span></span>        |
| <span data-ttu-id="0d65d-140">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="0d65d-140">WPF Application</span></span>                              | [<span data-ttu-id="0d65d-141">wpf</span><span class="sxs-lookup"><span data-stu-id="0d65d-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="0d65d-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-142">[C#]</span></span>         | <span data-ttu-id="0d65d-143">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="0d65d-143">Common/WPF</span></span>                            | <span data-ttu-id="0d65d-144">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-144">3.0</span></span>        |
| <span data-ttu-id="0d65d-145">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-145">WPF Class library</span></span>                            | [<span data-ttu-id="0d65d-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="0d65d-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="0d65d-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-147">[C#]</span></span>         | <span data-ttu-id="0d65d-148">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="0d65d-148">Common/WPF</span></span>                            | <span data-ttu-id="0d65d-149">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-149">3.0</span></span>        |
| <span data-ttu-id="0d65d-150">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="0d65d-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="0d65d-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="0d65d-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-152">[C#]</span></span>         | <span data-ttu-id="0d65d-153">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="0d65d-153">Common/WPF</span></span>                            | <span data-ttu-id="0d65d-154">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-154">3.0</span></span>        |
| <span data-ttu-id="0d65d-155">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="0d65d-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="0d65d-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="0d65d-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-157">[C#]</span></span>         | <span data-ttu-id="0d65d-158">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="0d65d-158">Common/WPF</span></span>                            | <span data-ttu-id="0d65d-159">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-159">3.0</span></span>        |
| <span data-ttu-id="0d65d-160">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="0d65d-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="0d65d-161">winforms</span><span class="sxs-lookup"><span data-stu-id="0d65d-161">winforms</span></span>](#winforms)           | <span data-ttu-id="0d65d-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-162">[C#]</span></span>         | <span data-ttu-id="0d65d-163">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="0d65d-163">Common/WinForms</span></span>                       | <span data-ttu-id="0d65d-164">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-164">3.0</span></span>        |
| <span data-ttu-id="0d65d-165">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="0d65d-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="0d65d-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="0d65d-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-167">[C#]</span></span>         | <span data-ttu-id="0d65d-168">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="0d65d-168">Common/WinForms</span></span>                       | <span data-ttu-id="0d65d-169">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-169">3.0</span></span>        |
| <span data-ttu-id="0d65d-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="0d65d-170">Worker Service</span></span>                               | [<span data-ttu-id="0d65d-171">worker</span><span class="sxs-lookup"><span data-stu-id="0d65d-171">worker</span></span>](#web-others)           | <span data-ttu-id="0d65d-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-172">[C#]</span></span>         | <span data-ttu-id="0d65d-173">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="0d65d-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="0d65d-174">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-174">3.0</span></span>        |
| <span data-ttu-id="0d65d-175">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="0d65d-175">Unit Test Project</span></span>                            | [<span data-ttu-id="0d65d-176">mstest</span><span class="sxs-lookup"><span data-stu-id="0d65d-176">mstest</span></span>](#test)                 | <span data-ttu-id="0d65d-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0d65d-177">[C#], F#, VB</span></span> | <span data-ttu-id="0d65d-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="0d65d-178">Test/MSTest</span></span>                           | <span data-ttu-id="0d65d-179">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-179">1.0</span></span>        |
| <span data-ttu-id="0d65d-180">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="0d65d-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="0d65d-181">nunit</span><span class="sxs-lookup"><span data-stu-id="0d65d-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="0d65d-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0d65d-182">[C#], F#, VB</span></span> | <span data-ttu-id="0d65d-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="0d65d-183">Test/NUnit</span></span>                            | <span data-ttu-id="0d65d-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="0d65d-184">2.1.400</span></span>    |
| <span data-ttu-id="0d65d-185">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="0d65d-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="0d65d-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0d65d-186">[C#], F#, VB</span></span> | <span data-ttu-id="0d65d-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="0d65d-187">Test/NUnit</span></span>                            | <span data-ttu-id="0d65d-188">2.2</span><span class="sxs-lookup"><span data-stu-id="0d65d-188">2.2</span></span>        |
| <span data-ttu-id="0d65d-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="0d65d-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="0d65d-190">xunit</span><span class="sxs-lookup"><span data-stu-id="0d65d-190">xunit</span></span>](#test)                  | <span data-ttu-id="0d65d-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0d65d-191">[C#], F#, VB</span></span> | <span data-ttu-id="0d65d-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="0d65d-192">Test/xUnit</span></span>                            | <span data-ttu-id="0d65d-193">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-193">1.0</span></span>        |
| <span data-ttu-id="0d65d-194">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0d65d-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="0d65d-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-195">[C#]</span></span>         | <span data-ttu-id="0d65d-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0d65d-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="0d65d-197">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-197">3.0</span></span>        |
| <span data-ttu-id="0d65d-198">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="0d65d-198">Razor Page</span></span>                                   | [<span data-ttu-id="0d65d-199">page</span><span class="sxs-lookup"><span data-stu-id="0d65d-199">page</span></span>](#page)                   | <span data-ttu-id="0d65d-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-200">[C#]</span></span>         | <span data-ttu-id="0d65d-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0d65d-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="0d65d-202">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-202">2.0</span></span>        |
| <span data-ttu-id="0d65d-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="0d65d-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="0d65d-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="0d65d-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="0d65d-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-205">[C#]</span></span>         | <span data-ttu-id="0d65d-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0d65d-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="0d65d-207">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-207">2.0</span></span>        |
| <span data-ttu-id="0d65d-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0d65d-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="0d65d-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-209">[C#]</span></span>         | <span data-ttu-id="0d65d-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0d65d-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="0d65d-211">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-211">2.0</span></span>        |
| <span data-ttu-id="0d65d-212">Blazor 서버 앱</span><span class="sxs-lookup"><span data-stu-id="0d65d-212">Blazor Server App</span></span>                            | [<span data-ttu-id="0d65d-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="0d65d-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="0d65d-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-214">[C#]</span></span>         | <span data-ttu-id="0d65d-215">웹/Blazor</span><span class="sxs-lookup"><span data-stu-id="0d65d-215">Web/Blazor</span></span>                            | <span data-ttu-id="0d65d-216">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-216">3.0</span></span>        |
| <span data-ttu-id="0d65d-217">Blazor WebAssembly 앱</span><span class="sxs-lookup"><span data-stu-id="0d65d-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="0d65d-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-218">[C#]</span></span>         | <span data-ttu-id="0d65d-219">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="0d65d-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="0d65d-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="0d65d-220">3.1.300</span></span>    |
| <span data-ttu-id="0d65d-221">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="0d65d-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="0d65d-222">web</span><span class="sxs-lookup"><span data-stu-id="0d65d-222">web</span></span>](#web)                     | <span data-ttu-id="0d65d-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0d65d-223">[C#], F#</span></span>     | <span data-ttu-id="0d65d-224">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="0d65d-224">Web/Empty</span></span>                             | <span data-ttu-id="0d65d-225">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-225">1.0</span></span>        |
| <span data-ttu-id="0d65d-226">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="0d65d-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="0d65d-227">mvc</span><span class="sxs-lookup"><span data-stu-id="0d65d-227">mvc</span></span>](#web-options)             | <span data-ttu-id="0d65d-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0d65d-228">[C#], F#</span></span>     | <span data-ttu-id="0d65d-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="0d65d-229">Web/MVC</span></span>                               | <span data-ttu-id="0d65d-230">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-230">1.0</span></span>        |
| <span data-ttu-id="0d65d-231">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="0d65d-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="0d65d-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="0d65d-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="0d65d-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-233">[C#]</span></span>         | <span data-ttu-id="0d65d-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="0d65d-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="0d65d-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="0d65d-236">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="0d65d-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="0d65d-237">angular</span><span class="sxs-lookup"><span data-stu-id="0d65d-237">angular</span></span>](#spa)                 | <span data-ttu-id="0d65d-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-238">[C#]</span></span>         | <span data-ttu-id="0d65d-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="0d65d-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="0d65d-240">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-240">2.0</span></span>        |
| <span data-ttu-id="0d65d-241">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="0d65d-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="0d65d-242">react</span><span class="sxs-lookup"><span data-stu-id="0d65d-242">react</span></span>](#spa)                   | <span data-ttu-id="0d65d-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-243">[C#]</span></span>         | <span data-ttu-id="0d65d-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="0d65d-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="0d65d-245">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-245">2.0</span></span>        |
| <span data-ttu-id="0d65d-246">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="0d65d-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="0d65d-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="0d65d-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="0d65d-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-248">[C#]</span></span>         | <span data-ttu-id="0d65d-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="0d65d-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="0d65d-250">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-250">2.0</span></span>        |
| <span data-ttu-id="0d65d-251">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-251">Razor Class Library</span></span>                          | [<span data-ttu-id="0d65d-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="0d65d-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="0d65d-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-253">[C#]</span></span>         | <span data-ttu-id="0d65d-254">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0d65d-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="0d65d-255">2.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-255">2.1</span></span>        |
| <span data-ttu-id="0d65d-256">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="0d65d-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="0d65d-257">webapi</span><span class="sxs-lookup"><span data-stu-id="0d65d-257">webapi</span></span>](#webapi)               | <span data-ttu-id="0d65d-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0d65d-258">[C#], F#</span></span>     | <span data-ttu-id="0d65d-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="0d65d-259">Web/WebAPI</span></span>                            | <span data-ttu-id="0d65d-260">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-260">1.0</span></span>        |
| <span data-ttu-id="0d65d-261">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="0d65d-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="0d65d-262">grpc</span><span class="sxs-lookup"><span data-stu-id="0d65d-262">grpc</span></span>](#web-others)             | <span data-ttu-id="0d65d-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="0d65d-263">[C#]</span></span>         | <span data-ttu-id="0d65d-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="0d65d-264">Web/gRPC</span></span>                              | <span data-ttu-id="0d65d-265">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-265">3.0</span></span>        |
| <span data-ttu-id="0d65d-266">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="0d65d-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="0d65d-267">Config</span><span class="sxs-lookup"><span data-stu-id="0d65d-267">Config</span></span>                                | <span data-ttu-id="0d65d-268">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-268">3.0</span></span>        |
| <span data-ttu-id="0d65d-269">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="0d65d-269">global.json file</span></span>                             | [<span data-ttu-id="0d65d-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="0d65d-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="0d65d-271">Config</span><span class="sxs-lookup"><span data-stu-id="0d65d-271">Config</span></span>                                | <span data-ttu-id="0d65d-272">2.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-272">2.0</span></span>        |
| <span data-ttu-id="0d65d-273">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="0d65d-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="0d65d-274">Config</span><span class="sxs-lookup"><span data-stu-id="0d65d-274">Config</span></span>                                | <span data-ttu-id="0d65d-275">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-275">1.0</span></span>        |
| <span data-ttu-id="0d65d-276">Dotnet 로컬 도구 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="0d65d-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="0d65d-277">Config</span><span class="sxs-lookup"><span data-stu-id="0d65d-277">Config</span></span>                                | <span data-ttu-id="0d65d-278">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-278">3.0</span></span>        |
| <span data-ttu-id="0d65d-279">웹 구성</span><span class="sxs-lookup"><span data-stu-id="0d65d-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="0d65d-280">Config</span><span class="sxs-lookup"><span data-stu-id="0d65d-280">Config</span></span>                                | <span data-ttu-id="0d65d-281">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-281">1.0</span></span>        |
| <span data-ttu-id="0d65d-282">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="0d65d-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="0d65d-283">솔루션</span><span class="sxs-lookup"><span data-stu-id="0d65d-283">Solution</span></span>                              | <span data-ttu-id="0d65d-284">1.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-284">1.0</span></span>        |
| <span data-ttu-id="0d65d-285">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="0d65d-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="0d65d-286">proto</span><span class="sxs-lookup"><span data-stu-id="0d65d-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="0d65d-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="0d65d-287">Web/gRPC</span></span>                              | <span data-ttu-id="0d65d-288">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="0d65d-289">옵션</span><span class="sxs-lookup"><span data-stu-id="0d65d-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="0d65d-290">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="0d65d-291">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="0d65d-292">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0d65d-293">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0d65d-294">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-294">Prints out help for the command.</span></span> <span data-ttu-id="0d65d-295">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="0d65d-296">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="0d65d-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="0d65d-297">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0d65d-298">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="0d65d-299">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="0d65d-300">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="0d65d-301">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="0d65d-302">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="0d65d-303">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="0d65d-304">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="0d65d-305">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-305">The language of the template to create.</span></span> <span data-ttu-id="0d65d-306">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="0d65d-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0d65d-307">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0d65d-308">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="0d65d-309">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="0d65d-310">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="0d65d-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="0d65d-311">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-311">The name for the created output.</span></span> <span data-ttu-id="0d65d-312">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="0d65d-313">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="0d65d-314">.NET Core 2.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="0d65d-315">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-315">Location to place the generated output.</span></span> <span data-ttu-id="0d65d-316">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="0d65d-317">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-317">Filters templates based on available types.</span></span> <span data-ttu-id="0d65d-318">미리 정의된 값은 `project`, `item` 및 `other`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="0d65d-319">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0d65d-320">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="0d65d-321">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="0d65d-322">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0d65d-323">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="0d65d-324">예를 들어 *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="0d65d-325">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="0d65d-326">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="0d65d-327">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="0d65d-328">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="0d65d-329">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="0d65d-330">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="0d65d-330">Template options</span></span>

<span data-ttu-id="0d65d-331">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-331">Each project template may have additional options available.</span></span> <span data-ttu-id="0d65d-332">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="0d65d-333">콘솔</span><span class="sxs-lookup"><span data-stu-id="0d65d-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-334">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-335">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="0d65d-336">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-337">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-337">SDK version</span></span> | <span data-ttu-id="0d65d-338">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-339">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-340">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="0d65d-341">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="0d65d-342">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="0d65d-343">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-343">Not supported for F#.</span></span> <span data-ttu-id="0d65d-344">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="0d65d-345">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-346">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="0d65d-347">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="0d65d-348">classlib</span><span class="sxs-lookup"><span data-stu-id="0d65d-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-349">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-350">값: `netcoreapp<version>`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="0d65d-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0d65d-351">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="0d65d-352">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="0d65d-353">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="0d65d-354">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-354">Not supported for F#.</span></span> <span data-ttu-id="0d65d-355">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="0d65d-356">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-357">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="0d65d-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="0d65d-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-359">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-360">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="0d65d-361">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="0d65d-362">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="0d65d-363">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="0d65d-364">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-365">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="0d65d-366">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="0d65d-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="0d65d-367">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="0d65d-368">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="0d65d-369">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-370">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="0d65d-371">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="0d65d-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-372">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-373">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="0d65d-374">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-375">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-376">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="0d65d-377">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="0d65d-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-378">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-379">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="0d65d-380">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-381">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-381">SDK version</span></span> | <span data-ttu-id="0d65d-382">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-383">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-384">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="0d65d-385">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-386">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="0d65d-387">nunit</span><span class="sxs-lookup"><span data-stu-id="0d65d-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-388">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="0d65d-389">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-390">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-390">SDK version</span></span> | <span data-ttu-id="0d65d-391">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-392">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-393">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="0d65d-394">2.2</span><span class="sxs-lookup"><span data-stu-id="0d65d-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="0d65d-395">2.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="0d65d-396">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-397">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="0d65d-398">페이지</span><span class="sxs-lookup"><span data-stu-id="0d65d-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="0d65d-399">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-399">Namespace for the generated code.</span></span> <span data-ttu-id="0d65d-400">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="0d65d-401">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="0d65d-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="0d65d-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="0d65d-403">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-403">Namespace for the generated code.</span></span> <span data-ttu-id="0d65d-404">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="0d65d-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="0d65d-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="0d65d-406">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-406">The type of authentication to use.</span></span> <span data-ttu-id="0d65d-407">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-407">The possible values are:</span></span>

  - <span data-ttu-id="0d65d-408">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="0d65d-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="0d65d-409">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="0d65d-410">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="0d65d-411">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="0d65d-412">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="0d65d-413">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="0d65d-414">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0d65d-415">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-416">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="0d65d-417">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0d65d-418">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="0d65d-419">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="0d65d-420">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="0d65d-421">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="0d65d-422">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="0d65d-423">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0d65d-424">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0d65d-425">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="0d65d-426">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-426">The Client ID for this project.</span></span> <span data-ttu-id="0d65d-427">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0d65d-428">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="0d65d-429">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-429">The domain for the directory tenant.</span></span> <span data-ttu-id="0d65d-430">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-431">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="0d65d-432">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0d65d-433">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0d65d-434">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="0d65d-435">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0d65d-436">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-437">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="0d65d-438">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="0d65d-439">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-440">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="0d65d-441">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-441">Turns off HTTPS.</span></span> <span data-ttu-id="0d65d-442">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="0d65d-443">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0d65d-444">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-445">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="0d65d-446">웹</span><span class="sxs-lookup"><span data-stu-id="0d65d-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-447">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-448">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-449">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="0d65d-450">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-451">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-451">SDK version</span></span> | <span data-ttu-id="0d65d-452">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-453">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-454">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="0d65d-455">2.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="0d65d-456">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="0d65d-457">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="0d65d-458">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="0d65d-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="0d65d-459">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-459">The type of authentication to use.</span></span> <span data-ttu-id="0d65d-460">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-460">The possible values are:</span></span>

  - <span data-ttu-id="0d65d-461">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="0d65d-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="0d65d-462">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="0d65d-463">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="0d65d-464">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="0d65d-465">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="0d65d-466">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="0d65d-467">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0d65d-468">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-469">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="0d65d-470">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0d65d-471">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="0d65d-472">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="0d65d-473">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="0d65d-474">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="0d65d-475">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="0d65d-476">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0d65d-477">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0d65d-478">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="0d65d-479">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-479">The Client ID for this project.</span></span> <span data-ttu-id="0d65d-480">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0d65d-481">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="0d65d-482">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-482">The domain for the directory tenant.</span></span> <span data-ttu-id="0d65d-483">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-484">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="0d65d-485">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0d65d-486">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0d65d-487">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="0d65d-488">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0d65d-489">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-490">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="0d65d-491">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="0d65d-492">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-493">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="0d65d-494">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-494">Turns off HTTPS.</span></span> <span data-ttu-id="0d65d-495">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="0d65d-496">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0d65d-497">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-498">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-499">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="0d65d-500">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-501">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-501">SDK version</span></span> | <span data-ttu-id="0d65d-502">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-503">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-504">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="0d65d-505">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="0d65d-506">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="0d65d-507">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="0d65d-508">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="0d65d-509">.NET Core 3.1.201 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="0d65d-510">angular, react</span><span class="sxs-lookup"><span data-stu-id="0d65d-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="0d65d-511">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-511">The type of authentication to use.</span></span> <span data-ttu-id="0d65d-512">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="0d65d-513">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-513">The possible values are:</span></span>

  - <span data-ttu-id="0d65d-514">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="0d65d-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="0d65d-515">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-516">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-517">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="0d65d-518">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-518">Turns off HTTPS.</span></span> <span data-ttu-id="0d65d-519">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="0d65d-520">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0d65d-521">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-522">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-523">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-524">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="0d65d-525">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-526">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-526">SDK version</span></span> | <span data-ttu-id="0d65d-527">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-528">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-529">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="0d65d-530">2.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="0d65d-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="0d65d-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-532">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-533">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-534">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="0d65d-535">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-536">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-536">SDK version</span></span> | <span data-ttu-id="0d65d-537">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-538">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-539">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="0d65d-540">2.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="0d65d-541">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="0d65d-542">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="0d65d-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="0d65d-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="0d65d-544">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="0d65d-545">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="0d65d-546">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="0d65d-547">webapi</span><span class="sxs-lookup"><span data-stu-id="0d65d-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="0d65d-548">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-548">The type of authentication to use.</span></span> <span data-ttu-id="0d65d-549">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-549">The possible values are:</span></span>

  - <span data-ttu-id="0d65d-550">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="0d65d-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="0d65d-551">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="0d65d-552">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="0d65d-553">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="0d65d-554">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0d65d-555">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0d65d-556">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="0d65d-557">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0d65d-558">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="0d65d-559">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0d65d-560">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0d65d-561">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="0d65d-562">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-562">The Client ID for this project.</span></span> <span data-ttu-id="0d65d-563">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0d65d-564">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="0d65d-565">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-565">The domain for the directory tenant.</span></span> <span data-ttu-id="0d65d-566">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0d65d-567">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="0d65d-568">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0d65d-569">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0d65d-570">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="0d65d-571">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="0d65d-572">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="0d65d-573">생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="0d65d-574">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-574">Turns off HTTPS.</span></span> <span data-ttu-id="0d65d-575">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="0d65d-576">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="0d65d-577">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0d65d-578">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0d65d-579">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0d65d-580">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="0d65d-581">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="0d65d-582">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="0d65d-582">SDK version</span></span> | <span data-ttu-id="0d65d-583">기본값</span><span class="sxs-lookup"><span data-stu-id="0d65d-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="0d65d-584">3.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="0d65d-585">3.0</span><span class="sxs-lookup"><span data-stu-id="0d65d-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="0d65d-586">2.1</span><span class="sxs-lookup"><span data-stu-id="0d65d-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="0d65d-587">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="0d65d-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="0d65d-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="0d65d-589">*global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="0d65d-590">예</span><span class="sxs-lookup"><span data-stu-id="0d65d-590">Examples</span></span>

- <span data-ttu-id="0d65d-591">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="0d65d-592">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="0d65d-593">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="0d65d-594">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="0d65d-595">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="0d65d-596">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="0d65d-597">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="0d65d-598">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="0d65d-599">*ng*와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="0d65d-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="0d65d-600">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="0d65d-601">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="0d65d-602">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="0d65d-603">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d65d-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="0d65d-604">참조</span><span class="sxs-lookup"><span data-stu-id="0d65d-604">See also</span></span>

- [<span data-ttu-id="0d65d-605">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d65d-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="0d65d-606">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="0d65d-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="0d65d-607">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="0d65d-607">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="0d65d-608">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="0d65d-608">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
