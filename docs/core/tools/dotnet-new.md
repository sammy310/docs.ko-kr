---
title: dotnet new 명령
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
ms.date: 05/06/2019
ms.openlocfilehash: c9529e135f48c80f445c91038294a3e7266486f1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420470"
---
# <a name="dotnet-new"></a><span data-ttu-id="6ce23-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6ce23-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6ce23-104">name</span><span class="sxs-lookup"><span data-stu-id="6ce23-104">Name</span></span>

<span data-ttu-id="6ce23-105">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6ce23-106">개요</span><span class="sxs-lookup"><span data-stu-id="6ce23-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="6ce23-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6ce23-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6ce23-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6ce23-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6ce23-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6ce23-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6ce23-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6ce23-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="6ce23-111">설명</span><span class="sxs-lookup"><span data-stu-id="6ce23-111">Description</span></span>

<span data-ttu-id="6ce23-112">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="6ce23-113">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="6ce23-114">인수</span><span class="sxs-lookup"><span data-stu-id="6ce23-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="6ce23-115">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="6ce23-116">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="6ce23-117">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="6ce23-118">`TEMPLATE` 값이 **템플릿** 또는 **약식 이름** 열의 텍스트와 정확히 일치하지 않는 경우 해당 두 열에 대해 부분 문자열 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="6ce23-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6ce23-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6ce23-120">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-120">The command contains a default list of templates.</span></span> <span data-ttu-id="6ce23-121">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="6ce23-122">다음 표에서는 .NET Core SDK 2.2.100과 함께 사전 설치된 템플릿을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="6ce23-123">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="6ce23-124">템플릿</span><span class="sxs-lookup"><span data-stu-id="6ce23-124">Templates</span></span>                                    | <span data-ttu-id="6ce23-125">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="6ce23-125">Short Name</span></span>        | <span data-ttu-id="6ce23-126">언어</span><span class="sxs-lookup"><span data-stu-id="6ce23-126">Language</span></span>     | <span data-ttu-id="6ce23-127">Tags</span><span class="sxs-lookup"><span data-stu-id="6ce23-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="6ce23-128">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6ce23-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="6ce23-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-129">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-130">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="6ce23-130">Common/Console</span></span>                        |
| <span data-ttu-id="6ce23-131">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="6ce23-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-132">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-133">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-133">Common/Library</span></span>                        |
| <span data-ttu-id="6ce23-134">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="6ce23-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-135">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="6ce23-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="6ce23-137">NUnit 3 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="6ce23-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-138">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="6ce23-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="6ce23-140">NUnit 3 테스트 항목</span><span class="sxs-lookup"><span data-stu-id="6ce23-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="6ce23-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-141">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="6ce23-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="6ce23-143">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="6ce23-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-144">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="6ce23-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="6ce23-146">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="6ce23-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="6ce23-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-147">[C#]</span></span>         | <span data-ttu-id="6ce23-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="6ce23-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="6ce23-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="6ce23-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-150">[C#]</span></span>         | <span data-ttu-id="6ce23-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="6ce23-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="6ce23-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="6ce23-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-153">[C#]</span></span>         | <span data-ttu-id="6ce23-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="6ce23-155">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="6ce23-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="6ce23-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-156">[C#], F#</span></span>     | <span data-ttu-id="6ce23-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="6ce23-157">Web/Empty</span></span>                             |
| <span data-ttu-id="6ce23-158">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="6ce23-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="6ce23-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-159">[C#], F#</span></span>     | <span data-ttu-id="6ce23-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="6ce23-160">Web/MVC</span></span>                               |
| <span data-ttu-id="6ce23-161">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="6ce23-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="6ce23-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="6ce23-162">`webapp`, `razor`</span></span> | <span data-ttu-id="6ce23-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-163">[C#]</span></span>         | <span data-ttu-id="6ce23-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="6ce23-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="6ce23-165">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="6ce23-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-166">[C#]</span></span>         | <span data-ttu-id="6ce23-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="6ce23-168">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="6ce23-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-169">[C#]</span></span>         | <span data-ttu-id="6ce23-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="6ce23-171">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="6ce23-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-172">[C#]</span></span>         | <span data-ttu-id="6ce23-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="6ce23-174">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="6ce23-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-175">[C#]</span></span>         | <span data-ttu-id="6ce23-176">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="6ce23-177">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="6ce23-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="6ce23-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-178">[C#], F#</span></span>     | <span data-ttu-id="6ce23-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="6ce23-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="6ce23-180">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="6ce23-181">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-181">Config</span></span>                                |
| <span data-ttu-id="6ce23-182">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="6ce23-183">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-183">Config</span></span>                                |
| <span data-ttu-id="6ce23-184">웹 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="6ce23-185">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-185">Config</span></span>                                |
| <span data-ttu-id="6ce23-186">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="6ce23-187">솔루션</span><span class="sxs-lookup"><span data-stu-id="6ce23-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6ce23-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6ce23-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6ce23-189">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-189">The command contains a default list of templates.</span></span> <span data-ttu-id="6ce23-190">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="6ce23-191">다음 표에는 .NET Core SDK 2.1.300과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="6ce23-192">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="6ce23-193">템플릿</span><span class="sxs-lookup"><span data-stu-id="6ce23-193">Templates</span></span>                                    | <span data-ttu-id="6ce23-194">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="6ce23-194">Short Name</span></span>      | <span data-ttu-id="6ce23-195">언어</span><span class="sxs-lookup"><span data-stu-id="6ce23-195">Language</span></span>     | <span data-ttu-id="6ce23-196">Tags</span><span class="sxs-lookup"><span data-stu-id="6ce23-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="6ce23-197">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6ce23-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="6ce23-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-198">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-199">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="6ce23-199">Common/Console</span></span>                        |
| <span data-ttu-id="6ce23-200">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="6ce23-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-201">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-202">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-202">Common/Library</span></span>                        |
| <span data-ttu-id="6ce23-203">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="6ce23-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-204">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="6ce23-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="6ce23-206">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="6ce23-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-207">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="6ce23-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="6ce23-209">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="6ce23-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="6ce23-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-210">[C#]</span></span>         | <span data-ttu-id="6ce23-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="6ce23-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="6ce23-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="6ce23-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-213">[C#]</span></span>         | <span data-ttu-id="6ce23-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="6ce23-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="6ce23-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="6ce23-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-216">[C#]</span></span>         | <span data-ttu-id="6ce23-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="6ce23-218">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="6ce23-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="6ce23-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-219">[C#], F#</span></span>     | <span data-ttu-id="6ce23-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="6ce23-220">Web/Empty</span></span>                             |
| <span data-ttu-id="6ce23-221">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="6ce23-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="6ce23-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-222">[C#], F#</span></span>     | <span data-ttu-id="6ce23-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="6ce23-223">Web/MVC</span></span>                               |
| <span data-ttu-id="6ce23-224">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="6ce23-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="6ce23-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-225">[C#]</span></span>         | <span data-ttu-id="6ce23-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="6ce23-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="6ce23-227">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="6ce23-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-228">[C#]</span></span>         | <span data-ttu-id="6ce23-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="6ce23-230">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="6ce23-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-231">[C#]</span></span>         | <span data-ttu-id="6ce23-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="6ce23-233">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="6ce23-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-234">[C#]</span></span>         | <span data-ttu-id="6ce23-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="6ce23-236">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="6ce23-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-237">[C#]</span></span>         | <span data-ttu-id="6ce23-238">Web/Razor/Library/Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="6ce23-239">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="6ce23-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="6ce23-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-240">[C#], F#</span></span>     | <span data-ttu-id="6ce23-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="6ce23-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="6ce23-242">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="6ce23-243">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-243">Config</span></span>                                |
| <span data-ttu-id="6ce23-244">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="6ce23-245">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-245">Config</span></span>                                |
| <span data-ttu-id="6ce23-246">웹 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="6ce23-247">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-247">Config</span></span>                                |
| <span data-ttu-id="6ce23-248">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="6ce23-249">솔루션</span><span class="sxs-lookup"><span data-stu-id="6ce23-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6ce23-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6ce23-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="6ce23-251">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-251">The command contains a default list of templates.</span></span> <span data-ttu-id="6ce23-252">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="6ce23-253">다음 표에는 .NET Core SDK 2.0.0과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="6ce23-254">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="6ce23-255">템플릿</span><span class="sxs-lookup"><span data-stu-id="6ce23-255">Templates</span></span>                                    | <span data-ttu-id="6ce23-256">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="6ce23-256">Short Name</span></span>    | <span data-ttu-id="6ce23-257">언어</span><span class="sxs-lookup"><span data-stu-id="6ce23-257">Language</span></span>     | <span data-ttu-id="6ce23-258">Tags</span><span class="sxs-lookup"><span data-stu-id="6ce23-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="6ce23-259">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6ce23-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="6ce23-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-260">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-261">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="6ce23-261">Common/Console</span></span>      |
| <span data-ttu-id="6ce23-262">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="6ce23-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-263">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-264">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-264">Common/Library</span></span>      |
| <span data-ttu-id="6ce23-265">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="6ce23-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-266">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="6ce23-267">Test/MSTest</span></span>         |
| <span data-ttu-id="6ce23-268">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="6ce23-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="6ce23-269">[C#], F#, VB</span></span> | <span data-ttu-id="6ce23-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="6ce23-270">Test/xUnit</span></span>          |
| <span data-ttu-id="6ce23-271">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="6ce23-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="6ce23-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-272">[C#], F#</span></span>     | <span data-ttu-id="6ce23-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="6ce23-273">Web/Empty</span></span>           |
| <span data-ttu-id="6ce23-274">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="6ce23-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="6ce23-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-275">[C#], F#</span></span>     | <span data-ttu-id="6ce23-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="6ce23-276">Web/MVC</span></span>             |
| <span data-ttu-id="6ce23-277">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="6ce23-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="6ce23-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-278">[C#]</span></span>         | <span data-ttu-id="6ce23-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="6ce23-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="6ce23-280">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="6ce23-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-281">[C#]</span></span>         | <span data-ttu-id="6ce23-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="6ce23-283">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="6ce23-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-284">[C#]</span></span>         | <span data-ttu-id="6ce23-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="6ce23-286">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="6ce23-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="6ce23-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-287">[C#]</span></span>         | <span data-ttu-id="6ce23-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="6ce23-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="6ce23-289">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="6ce23-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="6ce23-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-290">[C#], F#</span></span>     | <span data-ttu-id="6ce23-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="6ce23-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="6ce23-292">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="6ce23-293">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-293">Config</span></span>              |
| <span data-ttu-id="6ce23-294">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="6ce23-295">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-295">Config</span></span>              |
| <span data-ttu-id="6ce23-296">웹 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="6ce23-297">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-297">Config</span></span>              |
| <span data-ttu-id="6ce23-298">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="6ce23-299">솔루션</span><span class="sxs-lookup"><span data-stu-id="6ce23-299">Solution</span></span>            |
| <span data-ttu-id="6ce23-300">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="6ce23-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="6ce23-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="6ce23-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="6ce23-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="6ce23-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="6ce23-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="6ce23-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="6ce23-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ce23-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6ce23-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6ce23-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6ce23-307">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-307">The command contains a default list of templates.</span></span> <span data-ttu-id="6ce23-308">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="6ce23-309">다음 표에는 .NET Core SDK 1.0.1과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="6ce23-310">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="6ce23-311">템플릿</span><span class="sxs-lookup"><span data-stu-id="6ce23-311">Templates</span></span>            | <span data-ttu-id="6ce23-312">짧은 이름</span><span class="sxs-lookup"><span data-stu-id="6ce23-312">Short Name</span></span>    | <span data-ttu-id="6ce23-313">언어</span><span class="sxs-lookup"><span data-stu-id="6ce23-313">Language</span></span> | <span data-ttu-id="6ce23-314">Tags</span><span class="sxs-lookup"><span data-stu-id="6ce23-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="6ce23-315">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6ce23-315">Console Application</span></span>  | `console`     | <span data-ttu-id="6ce23-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-316">[C#], F#</span></span> | <span data-ttu-id="6ce23-317">일반/콘솔</span><span class="sxs-lookup"><span data-stu-id="6ce23-317">Common/Console</span></span> |
| <span data-ttu-id="6ce23-318">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="6ce23-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-319">[C#], F#</span></span> | <span data-ttu-id="6ce23-320">일반/라이브러리</span><span class="sxs-lookup"><span data-stu-id="6ce23-320">Common/Library</span></span> |
| <span data-ttu-id="6ce23-321">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="6ce23-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-322">[C#], F#</span></span> | <span data-ttu-id="6ce23-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="6ce23-323">Test/MSTest</span></span>    |
| <span data-ttu-id="6ce23-324">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6ce23-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="6ce23-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-325">[C#], F#</span></span> | <span data-ttu-id="6ce23-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="6ce23-326">Test/xUnit</span></span>     |
| <span data-ttu-id="6ce23-327">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="6ce23-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="6ce23-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-328">[C#]</span></span>     | <span data-ttu-id="6ce23-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="6ce23-329">Web/Empty</span></span>      |
| <span data-ttu-id="6ce23-330">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="6ce23-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="6ce23-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="6ce23-331">[C#], F#</span></span> | <span data-ttu-id="6ce23-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="6ce23-332">Web/MVC</span></span>        |
| <span data-ttu-id="6ce23-333">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="6ce23-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="6ce23-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="6ce23-334">[C#]</span></span>     | <span data-ttu-id="6ce23-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="6ce23-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="6ce23-336">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="6ce23-337">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-337">Config</span></span>         |
| <span data-ttu-id="6ce23-338">웹 구성</span><span class="sxs-lookup"><span data-stu-id="6ce23-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="6ce23-339">Config</span><span class="sxs-lookup"><span data-stu-id="6ce23-339">Config</span></span>         |
| <span data-ttu-id="6ce23-340">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="6ce23-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="6ce23-341">솔루션</span><span class="sxs-lookup"><span data-stu-id="6ce23-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="6ce23-342">옵션</span><span class="sxs-lookup"><span data-stu-id="6ce23-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="6ce23-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6ce23-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="6ce23-344">지정된 명령이 실행되어 템플릿 만들기로 이어질 경우 발생하는 작업에 대한 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="6ce23-345">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="6ce23-346">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="6ce23-347">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-347">Prints out help for the command.</span></span> <span data-ttu-id="6ce23-348">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="6ce23-349">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="6ce23-350">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="6ce23-351">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="6ce23-352">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="6ce23-353">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="6ce23-354">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="6ce23-355">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="6ce23-356">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="6ce23-357">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-357">The language of the template to create.</span></span> <span data-ttu-id="6ce23-358">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="6ce23-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="6ce23-359">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-360">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="6ce23-361">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="6ce23-362">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-362">The name for the created output.</span></span> <span data-ttu-id="6ce23-363">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="6ce23-364">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6ce23-365">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-365">Location to place the generated output.</span></span> <span data-ttu-id="6ce23-366">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="6ce23-367">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-367">Filters templates based on available types.</span></span> <span data-ttu-id="6ce23-368">미리 정의된 값은 "project", "item" 또는 "other"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="6ce23-369">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="6ce23-370">`<PATH|NUGET_ID>` 값을 제외하면 현재 설치된 모든 템플릿 팩과 연결된 템플릿이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-371">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="6ce23-372">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="6ce23-373">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6ce23-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6ce23-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="6ce23-375">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="6ce23-376">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="6ce23-377">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-377">Prints out help for the command.</span></span> <span data-ttu-id="6ce23-378">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="6ce23-379">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="6ce23-380">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="6ce23-381">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="6ce23-382">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="6ce23-383">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="6ce23-384">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="6ce23-385">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="6ce23-386">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="6ce23-387">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-387">The language of the template to create.</span></span> <span data-ttu-id="6ce23-388">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="6ce23-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="6ce23-389">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-390">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="6ce23-391">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="6ce23-392">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-392">The name for the created output.</span></span> <span data-ttu-id="6ce23-393">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="6ce23-394">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6ce23-395">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-395">Location to place the generated output.</span></span> <span data-ttu-id="6ce23-396">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="6ce23-397">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-397">Filters templates based on available types.</span></span> <span data-ttu-id="6ce23-398">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="6ce23-399">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-400">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="6ce23-401">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="6ce23-402">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6ce23-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6ce23-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="6ce23-404">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="6ce23-405">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="6ce23-406">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-406">Prints out help for the command.</span></span> <span data-ttu-id="6ce23-407">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="6ce23-408">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="6ce23-409">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="6ce23-410">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="6ce23-411">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="6ce23-412">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="6ce23-413">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="6ce23-414">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="6ce23-415">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="6ce23-416">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-416">The language of the template to create.</span></span> <span data-ttu-id="6ce23-417">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="6ce23-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="6ce23-418">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-419">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="6ce23-420">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="6ce23-421">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-421">The name for the created output.</span></span> <span data-ttu-id="6ce23-422">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6ce23-423">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-423">Location to place the generated output.</span></span> <span data-ttu-id="6ce23-424">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="6ce23-425">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-425">Filters templates based on available types.</span></span> <span data-ttu-id="6ce23-426">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="6ce23-427">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-428">소스 `PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="6ce23-429">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="6ce23-430">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="6ce23-431">템플릿을 제거하는 데 필요한 `PATH` 또는 `NUGET_ID` 인수를 확인할 수 없는 경우, 인수 없이 `dotnet new --uninstall`을 실행하면 설치된 모든 템플릿 및 템플릿을 제거하는 데 필요한 인수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6ce23-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6ce23-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="6ce23-433">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="6ce23-434">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="6ce23-435">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="6ce23-436">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-436">Prints out help for the command.</span></span> <span data-ttu-id="6ce23-437">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="6ce23-438">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="6ce23-439">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="6ce23-440">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="6ce23-441">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-441">The language of the template to create.</span></span> <span data-ttu-id="6ce23-442">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="6ce23-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="6ce23-443">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce23-444">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="6ce23-445">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="6ce23-446">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-446">The name for the created output.</span></span> <span data-ttu-id="6ce23-447">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6ce23-448">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-448">Location to place the generated output.</span></span> <span data-ttu-id="6ce23-449">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="6ce23-450">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="6ce23-450">Template options</span></span>

<span data-ttu-id="6ce23-451">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-451">Each project template may have additional options available.</span></span> <span data-ttu-id="6ce23-452">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="6ce23-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6ce23-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6ce23-454">**콘솔**</span><span class="sxs-lookup"><span data-stu-id="6ce23-454">**console**</span></span>

<span data-ttu-id="6ce23-455">`--langVersion <VERSION_NUMBER>` - 생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="6ce23-456">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="6ce23-457">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-457">Not supported for F#.</span></span>

<span data-ttu-id="6ce23-458">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="6ce23-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="6ce23-460">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-461">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-462">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-463">이 옵션은 `IndividualAuth` 또는 `OrganizationalAuth`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="6ce23-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="6ce23-464">**razorclasslib**</span></span>

<span data-ttu-id="6ce23-465">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="6ce23-466">**classlib**</span></span>

<span data-ttu-id="6ce23-467">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-468">값: `netcoreapp2.2`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="6ce23-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="6ce23-469">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="6ce23-470">`--langVersion <VERSION_NUMBER>` - 생성된 프로젝트 파일에서 `LangVersion` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="6ce23-471">예를 들어 C# 7.3을 사용하려면 `--langVersion 7.3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="6ce23-472">F#에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-472">Not supported for F#.</span></span>

<span data-ttu-id="6ce23-473">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="6ce23-474">**mstest, xunit**</span></span>

<span data-ttu-id="6ce23-475">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="6ce23-476">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="6ce23-477">**nunit**</span></span>

<span data-ttu-id="6ce23-478">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-479">기본값은 `netcoreapp2.1`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="6ce23-480">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="6ce23-481">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-482">**page**</span><span class="sxs-lookup"><span data-stu-id="6ce23-482">**page**</span></span>

<span data-ttu-id="6ce23-483">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="6ce23-484">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="6ce23-485">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="6ce23-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="6ce23-486">**viewimports**</span></span>

<span data-ttu-id="6ce23-487">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="6ce23-488">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="6ce23-489">**web**</span><span class="sxs-lookup"><span data-stu-id="6ce23-489">**web**</span></span>

<span data-ttu-id="6ce23-490">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-491">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-492">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-493">이 옵션은 `IndividualAuth` 또는 `OrganizationalAuth`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="6ce23-494">**mvc, 웹앱**</span><span class="sxs-lookup"><span data-stu-id="6ce23-494">**mvc, webapp**</span></span>

<span data-ttu-id="6ce23-495">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-496">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-496">The possible values are:</span></span>

- <span data-ttu-id="6ce23-497">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6ce23-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="6ce23-498">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="6ce23-499">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="6ce23-500">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="6ce23-501">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="6ce23-502">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="6ce23-503">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6ce23-504">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-505">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="6ce23-506">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6ce23-507">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-508">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="6ce23-509">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-510">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="6ce23-511">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-512">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6ce23-513">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="6ce23-514">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="6ce23-515">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="6ce23-516">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="6ce23-517">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="6ce23-518">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="6ce23-519">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-520">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="6ce23-521">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6ce23-522">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-523">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="6ce23-524">`--callback-path <PATH>` - 리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="6ce23-525">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-526">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="6ce23-527">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="6ce23-528">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="6ce23-529">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-530">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-531">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="6ce23-532">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="6ce23-533">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6ce23-534">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-535">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="6ce23-536">**webapi**</span></span>

<span data-ttu-id="6ce23-537">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-538">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-538">The possible values are:</span></span>

- <span data-ttu-id="6ce23-539">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6ce23-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="6ce23-540">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="6ce23-541">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="6ce23-542">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="6ce23-543">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6ce23-544">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-545">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="6ce23-546">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6ce23-547">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-548">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6ce23-549">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-550">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="6ce23-551">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="6ce23-552">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-553">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="6ce23-554">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="6ce23-555">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-556">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="6ce23-557">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6ce23-558">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-559">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="6ce23-560">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="6ce23-561">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="6ce23-562">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-563">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-564">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="6ce23-565">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="6ce23-566">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6ce23-567">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-568">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="6ce23-569">**globaljson**</span></span>

<span data-ttu-id="6ce23-570">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6ce23-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6ce23-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6ce23-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="6ce23-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="6ce23-573">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="6ce23-574">**classlib**</span></span>

<span data-ttu-id="6ce23-575">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-576">값: `netcoreapp2.1`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="6ce23-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="6ce23-577">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="6ce23-578">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="6ce23-579">**mstest, xunit**</span></span>

<span data-ttu-id="6ce23-580">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="6ce23-581">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="6ce23-582">**globaljson**</span></span>

<span data-ttu-id="6ce23-583">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="6ce23-584">**web**</span><span class="sxs-lookup"><span data-stu-id="6ce23-584">**web**</span></span>

<span data-ttu-id="6ce23-585">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-586">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-587">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-588">이 옵션은 `IndividualAuth` 또는 `OrganizationalAuth`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="6ce23-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="6ce23-589">**webapi**</span></span>

<span data-ttu-id="6ce23-590">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-591">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-591">The possible values are:</span></span>

- <span data-ttu-id="6ce23-592">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6ce23-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="6ce23-593">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="6ce23-594">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="6ce23-595">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="6ce23-596">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6ce23-597">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-598">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="6ce23-599">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6ce23-600">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-601">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6ce23-602">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-603">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="6ce23-604">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="6ce23-605">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-606">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="6ce23-607">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="6ce23-608">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-609">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="6ce23-610">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6ce23-611">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-612">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="6ce23-613">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="6ce23-614">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="6ce23-615">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-616">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6ce23-617">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-618">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-619">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-620">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="6ce23-621">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="6ce23-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="6ce23-622">**mvc, razor**</span></span>

<span data-ttu-id="6ce23-623">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-624">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-624">The possible values are:</span></span>

- <span data-ttu-id="6ce23-625">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6ce23-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="6ce23-626">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="6ce23-627">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="6ce23-628">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="6ce23-629">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="6ce23-630">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="6ce23-631">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6ce23-632">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-633">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="6ce23-634">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6ce23-635">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-636">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="6ce23-637">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-638">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="6ce23-639">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-640">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6ce23-641">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="6ce23-642">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="6ce23-643">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="6ce23-644">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="6ce23-645">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="6ce23-646">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="6ce23-647">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-648">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="6ce23-649">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6ce23-650">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-651">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="6ce23-652">`--callback-path <PATH>` - 리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="6ce23-653">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-654">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="6ce23-655">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="6ce23-656">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="6ce23-657">`--exclude-launch-settings` - 생성된 템플릿에서 *launchSettings.json*을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="6ce23-658">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="6ce23-659">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6ce23-660">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-661">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-662">`--no-https` - 프로젝트에는 HTTPS가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="6ce23-663">`app.UseHsts` 및 `app.UseHttpsRedirection`은 `Startup.Configure`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="6ce23-664">이 옵션은 `Individual`, `IndividualB2C`, `SingleOrg` 또는 `MultiOrg`를 사용하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="6ce23-665">**page**</span><span class="sxs-lookup"><span data-stu-id="6ce23-665">**page**</span></span>

<span data-ttu-id="6ce23-666">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="6ce23-667">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="6ce23-668">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="6ce23-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="6ce23-669">**viewimports**</span></span>

<span data-ttu-id="6ce23-670">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="6ce23-671">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6ce23-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6ce23-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="6ce23-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="6ce23-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="6ce23-674">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="6ce23-675">**classlib**</span></span>

<span data-ttu-id="6ce23-676">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-677">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="6ce23-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="6ce23-678">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="6ce23-679">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="6ce23-680">**mstest, xunit**</span></span>

<span data-ttu-id="6ce23-681">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="6ce23-682">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="6ce23-683">**globaljson**</span></span>

<span data-ttu-id="6ce23-684">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="6ce23-685">**web**</span><span class="sxs-lookup"><span data-stu-id="6ce23-685">**web**</span></span>

<span data-ttu-id="6ce23-686">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="6ce23-687">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="6ce23-688">**webapi**</span></span>

<span data-ttu-id="6ce23-689">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-690">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-690">The possible values are:</span></span>

- <span data-ttu-id="6ce23-691">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6ce23-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="6ce23-692">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="6ce23-693">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="6ce23-694">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="6ce23-695">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6ce23-696">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-697">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="6ce23-698">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6ce23-699">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-700">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6ce23-701">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-702">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="6ce23-703">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="6ce23-704">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-705">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="6ce23-706">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="6ce23-707">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-708">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="6ce23-709">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6ce23-710">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-711">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="6ce23-712">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="6ce23-713">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="6ce23-714">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="6ce23-715">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6ce23-716">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-717">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="6ce23-718">**mvc, razor**</span></span>

<span data-ttu-id="6ce23-719">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-720">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-720">The possible values are:</span></span>

- <span data-ttu-id="6ce23-721">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6ce23-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="6ce23-722">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="6ce23-723">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="6ce23-724">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="6ce23-725">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="6ce23-726">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="6ce23-727">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="6ce23-728">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-729">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="6ce23-730">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="6ce23-731">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-732">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="6ce23-733">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-734">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="6ce23-735">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-736">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="6ce23-737">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="6ce23-738">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="6ce23-739">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="6ce23-740">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="6ce23-741">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="6ce23-742">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="6ce23-743">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-744">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="6ce23-745">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="6ce23-746">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="6ce23-747">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="6ce23-748">`--callback-path <PATH>` - 리디렉션 URI의 애플리케이션 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="6ce23-749">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="6ce23-750">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="6ce23-751">`-r|--org-read-access` - 디렉터리에 대한 이 애플리케이션 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="6ce23-752">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="6ce23-753">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="6ce23-754">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="6ce23-755">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="6ce23-756">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="6ce23-757">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="6ce23-758">**page**</span><span class="sxs-lookup"><span data-stu-id="6ce23-758">**page**</span></span>

<span data-ttu-id="6ce23-759">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="6ce23-760">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="6ce23-761">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="6ce23-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="6ce23-762">**viewimports**</span></span>

<span data-ttu-id="6ce23-763">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="6ce23-764">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6ce23-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6ce23-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6ce23-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="6ce23-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="6ce23-767">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-768">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="6ce23-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="6ce23-769">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="6ce23-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="6ce23-770">**classlib**</span></span>

<span data-ttu-id="6ce23-771">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-772">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="6ce23-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="6ce23-773">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="6ce23-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="6ce23-774">**mvc**</span></span>

<span data-ttu-id="6ce23-775">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="6ce23-776">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="6ce23-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="6ce23-777">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="6ce23-778">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="6ce23-779">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="6ce23-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="6ce23-780">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-780">The default value is `None`.</span></span>

<span data-ttu-id="6ce23-781">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="6ce23-782">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="6ce23-782">Values: `true` or `false`.</span></span> <span data-ttu-id="6ce23-783">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="6ce23-784">예</span><span class="sxs-lookup"><span data-stu-id="6ce23-784">Examples</span></span>

<span data-ttu-id="6ce23-785">템플릿 이름을 지정하여 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="6ce23-786">현재 디렉터리에 F# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="6ce23-787">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="6ce23-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="6ce23-788">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="6ce23-789">새 xUnit 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="6ce23-790">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="6ce23-791">*we* 부분 문자열과 일치하는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="6ce23-792">정확히 일치하는 항목을 찾을 수 없으므로 부분 문자열 일치는 약식 이름과 열 모두에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="6ce23-793">*ng*와 일치하는 템플릿을 호출해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6ce23-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="6ce23-794">단일 일치 항목을 확인할 수 없는 경우 부분적으로 일치하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce23-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="6ce23-795">ASP.NET Core용 단일 페이지 애플리케이션 템플릿 버전 2.0을 설치합니다(.NET Core SDK 1.1 및 이후 버전에서만 사용할 수 있는 명령 옵션).</span><span class="sxs-lookup"><span data-stu-id="6ce23-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="6ce23-796">현재 디렉터리에서 SDK 버전을 2.0.0으로 설정하여 *global.json*을 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="6ce23-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="6ce23-797">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ce23-797">See also</span></span>

- [<span data-ttu-id="6ce23-798">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="6ce23-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="6ce23-799">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="6ce23-799">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="6ce23-800">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="6ce23-800">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="6ce23-801">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="6ce23-801">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
