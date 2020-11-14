---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/04/2020
ms.openlocfilehash: 2ee06c37cd950f3b9771db2f30fe353435641d67
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400593"
---
# <a name="dotnet-new"></a><span data-ttu-id="c39a3-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c39a3-103">dotnet new</span></span>

<span data-ttu-id="c39a3-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c39a3-105">이름</span><span class="sxs-lookup"><span data-stu-id="c39a3-105">Name</span></span>

<span data-ttu-id="c39a3-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c39a3-107">개요</span><span class="sxs-lookup"><span data-stu-id="c39a3-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="c39a3-108">설명</span><span class="sxs-lookup"><span data-stu-id="c39a3-108">Description</span></span>

<span data-ttu-id="c39a3-109">`dotnet new` 명령은 템플릿을 기반으로 .NET Core 프로젝트 또는 다른 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="c39a3-110">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="c39a3-111">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="c39a3-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="c39a3-112">인수</span><span class="sxs-lookup"><span data-stu-id="c39a3-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="c39a3-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c39a3-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c39a3-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="c39a3-116">`dotnet new --list` 또는 `dotnet new -l`을 실행하여 설치된 모든 템플릿의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="c39a3-117">`TEMPLATE` 값이 반환된 테이블의 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="c39a3-118">.NET Core 3.0 SDK부터 CLI는 다음 조건에서 `dotnet new` 명령을 호출할 때 NuGet.org에서 템플릿을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="c39a3-119">`dotnet new`를 호출할 때 CLI가 템플릿 일치 또는 부분 일치조차 찾을 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="c39a3-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="c39a3-120">최신 버전의 템플릿을 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="c39a3-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="c39a3-121">이 경우 프로젝트 또는 아티팩트가 만들어지지만 CLI는 업데이트된 템플릿 버전에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="c39a3-122">다음 표에는 .NET Core SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="c39a3-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="c39a3-124">특정 템플릿 옵션을 보려면 약식 이름 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="c39a3-125">템플릿</span><span class="sxs-lookup"><span data-stu-id="c39a3-125">Templates</span></span>                                    | <span data-ttu-id="c39a3-126">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="c39a3-126">Short name</span></span>                      | <span data-ttu-id="c39a3-127">언어</span><span class="sxs-lookup"><span data-stu-id="c39a3-127">Language</span></span>     | <span data-ttu-id="c39a3-128">Tags</span><span class="sxs-lookup"><span data-stu-id="c39a3-128">Tags</span></span>                                  | <span data-ttu-id="c39a3-129">도입</span><span class="sxs-lookup"><span data-stu-id="c39a3-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="c39a3-130">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="c39a3-130">Console Application</span></span>                          | [<span data-ttu-id="c39a3-131">콘솔</span><span class="sxs-lookup"><span data-stu-id="c39a3-131">console</span></span>](#console)             | <span data-ttu-id="c39a3-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-132">[C#], F#, VB</span></span> | <span data-ttu-id="c39a3-133">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="c39a3-133">Common/Console</span></span>                        | <span data-ttu-id="c39a3-134">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-134">1.0</span></span>        |
| <span data-ttu-id="c39a3-135">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-135">Class library</span></span>                                | [<span data-ttu-id="c39a3-136">classlib</span><span class="sxs-lookup"><span data-stu-id="c39a3-136">classlib</span></span>](#classlib)           | <span data-ttu-id="c39a3-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-137">[C#], F#, VB</span></span> | <span data-ttu-id="c39a3-138">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-138">Common/Library</span></span>                        | <span data-ttu-id="c39a3-139">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-139">1.0</span></span>        |
| <span data-ttu-id="c39a3-140">WPF 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="c39a3-140">WPF Application</span></span>                              | [<span data-ttu-id="c39a3-141">wpf</span><span class="sxs-lookup"><span data-stu-id="c39a3-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="c39a3-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-142">[C#], VB</span></span>     | <span data-ttu-id="c39a3-143">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="c39a3-143">Common/WPF</span></span>                            | <span data-ttu-id="c39a3-144">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="c39a3-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c39a3-145">WPF 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-145">WPF Class library</span></span>                            | [<span data-ttu-id="c39a3-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="c39a3-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="c39a3-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-147">[C#], VB</span></span>     | <span data-ttu-id="c39a3-148">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="c39a3-148">Common/WPF</span></span>                            | <span data-ttu-id="c39a3-149">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="c39a3-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c39a3-150">WPF 사용자 지정 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="c39a3-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="c39a3-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="c39a3-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-152">[C#], VB</span></span>     | <span data-ttu-id="c39a3-153">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="c39a3-153">Common/WPF</span></span>                            | <span data-ttu-id="c39a3-154">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="c39a3-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c39a3-155">WPF 사용자 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="c39a3-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="c39a3-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="c39a3-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-157">[C#], VB</span></span>     | <span data-ttu-id="c39a3-158">일반/WPF</span><span class="sxs-lookup"><span data-stu-id="c39a3-158">Common/WPF</span></span>                            | <span data-ttu-id="c39a3-159">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="c39a3-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c39a3-160">Windows Forms(WinForms) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="c39a3-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="c39a3-161">winforms</span><span class="sxs-lookup"><span data-stu-id="c39a3-161">winforms</span></span>](#winforms)           | <span data-ttu-id="c39a3-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-162">[C#], VB</span></span>     | <span data-ttu-id="c39a3-163">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="c39a3-163">Common/WinForms</span></span>                       | <span data-ttu-id="c39a3-164">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="c39a3-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c39a3-165">Windows Forms(WinForms) 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="c39a3-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="c39a3-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="c39a3-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-167">[C#], VB</span></span>     | <span data-ttu-id="c39a3-168">일반/WinForms</span><span class="sxs-lookup"><span data-stu-id="c39a3-168">Common/WinForms</span></span>                       | <span data-ttu-id="c39a3-169">3.0(VB의 경우 5.0)</span><span class="sxs-lookup"><span data-stu-id="c39a3-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c39a3-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="c39a3-170">Worker Service</span></span>                               | [<span data-ttu-id="c39a3-171">worker</span><span class="sxs-lookup"><span data-stu-id="c39a3-171">worker</span></span>](#web-others)           | <span data-ttu-id="c39a3-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-172">[C#]</span></span>         | <span data-ttu-id="c39a3-173">일반/Worker/웹</span><span class="sxs-lookup"><span data-stu-id="c39a3-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="c39a3-174">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-174">3.0</span></span>        |
| <span data-ttu-id="c39a3-175">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="c39a3-175">Unit Test Project</span></span>                            | [<span data-ttu-id="c39a3-176">mstest</span><span class="sxs-lookup"><span data-stu-id="c39a3-176">mstest</span></span>](#test)                 | <span data-ttu-id="c39a3-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-177">[C#], F#, VB</span></span> | <span data-ttu-id="c39a3-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="c39a3-178">Test/MSTest</span></span>                           | <span data-ttu-id="c39a3-179">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-179">1.0</span></span>        |
| <span data-ttu-id="c39a3-180">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="c39a3-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="c39a3-181">nunit</span><span class="sxs-lookup"><span data-stu-id="c39a3-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="c39a3-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-182">[C#], F#, VB</span></span> | <span data-ttu-id="c39a3-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c39a3-183">Test/NUnit</span></span>                            | <span data-ttu-id="c39a3-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="c39a3-184">2.1.400</span></span>    |
| <span data-ttu-id="c39a3-185">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="c39a3-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="c39a3-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-186">[C#], F#, VB</span></span> | <span data-ttu-id="c39a3-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c39a3-187">Test/NUnit</span></span>                            | <span data-ttu-id="c39a3-188">2.2</span><span class="sxs-lookup"><span data-stu-id="c39a3-188">2.2</span></span>        |
| <span data-ttu-id="c39a3-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="c39a3-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="c39a3-190">xunit</span><span class="sxs-lookup"><span data-stu-id="c39a3-190">xunit</span></span>](#test)                  | <span data-ttu-id="c39a3-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c39a3-191">[C#], F#, VB</span></span> | <span data-ttu-id="c39a3-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="c39a3-192">Test/xUnit</span></span>                            | <span data-ttu-id="c39a3-193">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-193">1.0</span></span>        |
| <span data-ttu-id="c39a3-194">Razor 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c39a3-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="c39a3-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-195">[C#]</span></span>         | <span data-ttu-id="c39a3-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c39a3-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="c39a3-197">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-197">3.0</span></span>        |
| <span data-ttu-id="c39a3-198">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="c39a3-198">Razor Page</span></span>                                   | [<span data-ttu-id="c39a3-199">page</span><span class="sxs-lookup"><span data-stu-id="c39a3-199">page</span></span>](#page)                   | <span data-ttu-id="c39a3-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-200">[C#]</span></span>         | <span data-ttu-id="c39a3-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c39a3-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="c39a3-202">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-202">2.0</span></span>        |
| <span data-ttu-id="c39a3-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c39a3-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="c39a3-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="c39a3-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="c39a3-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-205">[C#]</span></span>         | <span data-ttu-id="c39a3-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c39a3-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="c39a3-207">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-207">2.0</span></span>        |
| <span data-ttu-id="c39a3-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c39a3-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="c39a3-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-209">[C#]</span></span>         | <span data-ttu-id="c39a3-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c39a3-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="c39a3-211">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-211">2.0</span></span>        |
| <span data-ttu-id="c39a3-212">:::no-loc(Blazor)::: 서버 앱</span><span class="sxs-lookup"><span data-stu-id="c39a3-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="c39a3-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="c39a3-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="c39a3-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-214">[C#]</span></span>         | <span data-ttu-id="c39a3-215">Web/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="c39a3-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="c39a3-216">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-216">3.0</span></span>        |
| <span data-ttu-id="c39a3-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: 앱</span><span class="sxs-lookup"><span data-stu-id="c39a3-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | [<span data-ttu-id="c39a3-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="c39a3-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="c39a3-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-219">[C#]</span></span>         | <span data-ttu-id="c39a3-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="c39a3-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="c39a3-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="c39a3-221">3.1.300</span></span>    |
| <span data-ttu-id="c39a3-222">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="c39a3-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="c39a3-223">web</span><span class="sxs-lookup"><span data-stu-id="c39a3-223">web</span></span>](#web)                     | <span data-ttu-id="c39a3-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c39a3-224">[C#], F#</span></span>     | <span data-ttu-id="c39a3-225">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="c39a3-225">Web/Empty</span></span>                             | <span data-ttu-id="c39a3-226">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-226">1.0</span></span>        |
| <span data-ttu-id="c39a3-227">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="c39a3-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="c39a3-228">mvc</span><span class="sxs-lookup"><span data-stu-id="c39a3-228">mvc</span></span>](#web-options)             | <span data-ttu-id="c39a3-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c39a3-229">[C#], F#</span></span>     | <span data-ttu-id="c39a3-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="c39a3-230">Web/MVC</span></span>                               | <span data-ttu-id="c39a3-231">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-231">1.0</span></span>        |
| <span data-ttu-id="c39a3-232">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="c39a3-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="c39a3-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="c39a3-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="c39a3-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-234">[C#]</span></span>         | <span data-ttu-id="c39a3-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="c39a3-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="c39a3-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="c39a3-237">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="c39a3-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="c39a3-238">angular</span><span class="sxs-lookup"><span data-stu-id="c39a3-238">angular</span></span>](#spa)                 | <span data-ttu-id="c39a3-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-239">[C#]</span></span>         | <span data-ttu-id="c39a3-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c39a3-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c39a3-241">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-241">2.0</span></span>        |
| <span data-ttu-id="c39a3-242">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="c39a3-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="c39a3-243">react</span><span class="sxs-lookup"><span data-stu-id="c39a3-243">react</span></span>](#spa)                   | <span data-ttu-id="c39a3-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-244">[C#]</span></span>         | <span data-ttu-id="c39a3-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c39a3-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c39a3-246">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-246">2.0</span></span>        |
| <span data-ttu-id="c39a3-247">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="c39a3-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="c39a3-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="c39a3-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="c39a3-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-249">[C#]</span></span>         | <span data-ttu-id="c39a3-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c39a3-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c39a3-251">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-251">2.0</span></span>        |
| <span data-ttu-id="c39a3-252">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-252">Razor Class Library</span></span>                          | [<span data-ttu-id="c39a3-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c39a3-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="c39a3-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-254">[C#]</span></span>         | <span data-ttu-id="c39a3-255">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c39a3-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="c39a3-256">2.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-256">2.1</span></span>        |
| <span data-ttu-id="c39a3-257">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="c39a3-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="c39a3-258">webapi</span><span class="sxs-lookup"><span data-stu-id="c39a3-258">webapi</span></span>](#webapi)               | <span data-ttu-id="c39a3-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c39a3-259">[C#], F#</span></span>     | <span data-ttu-id="c39a3-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="c39a3-260">Web/WebAPI</span></span>                            | <span data-ttu-id="c39a3-261">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-261">1.0</span></span>        |
| <span data-ttu-id="c39a3-262">ASP.NET Core gRPC 서비스</span><span class="sxs-lookup"><span data-stu-id="c39a3-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="c39a3-263">grpc</span><span class="sxs-lookup"><span data-stu-id="c39a3-263">grpc</span></span>](#web-others)             | <span data-ttu-id="c39a3-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="c39a3-264">[C#]</span></span>         | <span data-ttu-id="c39a3-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c39a3-265">Web/gRPC</span></span>                              | <span data-ttu-id="c39a3-266">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-266">3.0</span></span>        |
| <span data-ttu-id="c39a3-267">dotnet gitignore 파일</span><span class="sxs-lookup"><span data-stu-id="c39a3-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="c39a3-268">Config</span><span class="sxs-lookup"><span data-stu-id="c39a3-268">Config</span></span>                                | <span data-ttu-id="c39a3-269">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-269">3.0</span></span>        |
| <span data-ttu-id="c39a3-270">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="c39a3-270">global.json file</span></span>                             | [<span data-ttu-id="c39a3-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="c39a3-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="c39a3-272">Config</span><span class="sxs-lookup"><span data-stu-id="c39a3-272">Config</span></span>                                | <span data-ttu-id="c39a3-273">2.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-273">2.0</span></span>        |
| <span data-ttu-id="c39a3-274">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="c39a3-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="c39a3-275">Config</span><span class="sxs-lookup"><span data-stu-id="c39a3-275">Config</span></span>                                | <span data-ttu-id="c39a3-276">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-276">1.0</span></span>        |
| <span data-ttu-id="c39a3-277">Dotnet 로컬 도구 매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="c39a3-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="c39a3-278">Config</span><span class="sxs-lookup"><span data-stu-id="c39a3-278">Config</span></span>                                | <span data-ttu-id="c39a3-279">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-279">3.0</span></span>        |
| <span data-ttu-id="c39a3-280">웹 구성</span><span class="sxs-lookup"><span data-stu-id="c39a3-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="c39a3-281">Config</span><span class="sxs-lookup"><span data-stu-id="c39a3-281">Config</span></span>                                | <span data-ttu-id="c39a3-282">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-282">1.0</span></span>        |
| <span data-ttu-id="c39a3-283">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="c39a3-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="c39a3-284">솔루션</span><span class="sxs-lookup"><span data-stu-id="c39a3-284">Solution</span></span>                              | <span data-ttu-id="c39a3-285">1.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-285">1.0</span></span>        |
| <span data-ttu-id="c39a3-286">프로토콜 버퍼 파일</span><span class="sxs-lookup"><span data-stu-id="c39a3-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="c39a3-287">proto</span><span class="sxs-lookup"><span data-stu-id="c39a3-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="c39a3-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c39a3-288">Web/gRPC</span></span>                              | <span data-ttu-id="c39a3-289">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="c39a3-290">옵션</span><span class="sxs-lookup"><span data-stu-id="c39a3-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="c39a3-291">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="c39a3-292">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="c39a3-293">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c39a3-294">선택한 템플릿이 출력 디렉터리의 기존 파일을 재정의하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c39a3-295">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-295">Prints out help for the command.</span></span> <span data-ttu-id="c39a3-296">`dotnet new` 명령 자체 또는 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="c39a3-297">예: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c39a3-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="c39a3-298">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c39a3-299">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c39a3-300">기본적으로 `dotnet new`는 안정적인 최신 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="c39a3-301">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="c39a3-302">이 명령을 실행할 때 템플릿의 버전이 이미 설치되어 있는 경우 템플릿이 지정된 버전으로 업데이트되거나 버전이 지정되지 않은 경우 안정적인 최신 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="c39a3-303">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="c39a3-304">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="c39a3-305">이름을 지정하지 않으면 모든 템플릿이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="c39a3-306">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-306">The language of the template to create.</span></span> <span data-ttu-id="c39a3-307">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="c39a3-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c39a3-308">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c39a3-309">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c39a3-310">이러한 경우 언어 매개 변수 값을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="c39a3-311">예: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c39a3-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="c39a3-312">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-312">The name for the created output.</span></span> <span data-ttu-id="c39a3-313">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="c39a3-314">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-314">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="c39a3-315">.NET Core 2.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-315">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c39a3-316">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-316">Location to place the generated output.</span></span> <span data-ttu-id="c39a3-317">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-317">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="c39a3-318">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-318">Filters templates based on available types.</span></span> <span data-ttu-id="c39a3-319">미리 정의된 값은 `project` 및 `item`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-319">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="c39a3-320">제공된 `PATH` 또는 `NUGET_ID`에서 템플릿 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-320">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c39a3-321">`<PATH|NUGET_ID>` 값을 지정하지 않으면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-321">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="c39a3-322">`NUGET_ID`를 지정하는 경우 버전 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-322">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="c39a3-323">이 옵션에 대한 매개 변수를 지정하지 않으면 명령은 설치된 템플릿 및 해당 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-323">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c39a3-324">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-324">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c39a3-325">예를 들어 *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp* 는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-325">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="c39a3-326">템플릿 경로에 마지막 디렉터리 슬래시를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-326">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="c39a3-327">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-327">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="c39a3-328">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-328">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="c39a3-329">현재 설치된 템플릿 패키지에 사용할 수 있는 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-329">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="c39a3-330">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-330">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="c39a3-331">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="c39a3-331">Template options</span></span>

<span data-ttu-id="c39a3-332">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-332">Each project template may have additional options available.</span></span> <span data-ttu-id="c39a3-333">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-333">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="c39a3-334">콘솔</span><span class="sxs-lookup"><span data-stu-id="c39a3-334">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c39a3-335">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-335">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-336">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-336">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c39a3-337">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-337">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-338">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-338">SDK version</span></span> | <span data-ttu-id="c39a3-339">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-339">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-340">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-341">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c39a3-342">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c39a3-343">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c39a3-344">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-344">Not supported for F#.</span></span> <span data-ttu-id="c39a3-345">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c39a3-346">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-347">지정할 경우 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="c39a3-348">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="c39a3-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="c39a3-350">classlib</span><span class="sxs-lookup"><span data-stu-id="c39a3-350">classlib</span></span>

- <span data-ttu-id="c39a3-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c39a3-352">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-353">값: `netcoreapp<version>`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard<version>`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="c39a3-353">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c39a3-354">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-354">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c39a3-355">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c39a3-356">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c39a3-357">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-357">Not supported for F#.</span></span> <span data-ttu-id="c39a3-358">.NET Core 2.2 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c39a3-359">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-360">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="c39a3-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="c39a3-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="c39a3-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c39a3-364">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-365">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-365">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c39a3-366">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c39a3-367">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c39a3-368">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c39a3-369">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-370">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="c39a3-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="c39a3-372">winforms, winformslib</span></span>

- <span data-ttu-id="c39a3-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="c39a3-374">생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c39a3-375">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c39a3-376">기본 C# 버전 목록은 [기본값](../../csharp/language-reference/configure-language-version.md#defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-377">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="c39a3-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="c39a3-379">worker, grpc</span></span>

- <span data-ttu-id="c39a3-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c39a3-381">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-382">기본값은 `netcoreapp3.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c39a3-383">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c39a3-384">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-385">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="c39a3-387">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="c39a3-387">mstest, xunit</span></span>

- <span data-ttu-id="c39a3-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c39a3-389">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-390">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c39a3-391">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-392">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-392">SDK version</span></span> | <span data-ttu-id="c39a3-393">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-394">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-394">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-395">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-395">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c39a3-396">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-397">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-397">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-398">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-398">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="c39a3-399">nunit</span><span class="sxs-lookup"><span data-stu-id="c39a3-399">nunit</span></span>

- <span data-ttu-id="c39a3-400">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-400">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c39a3-401">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-401">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="c39a3-402">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-402">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-403">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-403">SDK version</span></span> | <span data-ttu-id="c39a3-404">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-404">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-405">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-405">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-406">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-406">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c39a3-407">2.2</span><span class="sxs-lookup"><span data-stu-id="c39a3-407">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="c39a3-408">2.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-408">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c39a3-409">[dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-409">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-410">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-410">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-411">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-411">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="c39a3-412">페이지</span><span class="sxs-lookup"><span data-stu-id="c39a3-412">page</span></span>

- <span data-ttu-id="c39a3-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="c39a3-414">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-414">Namespace for the generated code.</span></span> <span data-ttu-id="c39a3-415">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-415">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="c39a3-416">PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-416">Creates the page without a PageModel.</span></span>

<span data-ttu-id="c39a3-417">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-417">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="c39a3-418">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="c39a3-418">viewimports, proto</span></span>

- <span data-ttu-id="c39a3-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="c39a3-420">생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-420">Namespace for the generated code.</span></span> <span data-ttu-id="c39a3-421">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-421">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c39a3-422">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-422">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="c39a3-423">blazorserver</span><span class="sxs-lookup"><span data-stu-id="c39a3-423">blazorserver</span></span>

- <span data-ttu-id="c39a3-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c39a3-425">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-425">The type of authentication to use.</span></span> <span data-ttu-id="c39a3-426">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-426">The possible values are:</span></span>

  - <span data-ttu-id="c39a3-427">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="c39a3-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c39a3-428">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c39a3-429">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c39a3-430">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c39a3-431">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-431">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c39a3-432">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-432">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-433">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-433">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c39a3-434">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-434">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-435">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-435">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c39a3-436">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-436">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c39a3-437">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-437">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c39a3-438">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-438">The reset password policy ID for this project.</span></span> <span data-ttu-id="c39a3-439">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-439">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c39a3-440">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-440">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c39a3-441">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-441">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-442">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-442">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c39a3-443">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-443">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c39a3-444">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-444">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c39a3-445">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-445">The Client ID for this project.</span></span> <span data-ttu-id="c39a3-446">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-446">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c39a3-447">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-447">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c39a3-448">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-448">The domain for the directory tenant.</span></span> <span data-ttu-id="c39a3-449">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-450">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-450">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c39a3-451">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-451">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c39a3-452">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-452">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-453">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-453">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c39a3-454">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-454">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c39a3-455">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-456">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-456">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c39a3-457">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-457">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c39a3-458">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-458">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c39a3-459">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-459">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-460">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-460">Turns off HTTPS.</span></span> <span data-ttu-id="c39a3-461">이 옵션은 `--auth`에 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-461">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c39a3-462">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-462">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c39a3-463">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-463">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-464">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-464">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-465">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-465">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="c39a3-466">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="c39a3-466">blazorwasm</span></span>

- <span data-ttu-id="c39a3-467">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-467">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c39a3-468">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="c39a3-469">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-469">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-470">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-470">SDK version</span></span> | <span data-ttu-id="c39a3-471">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-471">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-472">5.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-472">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="c39a3-473">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-473">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="c39a3-474">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-474">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="c39a3-475">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: 앱의 ASP.NET Core 호스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-475">Includes an ASP.NET Core host for the :::no-loc(Blazor)::: :::no-loc(WebAssembly)::: app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c39a3-476">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-476">The type of authentication to use.</span></span> <span data-ttu-id="c39a3-477">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-477">The possible values are:</span></span>

  - <span data-ttu-id="c39a3-478">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="c39a3-478">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c39a3-479">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-479">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c39a3-480">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-480">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c39a3-481">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-481">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="c39a3-482">OIDC 공급자의 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-482">The authority of the OIDC provider.</span></span> <span data-ttu-id="c39a3-483">`Individual` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-483">Use with `Individual` authentication.</span></span> <span data-ttu-id="c39a3-484">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-484">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-485">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-485">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c39a3-486">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-486">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-487">기본값은 `https://aadB2CInstance.b2clogin.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-487">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c39a3-488">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-488">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c39a3-489">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-489">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-490">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-490">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c39a3-491">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-491">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-492">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-492">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c39a3-493">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-493">The Client ID for this project.</span></span> <span data-ttu-id="c39a3-494">`IndividualB2C`, `SingleOrg` 또는 독립 실행형 시나리오의 경우 `Individual` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-494">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="c39a3-495">기본값은 `33333333-3333-3333-33333333333333333`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-495">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c39a3-496">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-496">The domain for the directory tenant.</span></span> <span data-ttu-id="c39a3-497">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-497">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-498">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-498">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="c39a3-499">호출하려는 서버 API의 앱 ID URI입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-499">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="c39a3-500">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-500">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-501">기본값은 `api.id.uri`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-501">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="c39a3-502">서버가 호스트하는 API의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-502">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="c39a3-503">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-503">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-504">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-504">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="c39a3-505">클라이언트가 액세스 토큰 프로비전을 요청하는 데 필요한 API 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-505">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="c39a3-506">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-506">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-507">기본값은 `user_impersonation`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-507">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c39a3-508">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-508">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c39a3-509">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-509">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-510">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-510">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c39a3-511">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-511">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c39a3-512">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-512">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c39a3-513">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="c39a3-514">프로그레시브 웹 애플리케이션(PWA)을 생성하여 설치 및 오프라인 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-514">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-515">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-515">Turns off HTTPS.</span></span> <span data-ttu-id="c39a3-516">이 옵션은 `--auth`에 `Individual`, `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-516">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c39a3-517">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c39a3-518">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="c39a3-519">웹앱에서 호출할 API의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-519">URL of the API to call from the web app.</span></span> <span data-ttu-id="c39a3-520">ASP.NET Core 호스트가 지정되지 않은 `SingleOrg` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-520">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="c39a3-521">기본값은 `https://graph.microsoft.com/v1.0/me`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-521">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="c39a3-522">웹앱이 Microsoft Graph를 호출하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-522">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="c39a3-523">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-523">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="c39a3-524">웹앱에서 API를 호출하기 위해 요청할 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-524">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="c39a3-525">ASP.NET Core 호스트가 지정되지 않은 `SingleOrg` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-525">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="c39a3-526">기본값은 `user.read`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-526">The default is `user.read`.</span></span>

<span data-ttu-id="c39a3-527">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-527">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="c39a3-528">web</span><span class="sxs-lookup"><span data-stu-id="c39a3-528">web</span></span>

- <span data-ttu-id="c39a3-529">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-529">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="c39a3-530">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c39a3-531">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-532">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c39a3-533">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-534">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-534">SDK version</span></span> | <span data-ttu-id="c39a3-535">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-536">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-537">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c39a3-538">2.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-538">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c39a3-539">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-540">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-540">Turns off HTTPS.</span></span>

<span data-ttu-id="c39a3-541">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-541">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="c39a3-542">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="c39a3-542">mvc, webapp</span></span>

- <span data-ttu-id="c39a3-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c39a3-544">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-544">The type of authentication to use.</span></span> <span data-ttu-id="c39a3-545">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-545">The possible values are:</span></span>

  - <span data-ttu-id="c39a3-546">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="c39a3-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c39a3-547">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-547">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c39a3-548">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c39a3-549">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c39a3-550">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-550">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c39a3-551">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-552">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c39a3-553">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-554">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c39a3-555">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c39a3-556">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-556">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c39a3-557">이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-557">The reset password policy ID for this project.</span></span> <span data-ttu-id="c39a3-558">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-558">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c39a3-559">이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-559">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c39a3-560">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-560">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-561">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-561">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c39a3-562">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-562">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c39a3-563">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-563">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c39a3-564">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-564">The Client ID for this project.</span></span> <span data-ttu-id="c39a3-565">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-565">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c39a3-566">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-566">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c39a3-567">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-567">The domain for the directory tenant.</span></span> <span data-ttu-id="c39a3-568">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-568">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-569">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-569">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c39a3-570">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-570">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c39a3-571">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-571">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-572">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-572">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c39a3-573">리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-573">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c39a3-574">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-574">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-575">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-575">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c39a3-576">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-576">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c39a3-577">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-577">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c39a3-578">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-578">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-579">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-579">Turns off HTTPS.</span></span> <span data-ttu-id="c39a3-580">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-580">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c39a3-581">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-581">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c39a3-582">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-582">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c39a3-583">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-583">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-584">.NET Core 3.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-584">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c39a3-585">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-585">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-586">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-586">SDK version</span></span> | <span data-ttu-id="c39a3-587">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-587">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-588">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-588">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-589">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-589">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="c39a3-590">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-590">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="c39a3-591">프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-591">Includes BrowserLink in the project.</span></span> <span data-ttu-id="c39a3-592">.NET Core 2.2 및 3.1 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-592">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="c39a3-593">프로젝트가 디버그 빌드에서 [Razor 런타임 컴파일](/aspnet/core/mvc/views/view-compilation#runtime-compilation)을 사용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-593">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="c39a3-594">.NET Core 3.1.201 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-594">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="c39a3-595">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-595">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="c39a3-596">angular, react</span><span class="sxs-lookup"><span data-stu-id="c39a3-596">angular, react</span></span>

- <span data-ttu-id="c39a3-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c39a3-598">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-598">The type of authentication to use.</span></span> <span data-ttu-id="c39a3-599">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-599">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="c39a3-600">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-600">The possible values are:</span></span>

  - <span data-ttu-id="c39a3-601">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="c39a3-601">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c39a3-602">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-602">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c39a3-603">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c39a3-604">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-604">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-605">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-605">Turns off HTTPS.</span></span> <span data-ttu-id="c39a3-606">이 옵션은 인증이 `None`인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-606">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c39a3-607">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c39a3-608">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-608">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-609">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-609">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c39a3-610">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-610">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-611">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-611">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c39a3-612">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-612">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-613">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-613">SDK version</span></span> | <span data-ttu-id="c39a3-614">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-614">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-615">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-616">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c39a3-617">2.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-617">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="c39a3-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-618">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="c39a3-619">reactredux</span><span class="sxs-lookup"><span data-stu-id="c39a3-619">reactredux</span></span>

- <span data-ttu-id="c39a3-620">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-620">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="c39a3-621">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-621">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c39a3-622">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-622">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-623">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-623">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c39a3-624">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-624">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-625">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-625">SDK version</span></span> | <span data-ttu-id="c39a3-626">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-626">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-627">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-627">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-628">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-628">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c39a3-629">2.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-629">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="c39a3-630">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-630">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-631">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-631">Turns off HTTPS.</span></span>

<span data-ttu-id="c39a3-632">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-632">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="c39a3-633">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c39a3-633">razorclasslib</span></span>

- <span data-ttu-id="c39a3-634">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-634">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="c39a3-635">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-635">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="c39a3-636">이 라이브러리에 구성 요소 외에 기존의 Razor 페이지와 뷰를 추가하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-636">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="c39a3-637">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-637">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="c39a3-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-638">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="c39a3-639">webapi</span><span class="sxs-lookup"><span data-stu-id="c39a3-639">webapi</span></span>

- <span data-ttu-id="c39a3-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c39a3-641">사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-641">The type of authentication to use.</span></span> <span data-ttu-id="c39a3-642">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-642">The possible values are:</span></span>

  - <span data-ttu-id="c39a3-643">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="c39a3-643">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c39a3-644">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-644">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c39a3-645">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-645">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c39a3-646">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-646">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-647">연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-647">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c39a3-648">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-648">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c39a3-649">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-649">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c39a3-650">이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-650">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c39a3-651">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-651">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c39a3-652">연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-652">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c39a3-653">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-653">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-654">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-654">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c39a3-655">이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-655">The Client ID for this project.</span></span> <span data-ttu-id="c39a3-656">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-656">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-657">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-657">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c39a3-658">디렉터리 테넌트의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-658">The domain for the directory tenant.</span></span> <span data-ttu-id="c39a3-659">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-659">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-660">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-660">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c39a3-661">연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-661">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c39a3-662">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-662">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c39a3-663">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-663">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c39a3-664">디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-664">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c39a3-665">`SingleOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-665">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c39a3-666">생성된 템플릿에서 *launchSettings.json* 을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-666">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c39a3-667">HTTPS를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-667">Turns off HTTPS.</span></span> <span data-ttu-id="c39a3-668">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-668">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c39a3-669">이 옵션은 인증에 `IndividualB2C` 또는 `SingleOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-669">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c39a3-670">SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-670">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c39a3-671">`IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-671">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c39a3-672">대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-672">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c39a3-673">.NET Core 2.2 SDK에서 사용할 수 없는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-673">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c39a3-674">다음 표에서는 사용하는 SDK 버전 번호에 따른 기본값을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-674">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c39a3-675">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c39a3-675">SDK version</span></span> | <span data-ttu-id="c39a3-676">기본값</span><span class="sxs-lookup"><span data-stu-id="c39a3-676">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c39a3-677">3.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-677">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c39a3-678">3.0</span><span class="sxs-lookup"><span data-stu-id="c39a3-678">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c39a3-679">2.1</span><span class="sxs-lookup"><span data-stu-id="c39a3-679">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c39a3-680">프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-680">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c39a3-681">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c39a3-681">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="c39a3-682">globaljson</span><span class="sxs-lookup"><span data-stu-id="c39a3-682">globaljson</span></span>

- <span data-ttu-id="c39a3-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="c39a3-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="c39a3-684">*global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-684">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="c39a3-685">예</span><span class="sxs-lookup"><span data-stu-id="c39a3-685">Examples</span></span>

- <span data-ttu-id="c39a3-686">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-686">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="c39a3-687">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-687">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="c39a3-688">지정된 디렉터리에 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-688">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="c39a3-689">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-689">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="c39a3-690">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-690">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="c39a3-691">SPA(단일 페이지 애플리케이션) 템플릿에 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-691">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="c39a3-692">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-692">List all templates matching the *we* substring.</span></span> <span data-ttu-id="c39a3-693">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-693">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="c39a3-694">*ng* 와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c39a3-694">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="c39a3-695">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-695">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="c39a3-696">ASP.NET Core용 SPA 템플릿의 버전 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-696">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="c39a3-697">설치된 템플릿 및 해당 세부 정보(제거 방법 포함)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-697">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="c39a3-698">SDK 버전을 3.1.101로 설정하여 현재 디렉터리에 *global.json* 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c39a3-698">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="c39a3-699">참조</span><span class="sxs-lookup"><span data-stu-id="c39a3-699">See also</span></span>

- [<span data-ttu-id="c39a3-700">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="c39a3-700">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="c39a3-701">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="c39a3-701">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="c39a3-702">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="c39a3-702">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="c39a3-703">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="c39a3-703">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
