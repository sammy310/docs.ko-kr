---
title: dotnet new에 대한 프로젝트 템플릿 만들기
description: dotnet new 명령에 대한 프로젝트 템플릿을 만드는 방법을 알아봅니다.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 1f4e73287fca650b20ed5617c8dfd80e0bd8363c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318282"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="634b0-103">자습서: 프로젝트 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="634b0-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="634b0-104">.NET Core를 사용하여 프로젝트, 파일, 리소스를 생성하는 템플릿을 만들고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="634b0-105">이 자습서는 `dotnet new` 명령에 사용할 템플릿을 만들고, 설치하고, 제거하는 방법을 알려주는 시리즈의 2부입니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="634b0-106">시리즈의 2부에서는 다음 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="634b0-107">프로젝트 템플릿의 리소스 만들기</span><span class="sxs-lookup"><span data-stu-id="634b0-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="634b0-108">템플릿 구성 폴더 및 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="634b0-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="634b0-109">파일 경로에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="634b0-109">Install a template from a file path</span></span>
> * <span data-ttu-id="634b0-110">항목 템플릿 테스트</span><span class="sxs-lookup"><span data-stu-id="634b0-110">Test an item template</span></span>
> * <span data-ttu-id="634b0-111">항목 템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="634b0-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="634b0-112">전제 조건</span><span class="sxs-lookup"><span data-stu-id="634b0-112">Prerequisites</span></span>

* <span data-ttu-id="634b0-113">이 자습서 시리즈의 [1부](cli-templates-create-item-template.md)를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="634b0-114">터미널을 열고 _working\templates\\_ 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-114">Open a terminal and navigate to the _working\templates\\_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="634b0-115">프로젝트 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="634b0-115">Create a project template</span></span>

<span data-ttu-id="634b0-116">프로젝트 템플릿은 사용자가 코드의 작업 집합을 쉽게 시작할 수 있도록 해주는 즉시 실행 가능한 프로젝트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="634b0-117">.NET Core에는 콘솔 애플리케이션 또는 클래스 라이브러리와 같은 몇 가지 프로젝트 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-117">.NET Core includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="634b0-118">이 예제에서는 C# 8.0을 사용하고 `async main` 진입점을 생성하는 새 콘솔 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-118">In this example, you'll create a new console project that enables C# 8.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="634b0-119">터미널에서 _working\templates\\_폴더로 이동하고_consoleasync_라는 새 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-119">In your terminal, navigate to the _working\templates\\_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="634b0-120">하위 폴더를 입력하고 `dotnet new console`을 실행하여 표준 콘솔 애플리케이션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="634b0-121">이 템플릿에서 생성된 파일을 편집하여 새 템플릿을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="634b0-122">Program.cs 수정</span><span class="sxs-lookup"><span data-stu-id="634b0-122">Modify Program.cs</span></span>

<span data-ttu-id="634b0-123">_program.cs_ 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="634b0-124">콘솔 프로젝트에서는 비동기 진입점을 사용하지 않으므로 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="634b0-125">코드를 다음과 같이 변경하고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-125">Change your code to the following and save the file:</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="634b0-126">consoleasync.csproj 수정</span><span class="sxs-lookup"><span data-stu-id="634b0-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="634b0-127">프로젝트에서 사용하는 C# 언어 버전을 8.0으로 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-127">Let's update the C# language version the project uses to version 8.0.</span></span> <span data-ttu-id="634b0-128">_consoleasync.csproj_ 파일을 편집하고 `<LangVersion>` 설정을 `<PropertyGroup>` 노드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="634b0-129">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="634b0-129">Build the project</span></span>

<span data-ttu-id="634b0-130">프로젝트 템플릿을 완료하기 전에 테스트하여 올바르게 컴파일되고 실행되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span> <span data-ttu-id="634b0-131">터미널에서 `dotnet run` 명령을 실행하면 다음 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-131">In your terminal, run the `dotnet run` command and you should see the following output:</span></span>

```console
C:\working\templates\consoleasync> dotnet run
Hello World with C# 8.0!
```

<span data-ttu-id="634b0-132">`dotnet run`을 사용하여 만든 _obj_ 및 _bin_ 폴더를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-132">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="634b0-133">이러한 파일을 삭제하면 템플릿에는 템플릿 관련 파일만 포함되고 빌드 작업의 결과로 생성되는 파일은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-133">Deleting these files ensures your template only includes the files related to your template and not any files that result of a build action.</span></span>

<span data-ttu-id="634b0-134">템플릿의 콘텐츠를 만들었으므로 이제 템플릿의 루트 폴더에 템플릿 구성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-134">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="634b0-135">템플릿 구성 만들기</span><span class="sxs-lookup"><span data-stu-id="634b0-135">Create the template config</span></span>

<span data-ttu-id="634b0-136">템플릿은 .NET Core의 템플릿 루트에 있는 특수 폴더 및 구성 파일에서 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-136">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="634b0-137">이 자습서에서 템플릿 폴더는 _working\templates\consoleasync\\_ 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-137">In this tutorial, your template folder is located at _working\templates\consoleasync\\_.</span></span>

<span data-ttu-id="634b0-138">템플릿을 만들 때 템플릿 폴더의 모든 파일과 폴더는 특수 구성 폴더를 제외하고 템플릿의 일부로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-138">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="634b0-139">이 구성 폴더는 _.template.config_입니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-139">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="634b0-140">먼저 _.template.config_라는 새 하위 폴더를 만들고 폴더로 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-140">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="634b0-141">그런 다음 _template.json_이라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-141">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="634b0-142">폴더 구조는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-142">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="634b0-143">원하는 텍스트 편집기에서 _template.json_을 열고 다음 json 코드를 붙여넣은 다음 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-143">Open the _template.json_ with your favorite text editor and paste in the following json code and save it:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="634b0-144">이 구성 파일에는 템플릿에 대한 모든 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-144">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="634b0-145">기본 설정(예: `name` 및 `shortName`)을 확인할 수 있지만 `project`로 설정된 `tags/type` 값도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-145">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="634b0-146">이 값에 따라, 만든 템플릿이 프로젝트 템플릿으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-146">This designates your template as a project template.</span></span> <span data-ttu-id="634b0-147">만드는 템플릿 형식에 대한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-147">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="634b0-148">`item` 및 `project` 값은 사용자가 검색 중인 템플릿 형식을 쉽게 필터링할 수 있도록 .NET Core에서 권장하는 일반적인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-148">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="634b0-149">`classifications` 항목은 `dotnet new`를 실행할 때 표시되고 템플릿 목록을 가져오는 **태그** 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-149">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="634b0-150">사용자는 분류 태그를 기준으로 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-150">Users can also search based on classification tags.</span></span> <span data-ttu-id="634b0-151">.json 파일의 `tags` 속성을 `classifications` 태그 목록과 혼동하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="634b0-151">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="634b0-152">불행히도 두 항목은 이름이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-152">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="634b0-153">*template.json* 파일에 대한 전체 스키마는 [JSON Schema Store](http://json.schemastore.org/template)(JSON 스키마 저장소)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-153">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="634b0-154">*template.json* 파일에 대한 자세한 내용은 [dotnet 템플릿 wiki](https://github.com/dotnet/templating/wiki)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="634b0-154">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="634b0-155">유효한 _.template.config/template.json_ 파일이 있으므로 이제 템플릿을 설치할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-155">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="634b0-156">템플릿을 설치하기 전에 _bin_ 또는 _obj_ 폴더와 같이 템플릿에 포함하지 않을 추가 파일 폴더 및 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-156">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="634b0-157">터미널에서 _consoleasync_ 폴더로 이동하고 `dotnet new -i .\`를 실행하여 현재 폴더에 있는 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-157">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="634b0-158">Linux 또는 MacOS 운영 체제를 사용하는 경우 슬래시를 사용합니다(`dotnet new -i ./`).</span><span class="sxs-lookup"><span data-stu-id="634b0-158">If you're using a Linux or MacOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="634b0-159">이 명령은 사용자 템플릿을 포함하여 설치된 템플릿 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-159">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\consoleasync> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a><span data-ttu-id="634b0-160">프로젝트 템플릿 테스트</span><span class="sxs-lookup"><span data-stu-id="634b0-160">Test the project template</span></span>

<span data-ttu-id="634b0-161">항목 템플릿을 설치했으므로 이제 템플릿을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-161">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="634b0-162">_test_ 폴더로 이동하고 `dotnet new consoleasync`을 사용하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-162">Navigate to the _test_ folder and create a new console application with `dotnet new consoleasync`.</span></span> <span data-ttu-id="634b0-163">그러면 `dotnet run` 명령으로 쉽게 테스트할 수 있는 작업 프로젝트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-163">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```console
C:\test> dotnet new consoleasync
The template "Example templates: async project" was created successfully.
```

```console
C:\test> dotnet run
Hello World with C# 8.0!
```

<span data-ttu-id="634b0-164">지금까지</span><span class="sxs-lookup"><span data-stu-id="634b0-164">Congratulations!</span></span> <span data-ttu-id="634b0-165">.NET Core를 사용하여 프로젝트 템플릿을 만들고 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-165">You created and deployed a project template with .NET Core.</span></span> <span data-ttu-id="634b0-166">이 자습서 시리즈의 다음 부분에 대비하여, 여기서 만든 템플릿을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-166">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="634b0-167">또한 _test_ 폴더에서 모든 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-167">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="634b0-168">그러면 이 자습서의 다음 주요 섹션을 위해 정리된 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-168">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="634b0-169">템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="634b0-169">Uninstall the template</span></span>

<span data-ttu-id="634b0-170">파일 경로를 사용하여 템플릿을 설치했으므로 **절대** 파일 경로를 사용하여 템플릿을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-170">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="634b0-171">`dotnet new -u` 명령을 실행하여 설치된 템플릿 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-171">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="634b0-172">사용자 템플릿은 마지막에 나열되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-172">Your template should be listed last.</span></span> <span data-ttu-id="634b0-173">`dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` 명령을 사용하여 템플릿을 제거하려면 나열된 경로를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-173">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```console
C:\working> dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

```console
C:\working> dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="634b0-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="634b0-174">Next steps</span></span>

<span data-ttu-id="634b0-175">이 자습서에서는 프로젝트 템플릿을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="634b0-175">In this tutorial, you created a project template.</span></span> <span data-ttu-id="634b0-176">항목 템플릿과 프로젝트 템플릿을 모두 사용하기 쉬운 파일로 패키징하는 방법을 알아보려면 이 자습서 시리즈를 계속 진행하세요.</span><span class="sxs-lookup"><span data-stu-id="634b0-176">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="634b0-177">템플릿 팩 만들기</span><span class="sxs-lookup"><span data-stu-id="634b0-177">Create a template pack</span></span>](cli-templates-create-template-pack.md)
