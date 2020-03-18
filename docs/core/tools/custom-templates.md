---
title: dotnet new에 대한 사용자 지정 템플릿
description: 모든 형식의 .NET 프로젝트 또는 파일에 대한 사용자 지정 템플릿을 알아봅니다.
author: thraka
ms.date: 06/14/2019
ms.openlocfilehash: 8e1ac4ca21a8a90ad0f7c9bd3dd11281eb4a6e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "73420872"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="9335a-103">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="9335a-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="9335a-104">[.NET Core SDK](https://dotnet.microsoft.com/download)에는 이미 설치되어 바로 사용할 수 있는 많은 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="9335a-105">[`dotnet new` 명령](dotnet-new.md)은 템플릿을 사용하는 방법일 뿐만 아니라 템플릿을 설치 및 제거하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="9335a-106">.NET Core 2.0부터 앱, 서비스, 도구 또는 클래스 라이브러리와 같은 모든 형식의 프로젝트에 대한 사용자 지정 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="9335a-107">구성 파일과 같이 하나 이상의 종속 파일을 출력하는 템플릿도 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="9335a-108">NuGet *.nupkg* 파일을 직접 참조하거나 템플릿이 포함된 파일 시스템 디렉터리를 지정하여 NuGet 피드의 NuGet 패키지에서 사용자 지정 템플릿을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="9335a-109">템플릿 엔진은 값을 바꾸고, 파일을 포함 및 제외하고, 템플릿 사용 시 사용자 지정 처리 작업을 실행할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="9335a-110">템플릿 엔진은 오픈 소스이며 온라인 코드 리포지토리는 GitHub의 [dotnet/templating](https://github.com/dotnet/templating/)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="9335a-111">템플릿 샘플을 보려면 [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) 리포지토리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-111">Visit the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) repo for samples of templates.</span></span> <span data-ttu-id="9335a-112">타사 템플릿을 포함한 추가 템플릿은 GitHub의 [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-112">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="9335a-113">사용자 지정 템플릿을 만들고 사용하는 방법에 대한 자세한 내용은 [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법) 및 [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-113">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="9335a-114">연습을 수행하고 템플릿을 만들려면 [dotnet new에 대한 사용자 지정 템플릿 만들기](../tutorials/cli-templates-create-item-template.md) 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-114">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="9335a-115">.NET 기본 템플릿</span><span class="sxs-lookup"><span data-stu-id="9335a-115">.NET default templates</span></span>

<span data-ttu-id="9335a-116">[.NET Core SDK](https://dotnet.microsoft.com/download)를 설치할 때 콘솔 앱, 클래스 라이브러리, 단위 테스트 프로젝트, ASP.NET Core 앱([Angular](https://angular.io/) 및 [React](https://facebook.github.io/react/) 프로젝트 포함) 및 구성 파일을 비롯한 프로젝트 및 파일을 만들 수 있는 12개 이상의 기본 제공 템플릿이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-116">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="9335a-117">기본 제공 템플릿을 나열하려면 `dotnet new` 옵션과 함께 `-l|--list` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-117">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="9335a-118">Configuration</span><span class="sxs-lookup"><span data-stu-id="9335a-118">Configuration</span></span>

<span data-ttu-id="9335a-119">템플릿은 다음 파트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-119">A template is composed of the following parts:</span></span>

- <span data-ttu-id="9335a-120">소스 파일 및 폴더</span><span class="sxs-lookup"><span data-stu-id="9335a-120">Source files and folders.</span></span>
- <span data-ttu-id="9335a-121">구성 파일(*template.json*)</span><span class="sxs-lookup"><span data-stu-id="9335a-121">A configuration file (*template.json*).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="9335a-122">소스 파일 및 폴더</span><span class="sxs-lookup"><span data-stu-id="9335a-122">Source files and folders</span></span>

<span data-ttu-id="9335a-123">소스 파일 및 폴더에는 `dotnet new <TEMPLATE>` 명령을 실행할 때 템플릿 엔진에서 사용하려는 파일과 폴더가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-123">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="9335a-124">템플릿 엔진은 프로젝트를 생성하는 데 *실행 가능한 프로젝트*를 소스 코드로 사용하도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-124">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="9335a-125">여기에는 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-125">This has several benefits:</span></span>

- <span data-ttu-id="9335a-126">템플릿 엔진에서는 특수 토큰을 프로젝트의 소스 코드에 삽입할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-126">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="9335a-127">코드 파일은 특수 파일이 아니고 템플릿 엔진 작업을 수행하는 방식으로 수정되지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-127">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="9335a-128">따라서 일반적으로 프로젝트 작업을 할 때 사용하는 도구로 템플릿 콘텐츠를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-128">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="9335a-129">다른 프로젝트를 처리하는 것처럼 템플릿 프로젝트를 빌드, 실행 및 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-129">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="9335a-130">*./.template.config/template.json* 구성 파일을 프로젝트에 추가하면 기존 프로젝트에서 템플릿을 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-130">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="9335a-131">템플릿에 저장되는 파일과 폴더가 공식적인 .NET 프로젝트 형식으로 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-131">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="9335a-132">템플릿 엔진에서 하나의 파일만 출력으로 생성하는 경우에도, 소스 파일 및 폴더는 템플릿을 사용할 때 만들려는 모든 콘텐츠로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-132">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="9335a-133">*template.json* 구성 파일에 제공한 논리 및 설정을 기준으로 템플릿에서 생성된 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-133">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="9335a-134">사용자는 `dotnet new <TEMPLATE>` 명령에 옵션을 전달하여 이러한 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-134">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="9335a-135">사용자 지정 논리의 일반적인 예는 템플릿을 통해 배포되는 코드 파일에 클래스 또는 변수의 이름을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-135">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="9335a-136">template.json</span><span class="sxs-lookup"><span data-stu-id="9335a-136">template.json</span></span>

<span data-ttu-id="9335a-137">*template.json* 파일은 템플릿 루트 디렉터리의 *.template.config* 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-137">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="9335a-138">이 파일은 템플릿 엔진에 구성 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-138">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="9335a-139">기능 템플릿을 충분히 만들 수 있는 최소 구성으로 다음 표에 나와 있는 멤버가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-139">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="9335a-140">멤버</span><span class="sxs-lookup"><span data-stu-id="9335a-140">Member</span></span>            | <span data-ttu-id="9335a-141">형식</span><span class="sxs-lookup"><span data-stu-id="9335a-141">Type</span></span>          | <span data-ttu-id="9335a-142">설명</span><span class="sxs-lookup"><span data-stu-id="9335a-142">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="9335a-143">URI</span><span class="sxs-lookup"><span data-stu-id="9335a-143">URI</span></span>           | <span data-ttu-id="9335a-144">*template.json* 파일에 대한 JSON 스키마.</span><span class="sxs-lookup"><span data-stu-id="9335a-144">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="9335a-145">스키마 지정 시 JSON 스키마가 JSON 편집 기능을 구현하도록 지원하는 편집기.</span><span class="sxs-lookup"><span data-stu-id="9335a-145">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="9335a-146">예를 들어 [Visual Studio Code](https://code.visualstudio.com/)에서는 이 멤버가 IntelliSense를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-146">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="9335a-147">`http://json.schemastore.org/template` 값을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-147">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="9335a-148">string</span><span class="sxs-lookup"><span data-stu-id="9335a-148">string</span></span>        | <span data-ttu-id="9335a-149">템플릿 작성자.</span><span class="sxs-lookup"><span data-stu-id="9335a-149">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="9335a-150">array(string)</span><span class="sxs-lookup"><span data-stu-id="9335a-150">array(string)</span></span> | <span data-ttu-id="9335a-151">사용자가 템플릿 검색 시 템플릿을 찾는 데 사용할 수 있는 0개 이상의 템플릿 특성.</span><span class="sxs-lookup"><span data-stu-id="9335a-151">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="9335a-152">*명령을 사용하여 생성된 템플릿 목록에 템플릿이 나타날 때*태그`dotnet new -l|--list` 열에 분류도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-152">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="9335a-153">string</span><span class="sxs-lookup"><span data-stu-id="9335a-153">string</span></span>        | <span data-ttu-id="9335a-154">이 템플릿의 공유한 이름.</span><span class="sxs-lookup"><span data-stu-id="9335a-154">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="9335a-155">string</span><span class="sxs-lookup"><span data-stu-id="9335a-155">string</span></span>        | <span data-ttu-id="9335a-156">사용자에게 표시되어야 하는 템플릿의 이름.</span><span class="sxs-lookup"><span data-stu-id="9335a-156">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="9335a-157">string</span><span class="sxs-lookup"><span data-stu-id="9335a-157">string</span></span>        | <span data-ttu-id="9335a-158">GUI를 통해 선택하는 것이 아니라 사용자가 템플릿 이름을 지정하는 환경에 적용되는, 템플릿 선택에 사용되는 기본 약식 이름.</span><span class="sxs-lookup"><span data-stu-id="9335a-158">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="9335a-159">예를 들어 명령 프롬프트에서 템플릿과 CLI 명령을 함께 사용할 경우 짧은 이름이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-159">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

<span data-ttu-id="9335a-160">*template.json* 파일에 대한 전체 스키마는 [JSON Schema Store](http://json.schemastore.org/template)(JSON 스키마 저장소)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-160">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="9335a-161">*template.json* 파일에 대한 자세한 내용은 [dotnet 템플릿 wiki](https://github.com/dotnet/templating/wiki)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-161">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="9335a-162">예제</span><span class="sxs-lookup"><span data-stu-id="9335a-162">Example</span></span>

<span data-ttu-id="9335a-163">예를 들어 아래에는 *console.cs* 및 *readme.txt*라는 두 개의 콘텐츠 파일이 포함된 템플릿 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-163">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt*.</span></span> <span data-ttu-id="9335a-164">또한 *template.json* 파일이 포함된 *.template.config*라는 필수 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-164">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="9335a-165">*template.json* 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-165">The *template.json* file looks like the following:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

<span data-ttu-id="9335a-166">*mytemplate* 폴더는 설치 가능한 템플릿 팩입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-166">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="9335a-167">팩이 설치되고 나면, `shortName` 명령에 `dotnet new`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-167">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="9335a-168">예를 들어 `dotnet new adatumconsole`은 `console.cs` 및 `readme.txt` 파일을 현재 폴더에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-168">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="9335a-169">템플릿을 NuGet 패키지(nupkg 파일)로 압축</span><span class="sxs-lookup"><span data-stu-id="9335a-169">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="9335a-170">사용자 지정 템플릿은 [dotnet pack](dotnet-pack.md) 명령과 *.csproj* 파일을 사용하여 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-170">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="9335a-171">또는 [nuget pack](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) 명령 및 [.nuspec](https://docs.microsoft.com/nuget/tools/cli-ref-pack) 파일과 함께 *NuGet*을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-171">Alternatively, [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="9335a-172">그러나 NuGet을 사용하려면 Windows에서는 .NET Framework가 필요하고, Linux 및 MacOS에서는 [Mono](https://www.mono-project.com/)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-172">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and MacOS.</span></span>

<span data-ttu-id="9335a-173">*.csproj* 파일은 기존의 코드 프로젝트 *.csproj* 파일과 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-173">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="9335a-174">다음 설정에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-174">Note the following settings:</span></span>

01. <span data-ttu-id="9335a-175">`<PackageType>` 설정이 추가되고 `Template`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-175">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="9335a-176">`<PackageVersion>` 설정이 추가되고 유효한 [NuGet 버전 번호](/nuget/reference/package-versioning)로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-176">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="9335a-177">`<PackageId>` 설정이 추가되고 고유 식별자로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-177">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="9335a-178">이 식별자는 템플릿 팩을 제거하는 데 사용되며, NuGet 피드에서 템플릿 팩을 등록하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-178">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="9335a-179">`<Title>`, `<Authors>`, `<Description>`, `<PackageTags>` 등의 일반 메타데이터 설정을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-179">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="9335a-180">템플릿 프로세스에서 생성된 이진 파일을 사용하지 않더라도 `<TargetFramework>` 설정을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-180">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="9335a-181">아래 예제에서는 `netstandard2.0`으로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-181">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="9335a-182">*.nupkg* NuGet 패키지 양식의 템플릿 팩은 모든 템플릿이 패키지 내의 *content* 폴더에 저장되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-182">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="9335a-183">생성된 *.nupkg*을 템플릿 팩으로 설치할 수 있도록 *.csproj* 파일에 추가해야 하는 몇 가지 설정이 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-183">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="9335a-184">프로젝트에서 NuGet 패키지의 `<IncludeContentInPack>`content`true`로 설정하는 모든 파일이 포함되도록 **설정을**로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-184">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="9335a-185">컴파일러가 NuGet 패키지에서 생성하는 모든 이진 파일이 제외되도록 `<IncludeBuildOutput>` 설정을 `false`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-185">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="9335a-186">`<ContentTargetFolders>` 설정을 `content`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-186">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="9335a-187">이렇게 하면 **content**로 설정된 파일이 NuGet 패키지의 *content* 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-187">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="9335a-188">NuGet 패키지의 이 폴더는 dotnet 템플릿 시스템에서 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-188">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="9335a-189">템플릿 프로젝트에서 코드 파일이 컴파일되지 않도록 모두 제외하는 간편한 방법은 프로젝트 파일의 `<Compile Remove="**\*" />` 요소에 `<ItemGroup>` 항목을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-189">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="9335a-190">템플릿 팩을 구성하는 간편한 방법은 모든 템플릿을 개별 폴더에 넣은 다음, *.csproj* 파일과 동일한 디렉터리에 있는 *templates* 폴더에 각 템플릿 폴더를 넣는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-190">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="9335a-191">이렇게 하면 단일 프로젝트 항목을 사용하여 *templates*에 있는 모든 파일과 폴더를 **content**로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-191">This way, you can use a single project item to include all files and folders in the *templates* as **content**.</span></span> <span data-ttu-id="9335a-192">`<ItemGroup>` 요소 내부에 `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-192">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="9335a-193">다음은 위의 모든 지침을 따르는 예제 *.csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-193">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="9335a-194">*templates* 자식 폴더를 *content* 패키지 폴더에 압축하고, 코드 파일이 컴파일되지 않도록 모두 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-194">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="9335a-195">아래 예제에서는 *.csproj*를 사용하여 템플릿 팩을 만드는 파일 및 폴더 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-195">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="9335a-196">*MyDotnetTemplates.csproj* 파일과 *templates* 폴더는 모두 *project_folder* 디렉터리의 루트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-196">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder*.</span></span> <span data-ttu-id="9335a-197">*templates* 폴더에는 *mytemplate1*과 *mytemplate2*라는 두 개의 템플릿이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-197">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2*.</span></span> <span data-ttu-id="9335a-198">각 템플릿에 *template.json* 구성 파일이 포함된 *. template.config* 폴더와 콘텐츠 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-198">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a><span data-ttu-id="9335a-199">템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="9335a-199">Installing a template</span></span>

<span data-ttu-id="9335a-200">[dotnet new -i|--install](dotnet-new.md) 명령을 사용하여 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-200">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="9335a-201">nuget.org에 저장된 NuGet 패키지에서 템플릿을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="9335a-201">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="9335a-202">NuGet 패키지 식별자를 사용하여 템플릿 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-202">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="9335a-203">로컬 nupkg 파일에서 템플릿을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="9335a-203">To install a template from a local nupkg file</span></span>

<span data-ttu-id="9335a-204">*.nupkg* NuGet 패키지 파일의 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-204">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="9335a-205">파일 시스템 디렉터리에서 템플릿을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="9335a-205">To install a template from a file system directory</span></span>

<span data-ttu-id="9335a-206">위 예제의 *mytemplate1*과 같은 템플릿 폴더에서 템플릿을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-206">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="9335a-207">*.template.config* 폴더의 폴더 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-207">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="9335a-208">템플릿 디렉터리의 경로가 절대 경로여야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-208">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="9335a-209">그러나 설치된 템플릿을 폴더에서 제거하려면 절대 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-209">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="9335a-210">설치된 템플릿 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="9335a-210">Get a list of installed templates</span></span>

<span data-ttu-id="9335a-211">다른 매개 변수가 없는 제거 명령은 설치된 템플릿을 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-211">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="9335a-212">해당 명령은 다음과 비슷한 출력을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-212">That command returns something similar to the following output:</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

<span data-ttu-id="9335a-213">`Currently installed items:` 뒤에 있는 첫 번째 수준의 항목은 템플릿 제거에 사용되는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-213">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="9335a-214">위 예제에서는 `Microsoft.DotNet.Common.ItemTemplates` 및 `Microsoft.DotNet.Common.ProjectTemplates.3.0`이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-214">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="9335a-215">파일 시스템 경로를 사용하여 템플릿을 설치한 경우, 이 식별자는 *.template.config* 폴더의 폴더 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-215">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="9335a-216">템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="9335a-216">Uninstalling a template</span></span>

<span data-ttu-id="9335a-217">[dotnet new -u|--uninstall](dotnet-new.md) 명령을 사용하여 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-217">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="9335a-218">NuGet 피드 또는 *.nupkg* 파일을 통해 직접 패키지를 설치한 경우, 식별자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-218">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="9335a-219">*.template.config* 폴더의 경로를 지정하여 패키지를 설치한 경우, **절대** 경로를 사용하여 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-219">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="9335a-220">`dotnet new -u` 명령을 통해 제공된 출력에서 템플릿의 절대 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-220">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="9335a-221">자세한 내용은 위의 [설치된 템플릿 목록 가져오기](#get-a-list-of-installed-templates) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9335a-221">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="9335a-222">사용자 지정 템플릿을 사용하여 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9335a-222">Create a project using a custom template</span></span>

<span data-ttu-id="9335a-223">템플릿이 설치된 후 다른 미리 설치된 템플릿을 사용하는 것처럼 `dotnet new <TEMPLATE>` 명령을 실행하여 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-223">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="9335a-224">템플릿 설정에서 구성한 템플릿 관련 옵션을 포함하여 [ 명령에 대한 ](dotnet-new.md#options)옵션`dotnet new`을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-224">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="9335a-225">템플릿의 짧은 이름을 직접 명령에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9335a-225">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="9335a-226">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9335a-226">See also</span></span>

- [<span data-ttu-id="9335a-227">dotnet new에 대한 사용자 지정 템플릿(자습서)</span><span class="sxs-lookup"><span data-stu-id="9335a-227">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/cli-templates-create-item-template.md)
- <span data-ttu-id="9335a-228">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)</span><span class="sxs-lookup"><span data-stu-id="9335a-228">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)</span></span>
- <span data-ttu-id="9335a-229">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="9335a-229">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
- <span data-ttu-id="9335a-230">[How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법)</span><span class="sxs-lookup"><span data-stu-id="9335a-230">[How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)</span></span>
- [<span data-ttu-id="9335a-231">*template.json* JSON 스키마 저장소에 대 한 스키마</span><span class="sxs-lookup"><span data-stu-id="9335a-231">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
