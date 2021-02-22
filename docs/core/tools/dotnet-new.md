---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET 프로젝트를 만듭니다.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: acaaf025555c46f720452b8c9d4f875b8656125a
ms.sourcegitcommit: b924ade6426cf61a4604c4e2ee54cb3592c29317
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "101096815"
---
# <a name="dotnet-new"></a><span data-ttu-id="66cc7-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="66cc7-103">dotnet new</span></span>

<span data-ttu-id="66cc7-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="66cc7-105">이름</span><span class="sxs-lookup"><span data-stu-id="66cc7-105">Name</span></span>

<span data-ttu-id="66cc7-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="66cc7-107">개요</span><span class="sxs-lookup"><span data-stu-id="66cc7-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="66cc7-108">설명</span><span class="sxs-lookup"><span data-stu-id="66cc7-108">Description</span></span>

<span data-ttu-id="66cc7-109">`dotnet new` 명령은 템플릿을 기반으로 .NET 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="66cc7-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="66cc7-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="66cc7-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="66cc7-112">인수</span><span class="sxs-lookup"><span data-stu-id="66cc7-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="66cc7-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="66cc7-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="66cc7-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="66cc7-116">`dotnet new --list` 또는 `dotnet new -l`을 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="66cc7-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="66cc7-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="66cc7-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="66cc7-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="66cc7-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="66cc7-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="66cc7-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="66cc7-122">다음 표에는 .NET SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="66cc7-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="66cc7-124">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="66cc7-125">템플릿</span><span class="sxs-lookup"><span data-stu-id="66cc7-125">Templates</span></span>                                    | <span data-ttu-id="66cc7-126">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="66cc7-126">Short name</span></span>                        | <span data-ttu-id="66cc7-127">언어</span><span class="sxs-lookup"><span data-stu-id="66cc7-127">Language</span></span>     | <span data-ttu-id="66cc7-128">Tags</span><span class="sxs-lookup"><span data-stu-id="66cc7-128">Tags</span></span>                                  | <span data-ttu-id="66cc7-129">도입</span><span class="sxs-lookup"><span data-stu-id="66cc7-129">Introduced</span></span> |
|----------------------------------------------|-----------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="66cc7-130">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="66cc7-130">Console Application</span></span>                          | [`console`](#console)             | <span data-ttu-id="66cc7-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-131">[C#], F#, VB</span></span> | <span data-ttu-id="66cc7-132">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="66cc7-132">Common/Console</span></span>                        | <span data-ttu-id="66cc7-133">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-133">1.0</span></span>        |
| <span data-ttu-id="66cc7-134">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-134">Class library</span></span>                                | [`classlib`](#classlib)           | <span data-ttu-id="66cc7-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-135">[C#], F#, VB</span></span> | <span data-ttu-id="66cc7-136">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-136">Common/Library</span></span>                        | <span data-ttu-id="66cc7-137">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-137">1.0</span></span>        |
| <span data-ttu-id="66cc7-138">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="66cc7-138">WPF Application</span></span>                              | [`wpf`](#wpf)                     | <span data-ttu-id="66cc7-139">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-139">[C#], VB</span></span>     | <span data-ttu-id="66cc7-140">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="66cc7-140">Common/WPF</span></span>                            | <span data-ttu-id="66cc7-141">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="66cc7-141">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="66cc7-142">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-142">WPF Class library</span></span>                            | [`wpflib`](#wpf)                  | <span data-ttu-id="66cc7-143">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-143">[C#], VB</span></span>     | <span data-ttu-id="66cc7-144">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="66cc7-144">Common/WPF</span></span>                            | <span data-ttu-id="66cc7-145">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="66cc7-145">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="66cc7-146">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-146">WPF Custom Control Library</span></span>                   | [`wpfcustomcontrollib`](#wpf)     | <span data-ttu-id="66cc7-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-147">[C#], VB</span></span>     | <span data-ttu-id="66cc7-148">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="66cc7-148">Common/WPF</span></span>                            | <span data-ttu-id="66cc7-149">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="66cc7-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="66cc7-150">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-150">WPF User Control Library</span></span>                     | [`wpfusercontrollib`](#wpf)       | <span data-ttu-id="66cc7-151">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-151">[C#], VB</span></span>     | <span data-ttu-id="66cc7-152">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="66cc7-152">Common/WPF</span></span>                            | <span data-ttu-id="66cc7-153">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="66cc7-153">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="66cc7-154">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="66cc7-154">Windows Forms (WinForms) Application</span></span>         | [`winforms`](#winforms)           | <span data-ttu-id="66cc7-155">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-155">[C#], VB</span></span>     | <span data-ttu-id="66cc7-156">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="66cc7-156">Common/WinForms</span></span>                       | <span data-ttu-id="66cc7-157">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="66cc7-157">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="66cc7-158">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-158">Windows Forms (WinForms) Class library</span></span>       | [`winformslib`](#winforms)        | <span data-ttu-id="66cc7-159">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-159">[C#], VB</span></span>     | <span data-ttu-id="66cc7-160">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="66cc7-160">Common/WinForms</span></span>                       | <span data-ttu-id="66cc7-161">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="66cc7-161">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="66cc7-162">Worker Service</span><span class="sxs-lookup"><span data-stu-id="66cc7-162">Worker Service</span></span>                               | [`worker`](#web-others)           | <span data-ttu-id="66cc7-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-163">[C#]</span></span>         | <span data-ttu-id="66cc7-164">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="66cc7-164">Common/Worker/Web</span></span>                     | <span data-ttu-id="66cc7-165">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-165">3.0</span></span>        |
| <span data-ttu-id="66cc7-166">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="66cc7-166">Unit Test Project</span></span>                            | [`mstest`](#test)                 | <span data-ttu-id="66cc7-167">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-167">[C#], F#, VB</span></span> | <span data-ttu-id="66cc7-168">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="66cc7-168">Test/MSTest</span></span>                           | <span data-ttu-id="66cc7-169">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-169">1.0</span></span>        |
| <span data-ttu-id="66cc7-170">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="66cc7-170">NUnit 3 Test Project</span></span>                         | [`nunit`](#nunit)                 | <span data-ttu-id="66cc7-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-171">[C#], F#, VB</span></span> | <span data-ttu-id="66cc7-172">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="66cc7-172">Test/NUnit</span></span>                            | <span data-ttu-id="66cc7-173">2.1.400</span><span class="sxs-lookup"><span data-stu-id="66cc7-173">2.1.400</span></span>    |
| <span data-ttu-id="66cc7-174">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="66cc7-174">NUnit 3 Test Item</span></span>                            | `nunit-test`                      | <span data-ttu-id="66cc7-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-175">[C#], F#, VB</span></span> | <span data-ttu-id="66cc7-176">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="66cc7-176">Test/NUnit</span></span>                            | <span data-ttu-id="66cc7-177">2.2</span><span class="sxs-lookup"><span data-stu-id="66cc7-177">2.2</span></span>        |
| <span data-ttu-id="66cc7-178">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="66cc7-178">xUnit Test Project</span></span>                           | [`xunit`](#test)                  | <span data-ttu-id="66cc7-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="66cc7-179">[C#], F#, VB</span></span> | <span data-ttu-id="66cc7-180">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="66cc7-180">Test/xUnit</span></span>                            | <span data-ttu-id="66cc7-181">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-181">1.0</span></span>        |
| <span data-ttu-id="66cc7-182">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="66cc7-182">Razor Component</span></span>                              | `razorcomponent`                  | <span data-ttu-id="66cc7-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-183">[C#]</span></span>         | <span data-ttu-id="66cc7-184">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="66cc7-184">Web/ASP.NET</span></span>                           | <span data-ttu-id="66cc7-185">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-185">3.0</span></span>        |
| <span data-ttu-id="66cc7-186">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="66cc7-186">Razor Page</span></span>                                   | [`page`](#page)                   | <span data-ttu-id="66cc7-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-187">[C#]</span></span>         | <span data-ttu-id="66cc7-188">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="66cc7-188">Web/ASP.NET</span></span>                           | <span data-ttu-id="66cc7-189">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-189">2.0</span></span>        |
| <span data-ttu-id="66cc7-190">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="66cc7-190">MVC ViewImports</span></span>                              | [`viewimports`](#namespace)       | <span data-ttu-id="66cc7-191">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-191">[C#]</span></span>         | <span data-ttu-id="66cc7-192">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="66cc7-192">Web/ASP.NET</span></span>                           | <span data-ttu-id="66cc7-193">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-193">2.0</span></span>        |
| <span data-ttu-id="66cc7-194">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="66cc7-194">MVC ViewStart</span></span>                                | `viewstart`                       | <span data-ttu-id="66cc7-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-195">[C#]</span></span>         | <span data-ttu-id="66cc7-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="66cc7-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="66cc7-197">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-197">2.0</span></span>        |
| <span data-ttu-id="66cc7-198">Blazor 서버 앱</span><span class="sxs-lookup"><span data-stu-id="66cc7-198">Blazor Server App</span></span>                            | [`blazorserver`](#blazorserver)   | <span data-ttu-id="66cc7-199">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-199">[C#]</span></span>         | <span data-ttu-id="66cc7-200">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="66cc7-200">Web/Blazor</span></span>                            | <span data-ttu-id="66cc7-201">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-201">3.0</span></span>        |
| <span data-ttu-id="66cc7-202">Blazor WebAssembly 앱</span><span class="sxs-lookup"><span data-stu-id="66cc7-202">Blazor WebAssembly App</span></span>                       | [`blazorwasm`](#blazorwasm)       | <span data-ttu-id="66cc7-203">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-203">[C#]</span></span>         | <span data-ttu-id="66cc7-204">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="66cc7-204">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="66cc7-205">3.1.300</span><span class="sxs-lookup"><span data-stu-id="66cc7-205">3.1.300</span></span>    |
| <span data-ttu-id="66cc7-206">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="66cc7-206">ASP.NET Core Empty</span></span>                           | [`web`](#web)                     | <span data-ttu-id="66cc7-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="66cc7-207">[C#], F#</span></span>     | <span data-ttu-id="66cc7-208">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="66cc7-208">Web/Empty</span></span>                             | <span data-ttu-id="66cc7-209">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-209">1.0</span></span>        |
| <span data-ttu-id="66cc7-210">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="66cc7-210">ASP.NET Core Web App (Model-View-Controller)</span></span> | [`mvc`](#web-options)             | <span data-ttu-id="66cc7-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="66cc7-211">[C#], F#</span></span>     | <span data-ttu-id="66cc7-212">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="66cc7-212">Web/MVC</span></span>                               | <span data-ttu-id="66cc7-213">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-213">1.0</span></span>        |
| <span data-ttu-id="66cc7-214">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="66cc7-214">ASP.NET Core Web App</span></span>                         | [`webapp, razor`](#web-options)   | <span data-ttu-id="66cc7-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-215">[C#]</span></span>         | <span data-ttu-id="66cc7-216">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="66cc7-216">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="66cc7-217">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-217">2.2, 2.0</span></span>   |
| <span data-ttu-id="66cc7-218">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="66cc7-218">ASP.NET Core with Angular</span></span>                    | [`angular`](#spa)                 | <span data-ttu-id="66cc7-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-219">[C#]</span></span>         | <span data-ttu-id="66cc7-220">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="66cc7-220">Web/MVC/SPA</span></span>                           | <span data-ttu-id="66cc7-221">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-221">2.0</span></span>        |
| <span data-ttu-id="66cc7-222">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="66cc7-222">ASP.NET Core with React.js</span></span>                   | [`react`](#spa)                   | <span data-ttu-id="66cc7-223">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-223">[C#]</span></span>         | <span data-ttu-id="66cc7-224">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="66cc7-224">Web/MVC/SPA</span></span>                           | <span data-ttu-id="66cc7-225">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-225">2.0</span></span>        |
| <span data-ttu-id="66cc7-226">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="66cc7-226">ASP.NET Core with React.js and Redux</span></span>         | [`reactredux`](#reactredux)       | <span data-ttu-id="66cc7-227">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-227">[C#]</span></span>         | <span data-ttu-id="66cc7-228">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="66cc7-228">Web/MVC/SPA</span></span>                           | <span data-ttu-id="66cc7-229">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-229">2.0</span></span>        |
| <span data-ttu-id="66cc7-230">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-230">Razor Class Library</span></span>                          | [`razorclasslib`](#razorclasslib) | <span data-ttu-id="66cc7-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-231">[C#]</span></span>         | <span data-ttu-id="66cc7-232">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="66cc7-232">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="66cc7-233">2.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-233">2.1</span></span>        |
| <span data-ttu-id="66cc7-234">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="66cc7-234">ASP.NET Core Web API</span></span>                         | [`webapi`](#webapi)               | <span data-ttu-id="66cc7-235">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="66cc7-235">[C#], F#</span></span>     | <span data-ttu-id="66cc7-236">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="66cc7-236">Web/WebAPI</span></span>                            | <span data-ttu-id="66cc7-237">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-237">1.0</span></span>        |
| <span data-ttu-id="66cc7-238">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="66cc7-238">ASP.NET Core gRPC Service</span></span>                    | [`grpc`](#web-others)             | <span data-ttu-id="66cc7-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="66cc7-239">[C#]</span></span>         | <span data-ttu-id="66cc7-240">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="66cc7-240">Web/gRPC</span></span>                              | <span data-ttu-id="66cc7-241">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-241">3.0</span></span>        |
| <span data-ttu-id="66cc7-242">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="66cc7-242">dotnet gitignore file</span></span>                        | `gitignore`                       |              | <span data-ttu-id="66cc7-243">Config</span><span class="sxs-lookup"><span data-stu-id="66cc7-243">Config</span></span>                                | <span data-ttu-id="66cc7-244">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-244">3.0</span></span>        |
| <span data-ttu-id="66cc7-245">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="66cc7-245">global.json file</span></span>                             | [`globaljson`](#globaljson)       |              | <span data-ttu-id="66cc7-246">Config</span><span class="sxs-lookup"><span data-stu-id="66cc7-246">Config</span></span>                                | <span data-ttu-id="66cc7-247">2.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-247">2.0</span></span>        |
| <span data-ttu-id="66cc7-248">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="66cc7-248">NuGet Config</span></span>                                 | `nugetconfig`                     |              | <span data-ttu-id="66cc7-249">Config</span><span class="sxs-lookup"><span data-stu-id="66cc7-249">Config</span></span>                                | <span data-ttu-id="66cc7-250">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-250">1.0</span></span>        |
| <span data-ttu-id="66cc7-251">Dotnet 로컬 도구 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="66cc7-251">Dotnet local tool manifest file</span></span>              | `tool-manifest`                   |              | <span data-ttu-id="66cc7-252">Config</span><span class="sxs-lookup"><span data-stu-id="66cc7-252">Config</span></span>                                | <span data-ttu-id="66cc7-253">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-253">3.0</span></span>        |
| <span data-ttu-id="66cc7-254">웹 구성</span><span class="sxs-lookup"><span data-stu-id="66cc7-254">Web Config</span></span>                                   | `webconfig`                       |              | <span data-ttu-id="66cc7-255">Config</span><span class="sxs-lookup"><span data-stu-id="66cc7-255">Config</span></span>                                | <span data-ttu-id="66cc7-256">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-256">1.0</span></span>        |
| <span data-ttu-id="66cc7-257">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="66cc7-257">Solution File</span></span>                                | `sln`                             |              | <span data-ttu-id="66cc7-258">솔루션</span><span class="sxs-lookup"><span data-stu-id="66cc7-258">Solution</span></span>                              | <span data-ttu-id="66cc7-259">1.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-259">1.0</span></span>        |
| <span data-ttu-id="66cc7-260">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="66cc7-260">Protocol Buffer File</span></span>                         | [`proto`](#namespace)             |              | <span data-ttu-id="66cc7-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="66cc7-261">Web/gRPC</span></span>                              | <span data-ttu-id="66cc7-262">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-262">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="66cc7-263">옵션</span><span class="sxs-lookup"><span data-stu-id="66cc7-263">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="66cc7-264">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-264">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="66cc7-265">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-265">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="66cc7-266">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-266">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="66cc7-267">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-267">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="66cc7-268">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-268">Prints out help for the command.</span></span> <span data-ttu-id="66cc7-269">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-269">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="66cc7-270">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="66cc7-270">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="66cc7-271">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-271">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="66cc7-272">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-272">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="66cc7-273">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-273">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="66cc7-274">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-274">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="66cc7-275">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-275">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="66cc7-276">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-276">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="66cc7-277">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-277">Lists templates containing the specified name.</span></span> <span data-ttu-id="66cc7-278">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-278">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="66cc7-279">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-279">The language of the template to create.</span></span> <span data-ttu-id="66cc7-280">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="66cc7-280">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="66cc7-281">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-281">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="66cc7-282">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-282">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="66cc7-283">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-283">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="66cc7-284">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="66cc7-284">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="66cc7-285">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-285">The name for the created output.</span></span> <span data-ttu-id="66cc7-286">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-286">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="66cc7-287">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-287">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="66cc7-288">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-288">Location to place the generated output.</span></span> <span data-ttu-id="66cc7-289">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-289">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="66cc7-290">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-290">Filters templates based on available types.</span></span> <span data-ttu-id="66cc7-291">미리 정의된 값은 `project` 및 `item`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-291">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="66cc7-292">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-292">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="66cc7-293">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-293">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="66cc7-294">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-294">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="66cc7-295">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-295">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="66cc7-296">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-296">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="66cc7-297">예를 들어 *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-297">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="66cc7-298">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-298">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="66cc7-299">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-299">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="66cc7-300">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-300">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="66cc7-301">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-301">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="66cc7-302">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-302">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="66cc7-303">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="66cc7-303">Template options</span></span>

<span data-ttu-id="66cc7-304">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-304">Each project template may have additional options available.</span></span> <span data-ttu-id="66cc7-305">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-305">The core templates have the following additional options:</span></span>

### `console`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-306">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-306">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-307">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-307">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="66cc7-308">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-308">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-309">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-309">SDK version</span></span> | <span data-ttu-id="66cc7-310">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-310">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-311">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-311">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-312">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-312">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-313">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-313">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="66cc7-314">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-314">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="66cc7-315">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-315">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="66cc7-316">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-316">Not supported for F#.</span></span> <span data-ttu-id="66cc7-317">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-317">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="66cc7-318">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-318">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-319">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-319">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="66cc7-320">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-320">Available since .NET Core 2.2 SDK.</span></span>

***

### `classlib`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-321">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-321">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-322">값: `net5.0`, `netcoreapp<version>`(.NET 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="66cc7-322">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="66cc7-323">.NET 5.0 SDK의 기본값은 `net5.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-323">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="66cc7-324">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-324">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="66cc7-325">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-325">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="66cc7-326">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-326">Not supported for F#.</span></span> <span data-ttu-id="66cc7-327">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-327">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="66cc7-328">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-328">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-329">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-329">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="66cc7-330">`wpf`, `wpflib`, `wpfcustomcontrollib`, `wpfusercontrollib`</span><span class="sxs-lookup"><span data-stu-id="66cc7-330">`wpf`, `wpflib`, `wpfcustomcontrollib`, `wpfusercontrollib`</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-331">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-332">기본값은 `net5.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-332">The default value is `net5.0`.</span></span> <span data-ttu-id="66cc7-333">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-333">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="66cc7-334">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-334">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="66cc7-335">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-335">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="66cc7-336">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-336">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-337">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-337">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="66cc7-338">`winforms`, `winformslib`</span><span class="sxs-lookup"><span data-stu-id="66cc7-338">`winforms`, `winformslib`</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="66cc7-339">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="66cc7-340">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="66cc7-341">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-342">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-342">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="66cc7-343">`worker`, `grpc`</span><span class="sxs-lookup"><span data-stu-id="66cc7-343">`worker`, `grpc`</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-344">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-344">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-345">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-345">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="66cc7-346">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-346">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-347">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-347">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-348">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-348">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="66cc7-349">`mstest`, `xunit`</span><span class="sxs-lookup"><span data-stu-id="66cc7-349">`mstest`, `xunit`</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-350">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-350">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-351">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-351">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="66cc7-352">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-352">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-353">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-353">SDK version</span></span> | <span data-ttu-id="66cc7-354">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-354">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-355">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-355">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-356">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-356">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-357">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-357">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="66cc7-358">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-358">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-359">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-359">Doesn't execute an implicit restore during project creation.</span></span>

***

### `nunit`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-360">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-360">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="66cc7-361">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-361">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-362">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-362">SDK version</span></span> | <span data-ttu-id="66cc7-363">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-363">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-364">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-364">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-365">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-365">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-366">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-366">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="66cc7-367">2.2</span><span class="sxs-lookup"><span data-stu-id="66cc7-367">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="66cc7-368">2.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-368">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="66cc7-369">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-369">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-370">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### `page`

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="66cc7-371">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-371">Namespace for the generated code.</span></span> <span data-ttu-id="66cc7-372">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-372">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="66cc7-373">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-373">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="66cc7-374">`viewimports`, `proto`</span><span class="sxs-lookup"><span data-stu-id="66cc7-374">`viewimports`, `proto`</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="66cc7-375">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-375">Namespace for the generated code.</span></span> <span data-ttu-id="66cc7-376">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-376">The default value is `MyApp.Namespace`.</span></span>

***

### `blazorserver`

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="66cc7-377">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-377">The type of authentication to use.</span></span> <span data-ttu-id="66cc7-378">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-378">The possible values are:</span></span>

  - <span data-ttu-id="66cc7-379">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="66cc7-379">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="66cc7-380">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-380">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="66cc7-381">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-381">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="66cc7-382">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-382">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="66cc7-383">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-383">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="66cc7-384">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-384">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-385">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-385">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="66cc7-386">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-386">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-387">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-387">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="66cc7-388">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-388">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="66cc7-389">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-389">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="66cc7-390">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-390">The reset password policy ID for this project.</span></span> <span data-ttu-id="66cc7-391">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-391">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="66cc7-392">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-392">The edit profile policy ID for this project.</span></span> <span data-ttu-id="66cc7-393">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-393">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-394">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-394">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="66cc7-395">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-395">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="66cc7-396">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-396">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="66cc7-397">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-397">The Client ID for this project.</span></span> <span data-ttu-id="66cc7-398">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-398">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="66cc7-399">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-399">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="66cc7-400">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-400">The domain for the directory tenant.</span></span> <span data-ttu-id="66cc7-401">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-401">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-402">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-402">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="66cc7-403">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-403">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="66cc7-404">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-404">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-405">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-405">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="66cc7-406">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-406">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="66cc7-407">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-407">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-408">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-408">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="66cc7-409">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-409">Allows this application read-access to the directory.</span></span> <span data-ttu-id="66cc7-410">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-410">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-411">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-411">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-412">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-412">Turns off HTTPS.</span></span> <span data-ttu-id="66cc7-413">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-413">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="66cc7-414">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-414">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="66cc7-415">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-415">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-416">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-416">Doesn't execute an implicit restore during project creation.</span></span>

***

### `blazorwasm`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-417">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-417">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="66cc7-418">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-418">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-419">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-419">SDK version</span></span> | <span data-ttu-id="66cc7-420">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-420">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-421">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-421">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-422">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-422">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="66cc7-423">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-423">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="66cc7-424">Blazor WebAssembly 앱의 ASP.NET Core 호스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-424">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="66cc7-425">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-425">The type of authentication to use.</span></span> <span data-ttu-id="66cc7-426">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-426">The possible values are:</span></span>

  - <span data-ttu-id="66cc7-427">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="66cc7-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="66cc7-428">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="66cc7-429">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="66cc7-430">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="66cc7-431">OIDC 공급자의 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-431">The authority of the OIDC provider.</span></span> <span data-ttu-id="66cc7-432">`Individual` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-432">Use with `Individual` authentication.</span></span> <span data-ttu-id="66cc7-433">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-433">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-434">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-434">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="66cc7-435">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-435">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-436">기본값은 `https://aadB2CInstance.b2clogin.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-436">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="66cc7-437">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-437">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="66cc7-438">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-438">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-439">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-439">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="66cc7-440">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-441">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-441">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="66cc7-442">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-442">The Client ID for this project.</span></span> <span data-ttu-id="66cc7-443">`IndividualB2C`, `SingleOrg` 또는 독립 실행형 시나리오의 경우 `Individual` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-443">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="66cc7-444">기본값은 `33333333-3333-3333-33333333333333333`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-444">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="66cc7-445">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-445">The domain for the directory tenant.</span></span> <span data-ttu-id="66cc7-446">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-446">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-447">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-447">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="66cc7-448">호출하려는 서버 API의 앱 ID URI입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-448">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="66cc7-449">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-450">기본값은 `api.id.uri`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-450">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="66cc7-451">서버가 호스트하는 API의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-451">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="66cc7-452">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-452">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-453">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-453">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="66cc7-454">클라이언트가 액세스 토큰 프로비전을 요청하는 데 필요한 API 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-454">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="66cc7-455">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-456">기본값은 `user_impersonation`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-456">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="66cc7-457">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-457">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="66cc7-458">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-458">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-459">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-459">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="66cc7-460">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-460">Allows this application read-access to the directory.</span></span> <span data-ttu-id="66cc7-461">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-461">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-462">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-462">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="66cc7-463">프로그레시브 웹 애플리케이션(PWA)을 생성하여 설치 및 오프라인 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-463">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-464">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-464">Turns off HTTPS.</span></span> <span data-ttu-id="66cc7-465">이 옵션은 `--auth`에 `Individual`, `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-465">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="66cc7-466">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-466">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="66cc7-467">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-467">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="66cc7-468">웹앱에서 호출할 API의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-468">URL of the API to call from the web app.</span></span> <span data-ttu-id="66cc7-469">ASP.NET Core 호스트가 지정되지 않은 `SingleOrg` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-469">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="66cc7-470">기본값은 `https://graph.microsoft.com/v1.0/me`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-470">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="66cc7-471">웹앱이 Microsoft Graph를 호출하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-471">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="66cc7-472">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-472">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="66cc7-473">웹앱에서 API를 호출하기 위해 요청할 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-473">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="66cc7-474">ASP.NET Core 호스트가 지정되지 않은 `SingleOrg` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-474">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="66cc7-475">기본값은 `user.read`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-475">The default is `user.read`.</span></span>

***

### `web`

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-476">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-476">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-477">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-477">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-478">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-478">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="66cc7-479">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-479">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-480">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-480">SDK version</span></span> | <span data-ttu-id="66cc7-481">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-481">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-482">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-482">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-483">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-483">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-484">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-484">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="66cc7-485">2.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-485">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="66cc7-486">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-486">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-487">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-487">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="66cc7-488">`mvc`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="66cc7-488">`mvc`, `webapp`</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="66cc7-489">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-489">The type of authentication to use.</span></span> <span data-ttu-id="66cc7-490">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-490">The possible values are:</span></span>

  - <span data-ttu-id="66cc7-491">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="66cc7-491">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="66cc7-492">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-492">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="66cc7-493">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-493">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="66cc7-494">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-494">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="66cc7-495">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-495">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="66cc7-496">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-496">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-497">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-497">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="66cc7-498">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-498">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-499">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-499">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="66cc7-500">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-500">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="66cc7-501">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-501">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="66cc7-502">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-502">The reset password policy ID for this project.</span></span> <span data-ttu-id="66cc7-503">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-503">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="66cc7-504">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-504">The edit profile policy ID for this project.</span></span> <span data-ttu-id="66cc7-505">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-505">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-506">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-506">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="66cc7-507">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-507">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="66cc7-508">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-508">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="66cc7-509">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-509">The Client ID for this project.</span></span> <span data-ttu-id="66cc7-510">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-510">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="66cc7-511">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-511">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="66cc7-512">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-512">The domain for the directory tenant.</span></span> <span data-ttu-id="66cc7-513">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-513">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-514">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-514">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="66cc7-515">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-515">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="66cc7-516">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-516">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-517">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-517">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="66cc7-518">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-518">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="66cc7-519">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-520">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-520">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="66cc7-521">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-521">Allows this application read-access to the directory.</span></span> <span data-ttu-id="66cc7-522">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-522">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-523">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-523">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-524">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-524">Turns off HTTPS.</span></span> <span data-ttu-id="66cc7-525">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-525">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="66cc7-526">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-526">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="66cc7-527">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-527">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-528">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-529">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-529">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="66cc7-530">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-531">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-531">SDK version</span></span> | <span data-ttu-id="66cc7-532">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-533">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-533">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-534">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-535">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-535">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="66cc7-536">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="66cc7-537">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-537">Includes BrowserLink in the project.</span></span> <span data-ttu-id="66cc7-538">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-538">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="66cc7-539">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-539">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="66cc7-540">.NET Core 3.1.201 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-540">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="66cc7-541">`angular`, `react`</span><span class="sxs-lookup"><span data-stu-id="66cc7-541">`angular`, `react`</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="66cc7-542">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-542">The type of authentication to use.</span></span> <span data-ttu-id="66cc7-543">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-543">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="66cc7-544">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-544">The possible values are:</span></span>

  - <span data-ttu-id="66cc7-545">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="66cc7-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="66cc7-546">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-546">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-547">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-547">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="66cc7-548">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-548">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-549">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-549">Turns off HTTPS.</span></span> <span data-ttu-id="66cc7-550">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-550">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="66cc7-551">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-551">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="66cc7-552">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-552">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-553">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-553">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-554">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-554">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-555">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-555">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="66cc7-556">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-556">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-557">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-557">SDK version</span></span> | <span data-ttu-id="66cc7-558">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-558">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-559">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-559">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-560">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-560">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-561">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-561">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="66cc7-562">2.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-562">2.1</span></span>         | `netcoreapp2.0` |

***

### `reactredux`

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-563">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-563">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-564">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-564">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-565">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-565">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="66cc7-566">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-566">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-567">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-567">SDK version</span></span> | <span data-ttu-id="66cc7-568">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-568">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-569">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-569">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-570">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-570">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-571">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-571">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="66cc7-572">2.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-572">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="66cc7-573">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-573">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-574">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-574">Turns off HTTPS.</span></span>

***

### `razorclasslib`

- **`--no-restore`**

  <span data-ttu-id="66cc7-575">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-575">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="66cc7-576">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-576">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="66cc7-577">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-577">Available since .NET Core 3.0 SDK.</span></span>

***
  
### `webapi`

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="66cc7-578">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-578">The type of authentication to use.</span></span> <span data-ttu-id="66cc7-579">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-579">The possible values are:</span></span>

  - <span data-ttu-id="66cc7-580">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="66cc7-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="66cc7-581">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="66cc7-582">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="66cc7-583">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-584">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="66cc7-585">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="66cc7-586">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="66cc7-587">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="66cc7-588">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="66cc7-589">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="66cc7-590">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-591">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="66cc7-592">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-592">The Client ID for this project.</span></span> <span data-ttu-id="66cc7-593">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-594">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="66cc7-595">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-595">The domain for the directory tenant.</span></span> <span data-ttu-id="66cc7-596">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-597">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="66cc7-598">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="66cc7-599">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="66cc7-600">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="66cc7-601">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="66cc7-602">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="66cc7-603">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="66cc7-604">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-604">Turns off HTTPS.</span></span> <span data-ttu-id="66cc7-605">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="66cc7-606">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="66cc7-607">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="66cc7-608">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="66cc7-609">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="66cc7-610">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="66cc7-611">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="66cc7-612">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="66cc7-612">SDK version</span></span> | <span data-ttu-id="66cc7-613">기본값</span><span class="sxs-lookup"><span data-stu-id="66cc7-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="66cc7-614">5.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-614">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="66cc7-615">3.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="66cc7-616">3.0</span><span class="sxs-lookup"><span data-stu-id="66cc7-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="66cc7-617">2.1</span><span class="sxs-lookup"><span data-stu-id="66cc7-617">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="66cc7-618">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-618">Doesn't execute an implicit restore during project creation.</span></span>

***

### `globaljson`

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="66cc7-619">*global.json* 파일에서 사용할 .NET SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-619">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="66cc7-620">예</span><span class="sxs-lookup"><span data-stu-id="66cc7-620">Examples</span></span>

- <span data-ttu-id="66cc7-621">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-621">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="66cc7-622">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-622">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="66cc7-623">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-623">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="66cc7-624">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-624">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="66cc7-625">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-625">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="66cc7-626">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-626">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="66cc7-627">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-627">List all templates matching the *we* substring.</span></span> <span data-ttu-id="66cc7-628">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-628">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="66cc7-629">*ng* 와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="66cc7-629">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="66cc7-630">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-630">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="66cc7-631">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-631">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="66cc7-632">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-632">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="66cc7-633">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json* 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66cc7-633">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="66cc7-634">참조</span><span class="sxs-lookup"><span data-stu-id="66cc7-634">See also</span></span>

- [<span data-ttu-id="66cc7-635">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="66cc7-635">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="66cc7-636">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="66cc7-636">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="66cc7-637">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="66cc7-637">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="66cc7-638">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="66cc7-638">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
