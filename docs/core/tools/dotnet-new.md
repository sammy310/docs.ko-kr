---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
ms.date: 05/06/2019
ms.openlocfilehash: 57b198d13984fb4585e1df6303afe481e7e0552d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969745"
---
# <a name="dotnet-new"></a><span data-ttu-id="8e625-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8e625-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8e625-104">name</span><span class="sxs-lookup"><span data-stu-id="8e625-104">Name</span></span>

<span data-ttu-id="8e625-105">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8e625-106">개요</span><span class="sxs-lookup"><span data-stu-id="8e625-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="8e625-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="8e625-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8e625-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8e625-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8e625-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8e625-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8e625-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8e625-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="8e625-111">설명</span><span class="sxs-lookup"><span data-stu-id="8e625-111">Description</span></span>

<span data-ttu-id="8e625-112">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="8e625-113">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="8e625-114">인수</span><span class="sxs-lookup"><span data-stu-id="8e625-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="8e625-115">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="8e625-116">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="8e625-117">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="8e625-118">`TEMPLATE` 값이 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="8e625-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="8e625-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="8e625-120">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-120">The command contains a default list of templates.</span></span> <span data-ttu-id="8e625-121">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8e625-122">다음 표에서는 .NET Core SDK 2.2.100과 함께 사전 설치된 템플릿을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="8e625-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="8e625-124">템플릿</span><span class="sxs-lookup"><span data-stu-id="8e625-124">Templates</span></span>                                    | <span data-ttu-id="8e625-125">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="8e625-125">Short Name</span></span>        | <span data-ttu-id="8e625-126">언어</span><span class="sxs-lookup"><span data-stu-id="8e625-126">Language</span></span>     | <span data-ttu-id="8e625-127">Tags</span><span class="sxs-lookup"><span data-stu-id="8e625-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="8e625-128">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="8e625-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="8e625-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-129">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-130">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="8e625-130">Common/Console</span></span>                        |
| <span data-ttu-id="8e625-131">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="8e625-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-132">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-133">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-133">Common/Library</span></span>                        |
| <span data-ttu-id="8e625-134">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="8e625-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-135">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="8e625-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="8e625-137">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="8e625-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-138">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="8e625-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="8e625-140">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="8e625-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="8e625-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-141">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="8e625-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="8e625-143">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="8e625-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-144">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="8e625-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="8e625-146">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="8e625-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="8e625-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-147">[C#]</span></span>         | <span data-ttu-id="8e625-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="8e625-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8e625-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="8e625-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-150">[C#]</span></span>         | <span data-ttu-id="8e625-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="8e625-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8e625-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="8e625-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-153">[C#]</span></span>         | <span data-ttu-id="8e625-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="8e625-155">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="8e625-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="8e625-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-156">[C#], F#</span></span>     | <span data-ttu-id="8e625-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="8e625-157">Web/Empty</span></span>                             |
| <span data-ttu-id="8e625-158">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="8e625-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="8e625-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-159">[C#], F#</span></span>     | <span data-ttu-id="8e625-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="8e625-160">Web/MVC</span></span>                               |
| <span data-ttu-id="8e625-161">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="8e625-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="8e625-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="8e625-162">`webapp`, `razor`</span></span> | <span data-ttu-id="8e625-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-163">[C#]</span></span>         | <span data-ttu-id="8e625-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="8e625-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="8e625-165">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="8e625-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-166">[C#]</span></span>         | <span data-ttu-id="8e625-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="8e625-168">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="8e625-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-169">[C#]</span></span>         | <span data-ttu-id="8e625-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="8e625-171">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="8e625-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-172">[C#]</span></span>         | <span data-ttu-id="8e625-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="8e625-174">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="8e625-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-175">[C#]</span></span>         | <span data-ttu-id="8e625-176">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="8e625-177">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="8e625-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="8e625-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-178">[C#], F#</span></span>     | <span data-ttu-id="8e625-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="8e625-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="8e625-180">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="8e625-181">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-181">Config</span></span>                                |
| <span data-ttu-id="8e625-182">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="8e625-183">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-183">Config</span></span>                                |
| <span data-ttu-id="8e625-184">웹 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="8e625-185">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-185">Config</span></span>                                |
| <span data-ttu-id="8e625-186">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="8e625-187">솔루션</span><span class="sxs-lookup"><span data-stu-id="8e625-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8e625-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8e625-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="8e625-189">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-189">The command contains a default list of templates.</span></span> <span data-ttu-id="8e625-190">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8e625-191">다음 표에는 .NET Core SDK 2.1.300과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="8e625-192">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="8e625-193">템플릿</span><span class="sxs-lookup"><span data-stu-id="8e625-193">Templates</span></span>                                    | <span data-ttu-id="8e625-194">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="8e625-194">Short Name</span></span>      | <span data-ttu-id="8e625-195">언어</span><span class="sxs-lookup"><span data-stu-id="8e625-195">Language</span></span>     | <span data-ttu-id="8e625-196">Tags</span><span class="sxs-lookup"><span data-stu-id="8e625-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="8e625-197">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="8e625-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="8e625-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-198">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-199">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="8e625-199">Common/Console</span></span>                        |
| <span data-ttu-id="8e625-200">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="8e625-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-201">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-202">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-202">Common/Library</span></span>                        |
| <span data-ttu-id="8e625-203">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="8e625-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-204">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="8e625-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="8e625-206">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="8e625-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-207">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="8e625-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="8e625-209">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="8e625-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="8e625-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-210">[C#]</span></span>         | <span data-ttu-id="8e625-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="8e625-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8e625-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="8e625-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-213">[C#]</span></span>         | <span data-ttu-id="8e625-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="8e625-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8e625-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="8e625-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-216">[C#]</span></span>         | <span data-ttu-id="8e625-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="8e625-218">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="8e625-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="8e625-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-219">[C#], F#</span></span>     | <span data-ttu-id="8e625-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="8e625-220">Web/Empty</span></span>                             |
| <span data-ttu-id="8e625-221">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="8e625-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="8e625-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-222">[C#], F#</span></span>     | <span data-ttu-id="8e625-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="8e625-223">Web/MVC</span></span>                               |
| <span data-ttu-id="8e625-224">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="8e625-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="8e625-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-225">[C#]</span></span>         | <span data-ttu-id="8e625-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="8e625-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="8e625-227">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="8e625-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-228">[C#]</span></span>         | <span data-ttu-id="8e625-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="8e625-230">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="8e625-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-231">[C#]</span></span>         | <span data-ttu-id="8e625-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="8e625-233">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="8e625-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-234">[C#]</span></span>         | <span data-ttu-id="8e625-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="8e625-236">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="8e625-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-237">[C#]</span></span>         | <span data-ttu-id="8e625-238">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="8e625-239">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="8e625-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="8e625-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-240">[C#], F#</span></span>     | <span data-ttu-id="8e625-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="8e625-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="8e625-242">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="8e625-243">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-243">Config</span></span>                                |
| <span data-ttu-id="8e625-244">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="8e625-245">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-245">Config</span></span>                                |
| <span data-ttu-id="8e625-246">웹 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="8e625-247">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-247">Config</span></span>                                |
| <span data-ttu-id="8e625-248">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="8e625-249">솔루션</span><span class="sxs-lookup"><span data-stu-id="8e625-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8e625-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8e625-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="8e625-251">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-251">The command contains a default list of templates.</span></span> <span data-ttu-id="8e625-252">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8e625-253">다음 표에는 .NET Core SDK 2.0.0과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="8e625-254">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="8e625-255">템플릿</span><span class="sxs-lookup"><span data-stu-id="8e625-255">Templates</span></span>                                    | <span data-ttu-id="8e625-256">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="8e625-256">Short Name</span></span>    | <span data-ttu-id="8e625-257">언어</span><span class="sxs-lookup"><span data-stu-id="8e625-257">Language</span></span>     | <span data-ttu-id="8e625-258">Tags</span><span class="sxs-lookup"><span data-stu-id="8e625-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="8e625-259">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="8e625-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="8e625-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-260">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-261">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="8e625-261">Common/Console</span></span>      |
| <span data-ttu-id="8e625-262">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="8e625-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-263">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-264">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-264">Common/Library</span></span>      |
| <span data-ttu-id="8e625-265">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="8e625-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-266">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="8e625-267">Test/MSTest</span></span>         |
| <span data-ttu-id="8e625-268">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="8e625-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8e625-269">[C#], F#, VB</span></span> | <span data-ttu-id="8e625-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="8e625-270">Test/xUnit</span></span>          |
| <span data-ttu-id="8e625-271">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="8e625-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="8e625-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-272">[C#], F#</span></span>     | <span data-ttu-id="8e625-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="8e625-273">Web/Empty</span></span>           |
| <span data-ttu-id="8e625-274">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="8e625-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="8e625-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-275">[C#], F#</span></span>     | <span data-ttu-id="8e625-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="8e625-276">Web/MVC</span></span>             |
| <span data-ttu-id="8e625-277">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="8e625-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="8e625-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-278">[C#]</span></span>         | <span data-ttu-id="8e625-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="8e625-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="8e625-280">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="8e625-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-281">[C#]</span></span>         | <span data-ttu-id="8e625-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="8e625-283">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="8e625-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-284">[C#]</span></span>         | <span data-ttu-id="8e625-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="8e625-286">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="8e625-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="8e625-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-287">[C#]</span></span>         | <span data-ttu-id="8e625-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8e625-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="8e625-289">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="8e625-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="8e625-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-290">[C#], F#</span></span>     | <span data-ttu-id="8e625-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="8e625-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="8e625-292">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="8e625-293">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-293">Config</span></span>              |
| <span data-ttu-id="8e625-294">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="8e625-295">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-295">Config</span></span>              |
| <span data-ttu-id="8e625-296">웹 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="8e625-297">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-297">Config</span></span>              |
| <span data-ttu-id="8e625-298">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="8e625-299">솔루션</span><span class="sxs-lookup"><span data-stu-id="8e625-299">Solution</span></span>            |
| <span data-ttu-id="8e625-300">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="8e625-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="8e625-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="8e625-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8e625-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="8e625-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="8e625-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8e625-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="8e625-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e625-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8e625-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8e625-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="8e625-307">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-307">The command contains a default list of templates.</span></span> <span data-ttu-id="8e625-308">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="8e625-309">다음 표에는 .NET Core SDK 1.0.1과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="8e625-310">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="8e625-311">템플릿</span><span class="sxs-lookup"><span data-stu-id="8e625-311">Templates</span></span>            | <span data-ttu-id="8e625-312">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="8e625-312">Short Name</span></span>    | <span data-ttu-id="8e625-313">언어</span><span class="sxs-lookup"><span data-stu-id="8e625-313">Language</span></span> | <span data-ttu-id="8e625-314">Tags</span><span class="sxs-lookup"><span data-stu-id="8e625-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="8e625-315">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="8e625-315">Console Application</span></span>  | `console`     | <span data-ttu-id="8e625-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-316">[C#], F#</span></span> | <span data-ttu-id="8e625-317">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="8e625-317">Common/Console</span></span> |
| <span data-ttu-id="8e625-318">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="8e625-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-319">[C#], F#</span></span> | <span data-ttu-id="8e625-320">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="8e625-320">Common/Library</span></span> |
| <span data-ttu-id="8e625-321">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="8e625-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-322">[C#], F#</span></span> | <span data-ttu-id="8e625-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="8e625-323">Test/MSTest</span></span>    |
| <span data-ttu-id="8e625-324">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="8e625-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="8e625-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-325">[C#], F#</span></span> | <span data-ttu-id="8e625-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="8e625-326">Test/xUnit</span></span>     |
| <span data-ttu-id="8e625-327">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="8e625-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="8e625-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-328">[C#]</span></span>     | <span data-ttu-id="8e625-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="8e625-329">Web/Empty</span></span>      |
| <span data-ttu-id="8e625-330">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="8e625-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="8e625-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e625-331">[C#], F#</span></span> | <span data-ttu-id="8e625-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="8e625-332">Web/MVC</span></span>        |
| <span data-ttu-id="8e625-333">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="8e625-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="8e625-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e625-334">[C#]</span></span>     | <span data-ttu-id="8e625-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="8e625-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="8e625-336">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="8e625-337">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-337">Config</span></span>         |
| <span data-ttu-id="8e625-338">웹 구성</span><span class="sxs-lookup"><span data-stu-id="8e625-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="8e625-339">Config</span><span class="sxs-lookup"><span data-stu-id="8e625-339">Config</span></span>         |
| <span data-ttu-id="8e625-340">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="8e625-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="8e625-341">솔루션</span><span class="sxs-lookup"><span data-stu-id="8e625-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="8e625-342">옵션</span><span class="sxs-lookup"><span data-stu-id="8e625-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="8e625-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="8e625-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="8e625-344">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="8e625-345">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8e625-346">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8e625-347">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-347">Prints out help for the command.</span></span> <span data-ttu-id="8e625-348">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="8e625-349">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8e625-350">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8e625-351">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="8e625-352">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="8e625-353">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="8e625-354">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="8e625-355">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8e625-356">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="8e625-357">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-357">The language of the template to create.</span></span> <span data-ttu-id="8e625-358">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="8e625-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8e625-359">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-360">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8e625-361">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8e625-362">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-362">The name for the created output.</span></span> <span data-ttu-id="8e625-363">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="8e625-364">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8e625-365">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-365">Location to place the generated output.</span></span> <span data-ttu-id="8e625-366">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="8e625-367">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-367">Filters templates based on available types.</span></span> <span data-ttu-id="8e625-368">미리 정의된 값은 "project", "item" 또는 "other"입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="8e625-369">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8e625-370">`<PATH|NUGET_ID>` 값을 제외하면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-371">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8e625-372">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="8e625-373">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8e625-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8e625-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="8e625-375">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8e625-376">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8e625-377">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-377">Prints out help for the command.</span></span> <span data-ttu-id="8e625-378">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="8e625-379">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8e625-380">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8e625-381">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="8e625-382">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="8e625-383">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="8e625-384">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="8e625-385">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8e625-386">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="8e625-387">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-387">The language of the template to create.</span></span> <span data-ttu-id="8e625-388">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="8e625-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8e625-389">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-390">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8e625-391">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8e625-392">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-392">The name for the created output.</span></span> <span data-ttu-id="8e625-393">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="8e625-394">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8e625-395">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-395">Location to place the generated output.</span></span> <span data-ttu-id="8e625-396">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="8e625-397">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-397">Filters templates based on available types.</span></span> <span data-ttu-id="8e625-398">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="8e625-399">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-400">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8e625-401">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="8e625-402">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8e625-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8e625-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="8e625-404">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8e625-405">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8e625-406">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-406">Prints out help for the command.</span></span> <span data-ttu-id="8e625-407">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="8e625-408">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8e625-409">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8e625-410">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="8e625-411">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="8e625-412">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="8e625-413">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="8e625-414">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8e625-415">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="8e625-416">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-416">The language of the template to create.</span></span> <span data-ttu-id="8e625-417">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="8e625-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8e625-418">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-419">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8e625-420">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8e625-421">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-421">The name for the created output.</span></span> <span data-ttu-id="8e625-422">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8e625-423">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-423">Location to place the generated output.</span></span> <span data-ttu-id="8e625-424">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="8e625-425">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-425">Filters templates based on available types.</span></span> <span data-ttu-id="8e625-426">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="8e625-427">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-428">소스 `PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8e625-429">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="8e625-430">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="8e625-431">템플릿을 제거하는 데 필요한 `PATH` 또는 `NUGET_ID` 인수를 확인할 수 없는 경우, 인수 없이 `dotnet new --uninstall`을 실행하면 설치된 모든 템플릿 및 템플릿을 제거하는 데 필요한 인수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8e625-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8e625-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="8e625-433">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="8e625-434">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="8e625-435">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8e625-436">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-436">Prints out help for the command.</span></span> <span data-ttu-id="8e625-437">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="8e625-438">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="8e625-439">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8e625-440">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="8e625-441">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-441">The language of the template to create.</span></span> <span data-ttu-id="8e625-442">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="8e625-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8e625-443">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8e625-444">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8e625-445">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8e625-446">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-446">The name for the created output.</span></span> <span data-ttu-id="8e625-447">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8e625-448">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-448">Location to place the generated output.</span></span> <span data-ttu-id="8e625-449">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="8e625-450">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="8e625-450">Template options</span></span>

<span data-ttu-id="8e625-451">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-451">Each project template may have additional options available.</span></span> <span data-ttu-id="8e625-452">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="8e625-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="8e625-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="8e625-454">**콘솔**</span><span class="sxs-lookup"><span data-stu-id="8e625-454">**console**</span></span>

<span data-ttu-id="8e625-455">`--langVersion <VERSION_NUMBER>` - 생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8e625-456">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8e625-457">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-457">Not supported for F#.</span></span>

<span data-ttu-id="8e625-458">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="8e625-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="8e625-460">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-461">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-462">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-463">이 옵션은 `IndividualAuth` 또는 `OrganizationalAuth`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="8e625-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="8e625-464">**razorclasslib**</span></span>

<span data-ttu-id="8e625-465">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8e625-466">**classlib**</span></span>

<span data-ttu-id="8e625-467">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-468">값: `netcoreapp2.2`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="8e625-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8e625-469">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="8e625-470">`--langVersion <VERSION_NUMBER>` - 생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8e625-471">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8e625-472">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-472">Not supported for F#.</span></span>

<span data-ttu-id="8e625-473">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="8e625-474">**mstest, xunit**</span></span>

<span data-ttu-id="8e625-475">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="8e625-476">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="8e625-477">**nunit**</span></span>

<span data-ttu-id="8e625-478">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-479">기본값은 `netcoreapp2.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="8e625-480">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="8e625-481">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-482">**page**</span><span class="sxs-lookup"><span data-stu-id="8e625-482">**page**</span></span>

<span data-ttu-id="8e625-483">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="8e625-484">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="8e625-485">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="8e625-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="8e625-486">**viewimports**</span></span>

<span data-ttu-id="8e625-487">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="8e625-488">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="8e625-489">**web**</span><span class="sxs-lookup"><span data-stu-id="8e625-489">**web**</span></span>

<span data-ttu-id="8e625-490">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-491">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-492">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-493">이 옵션은 `IndividualAuth` 또는 `OrganizationalAuth`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="8e625-494">**mvc, 웹앱**</span><span class="sxs-lookup"><span data-stu-id="8e625-494">**mvc, webapp**</span></span>

<span data-ttu-id="8e625-495">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-496">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-496">The possible values are:</span></span>

- <span data-ttu-id="8e625-497">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="8e625-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8e625-498">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="8e625-499">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8e625-500">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8e625-501">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="8e625-502">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8e625-503">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e625-504">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-505">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8e625-506">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e625-507">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-508">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="8e625-509">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-510">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="8e625-511">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-512">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e625-513">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e625-514">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8e625-515">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8e625-516">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e625-517">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8e625-518">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8e625-519">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-520">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8e625-521">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e625-522">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-523">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8e625-524">`--callback-path <PATH>` - 리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8e625-525">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-526">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="8e625-527">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e625-528">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8e625-529">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-530">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-531">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8e625-532">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="8e625-533">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e625-534">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-535">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="8e625-536">**webapi**</span></span>

<span data-ttu-id="8e625-537">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-538">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-538">The possible values are:</span></span>

- <span data-ttu-id="8e625-539">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="8e625-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8e625-540">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8e625-541">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8e625-542">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8e625-543">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e625-544">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-545">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8e625-546">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e625-547">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-548">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e625-549">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-550">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8e625-551">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8e625-552">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-553">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8e625-554">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8e625-555">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-556">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8e625-557">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e625-558">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-559">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8e625-560">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e625-561">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8e625-562">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-563">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-564">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8e625-565">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="8e625-566">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e625-567">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-568">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="8e625-569">**globaljson**</span></span>

<span data-ttu-id="8e625-570">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8e625-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8e625-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="8e625-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="8e625-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="8e625-573">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8e625-574">**classlib**</span></span>

<span data-ttu-id="8e625-575">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-576">값: `netcoreapp2.1`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="8e625-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8e625-577">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="8e625-578">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="8e625-579">**mstest, xunit**</span></span>

<span data-ttu-id="8e625-580">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="8e625-581">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="8e625-582">**globaljson**</span></span>

<span data-ttu-id="8e625-583">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="8e625-584">**web**</span><span class="sxs-lookup"><span data-stu-id="8e625-584">**web**</span></span>

<span data-ttu-id="8e625-585">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-586">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-587">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-588">이 옵션은 `IndividualAuth` 또는 `OrganizationalAuth`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="8e625-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="8e625-589">**webapi**</span></span>

<span data-ttu-id="8e625-590">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-591">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-591">The possible values are:</span></span>

- <span data-ttu-id="8e625-592">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="8e625-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8e625-593">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8e625-594">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8e625-595">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8e625-596">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e625-597">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-598">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8e625-599">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e625-600">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-601">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e625-602">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-603">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8e625-604">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8e625-605">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-606">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8e625-607">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8e625-608">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-609">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8e625-610">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e625-611">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-612">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8e625-613">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e625-614">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8e625-615">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-616">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e625-617">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-618">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-619">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-620">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8e625-621">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="8e625-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="8e625-622">**mvc, razor**</span></span>

<span data-ttu-id="8e625-623">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-624">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-624">The possible values are:</span></span>

- <span data-ttu-id="8e625-625">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="8e625-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8e625-626">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="8e625-627">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8e625-628">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8e625-629">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="8e625-630">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8e625-631">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e625-632">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-633">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8e625-634">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e625-635">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-636">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="8e625-637">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-638">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="8e625-639">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-640">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e625-641">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e625-642">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8e625-643">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8e625-644">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e625-645">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8e625-646">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8e625-647">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-648">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8e625-649">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e625-650">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-651">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8e625-652">`--callback-path <PATH>` - 리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8e625-653">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-654">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="8e625-655">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e625-656">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8e625-657">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="8e625-658">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="8e625-659">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e625-660">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-661">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-662">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="8e625-663">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8e625-664">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="8e625-665">**page**</span><span class="sxs-lookup"><span data-stu-id="8e625-665">**page**</span></span>

<span data-ttu-id="8e625-666">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="8e625-667">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="8e625-668">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="8e625-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="8e625-669">**viewimports**</span></span>

<span data-ttu-id="8e625-670">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="8e625-671">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8e625-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8e625-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="8e625-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="8e625-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="8e625-674">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8e625-675">**classlib**</span></span>

<span data-ttu-id="8e625-676">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-677">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="8e625-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8e625-678">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="8e625-679">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="8e625-680">**mstest, xunit**</span></span>

<span data-ttu-id="8e625-681">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="8e625-682">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="8e625-683">**globaljson**</span></span>

<span data-ttu-id="8e625-684">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="8e625-685">**web**</span><span class="sxs-lookup"><span data-stu-id="8e625-685">**web**</span></span>

<span data-ttu-id="8e625-686">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8e625-687">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="8e625-688">**webapi**</span></span>

<span data-ttu-id="8e625-689">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-690">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-690">The possible values are:</span></span>

- <span data-ttu-id="8e625-691">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="8e625-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8e625-692">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8e625-693">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8e625-694">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8e625-695">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e625-696">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-697">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8e625-698">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e625-699">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-700">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e625-701">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-702">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8e625-703">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8e625-704">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-705">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8e625-706">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8e625-707">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-708">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8e625-709">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e625-710">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-711">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8e625-712">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e625-713">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8e625-714">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8e625-715">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e625-716">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-717">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="8e625-718">**mvc, razor**</span></span>

<span data-ttu-id="8e625-719">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-720">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-720">The possible values are:</span></span>

- <span data-ttu-id="8e625-721">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="8e625-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8e625-722">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="8e625-723">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8e625-724">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8e625-725">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="8e625-726">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8e625-727">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8e625-728">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-729">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8e625-730">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8e625-731">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-732">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="8e625-733">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-734">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="8e625-735">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-736">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8e625-737">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e625-738">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8e625-739">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8e625-740">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8e625-741">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8e625-742">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8e625-743">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-744">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8e625-745">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8e625-746">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8e625-747">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8e625-748">`--callback-path <PATH>` - 리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8e625-749">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8e625-750">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="8e625-751">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8e625-752">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8e625-753">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8e625-754">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="8e625-755">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8e625-756">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8e625-757">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8e625-758">**page**</span><span class="sxs-lookup"><span data-stu-id="8e625-758">**page**</span></span>

<span data-ttu-id="8e625-759">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="8e625-760">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="8e625-761">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="8e625-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="8e625-762">**viewimports**</span></span>

<span data-ttu-id="8e625-763">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="8e625-764">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8e625-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8e625-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="8e625-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="8e625-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="8e625-767">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-768">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="8e625-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="8e625-769">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="8e625-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8e625-770">**classlib**</span></span>

<span data-ttu-id="8e625-771">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-772">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="8e625-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="8e625-773">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="8e625-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="8e625-774">**mvc**</span></span>

<span data-ttu-id="8e625-775">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e625-776">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="8e625-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="8e625-777">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="8e625-778">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8e625-779">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="8e625-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="8e625-780">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-780">The default value is `None`.</span></span>

<span data-ttu-id="8e625-781">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="8e625-782">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="8e625-782">Values: `true` or `false`.</span></span> <span data-ttu-id="8e625-783">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="8e625-784">예제</span><span class="sxs-lookup"><span data-stu-id="8e625-784">Examples</span></span>

<span data-ttu-id="8e625-785">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="8e625-786">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="8e625-787">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="8e625-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="8e625-788">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="8e625-789">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="8e625-790">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="8e625-791">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="8e625-792">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="8e625-793">*ng*와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="8e625-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="8e625-794">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8e625-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="8e625-795">ASP.NET Core용 단일 페이지 애플리케이션 템플릿 버전 2.0을 설치합니다(.NET Core SDK 1.1 및 이후 버전에서만 사용할 수 있는 명령 옵션).</span><span class="sxs-lookup"><span data-stu-id="8e625-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="8e625-796">현재 디렉터리에서 SDK 버전을 2.0.0으로 설정하여 *global.json*을 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="8e625-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="8e625-797">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e625-797">See also</span></span>

- [<span data-ttu-id="8e625-798">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="8e625-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="8e625-799">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="8e625-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- <span data-ttu-id="8e625-800">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="8e625-800">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="8e625-801">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="8e625-801">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
