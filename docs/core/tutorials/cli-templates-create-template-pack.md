---
title: dotnet new에 대한 템플릿 팩 만들기
description: dotnet new 명령에 대한 템플릿 팩을 빌드하는 csproj 파일을 만드는 방법을 알아봅니다.
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 3a72f68f5634c9ee5b137baf12a279130861e61a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787832"
---
# <a name="tutorial-create-a-template-pack"></a><span data-ttu-id="b76e5-103">자습서: 템플릿 팩 만들기</span><span class="sxs-lookup"><span data-stu-id="b76e5-103">Tutorial: Create a template pack</span></span>

<span data-ttu-id="b76e5-104">.NET Core를 사용하여 프로젝트, 파일, 리소스를 생성하는 템플릿을 만들고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="b76e5-105">이 자습서는 `dotnet new` 명령에 사용할 템플릿을 만들고, 설치하고, 제거하는 방법을 알려주는 시리즈의 3부입니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-105">This tutorial is part three of a series that teaches you how to create, install, and uninstall templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="b76e5-106">시리즈의 3부에서는 다음 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="b76e5-107">\*.csproj 프로젝트를 만들어 템플릿 팩 빌드</span><span class="sxs-lookup"><span data-stu-id="b76e5-107">Create a \*.csproj project to build a template pack</span></span>
> * <span data-ttu-id="b76e5-108">압축을 위해 프로젝트 파일 구성</span><span class="sxs-lookup"><span data-stu-id="b76e5-108">Configure the project file for packing</span></span>
> * <span data-ttu-id="b76e5-109">NuGet 패키지 파일에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="b76e5-109">Install a template from a NuGet package file</span></span>
> * <span data-ttu-id="b76e5-110">패키지 ID로 템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="b76e5-110">Uninstall a template by package ID</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b76e5-111">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b76e5-111">Prerequisites</span></span>

* <span data-ttu-id="b76e5-112">이 자습서 시리즈의 [1부](cli-templates-create-item-template.md) 및 [2부](cli-templates-create-project-template.md)를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-112">Complete [part 1](cli-templates-create-item-template.md) and [part 2](cli-templates-create-project-template.md) of this tutorial series.</span></span>

  <span data-ttu-id="b76e5-113">이 자습서에서는 이 자습서의 처음 두 부분에서 만든 두 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-113">This tutorial uses the two templates created in the first two parts of this tutorial.</span></span> <span data-ttu-id="b76e5-114">_working\templates\\_ 폴더에 템플릿을 폴더로 복사하여 다른 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-114">You can use a different template as long as you copy the template, as a folder, into the _working\templates\\_ folder.</span></span>

* <span data-ttu-id="b76e5-115">터미널을 열고 _working\\_ 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-115">Open a terminal and navigate to the _working\\_ folder.</span></span>

## <a name="create-a-template-pack-project"></a><span data-ttu-id="b76e5-116">템플릿 팩 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b76e5-116">Create a template pack project</span></span>

<span data-ttu-id="b76e5-117">템플릿 팩은 파일로 패키지된 하나 이상의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-117">A template pack is one or more templates packaged into a file.</span></span> <span data-ttu-id="b76e5-118">팩을 설치하거나 제거하면 각각 팩에 포함된 모든 템플릿이 추가되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-118">When you install or uninstall a pack, all templates contained in the pack are added or removed, respectively.</span></span> <span data-ttu-id="b76e5-119">이 자습서 시리즈의 이전 부분에서는 개별 템플릿 작업만 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-119">The previous parts of this tutorial series only worked with individual templates.</span></span> <span data-ttu-id="b76e5-120">압축되지 않은 템플릿을 공유하려면 템플릿 폴더를 복사하고 해당 폴더를 통해 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-120">To share a non-packed template, you have to copy the template folder and install via that folder.</span></span> <span data-ttu-id="b76e5-121">템플릿 팩은 둘 이상의 템플릿을 포함할 수 있고 단일 파일이므로 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-121">Because a template pack can have more than one template in it, and is a single file, sharing is easier.</span></span>

<span data-ttu-id="b76e5-122">템플릿 팩은 NuGet 패키지( _.nupkg_) 파일로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-122">Template packs are represented by a NuGet package (_.nupkg_) file.</span></span> <span data-ttu-id="b76e5-123">NuGet 패키지와 마찬가지로 템플릿 팩을 NuGet 피드에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-123">And, like any NuGet package, you can upload the template pack to a NuGet feed.</span></span> <span data-ttu-id="b76e5-124">`dotnet new -i` 명령은 NuGet 패키지 피드에서 템플릿 팩 설치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-124">The `dotnet new -i` command supports installing template pack from a NuGet package feed.</span></span> <span data-ttu-id="b76e5-125">_.nupkg_ 파일에서 직접 템플릿 팩을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-125">Additionally, you can install a template pack from a _.nupkg_ file directly.</span></span>

<span data-ttu-id="b76e5-126">일반적으로 C# 프로젝트 파일을 사용하여 코드를 컴파일하고 이진을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-126">Normally you use a C# project file to compile code and produce a binary.</span></span> <span data-ttu-id="b76e5-127">프로젝트를 사용하여 템플릿 팩을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-127">However, the project can also be used to generate a template pack.</span></span> <span data-ttu-id="b76e5-128">_.csproj_의 설정을 변경하여 코드를 컴파일하지 않도록 차단하고 템플릿의 모든 자산을 리소스로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-128">By changing the settings of the _.csproj_, you can prevent it from compiling any code and instead include all the assets of your templates as resources.</span></span> <span data-ttu-id="b76e5-129">이 프로젝트를 빌드하면 템플릿 팩 NuGet 패키지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-129">When this project is built, it produces a template pack NuGet package.</span></span>

<span data-ttu-id="b76e5-130">만든 팩에는 이전에 만든 [항목 템플릿](cli-templates-create-item-template.md) 및 [패키지 템플릿](cli-templates-create-project-template.md)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-130">The pack you'll create will include the [item template](cli-templates-create-item-template.md) and [package template](cli-templates-create-project-template.md) previously created.</span></span> <span data-ttu-id="b76e5-131">두 템플릿을 _working\templates\\_ 폴더로 그룹화했으므로 _.csproj_ 파일에 대해 _working_ 폴더를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-131">Because we grouped the two templates into the _working\templates\\_ folder, we can use the _working_ folder for the _.csproj_ file.</span></span>

<span data-ttu-id="b76e5-132">터미널에서 _working_ 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-132">In your terminal, navigate to the _working_ folder.</span></span> <span data-ttu-id="b76e5-133">새 프로젝트를 만들고 이름을 `templatepack`으로 설정하고 출력 폴더를 현재 폴더로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-133">Create a new project and set the name to `templatepack` and the output folder to the current folder.</span></span>

```dotnetcli
dotnet new console -n templatepack -o .
```

<span data-ttu-id="b76e5-134">`-n` 매개 변수는 _.csproj_ 파일 이름을 _templatepack.csproj_로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-134">The `-n` parameter sets the _.csproj_ filename to _templatepack.csproj_.</span></span> <span data-ttu-id="b76e5-135">`-o` 매개 변수는 현재 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-135">The `-o` parameter creates the files in the current directory.</span></span> <span data-ttu-id="b76e5-136">다음 출력과 유사한 결과가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-136">You should see a result similar to the following output.</span></span>

```console
C:\working> dotnet new console -n templatepack -o .
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

<span data-ttu-id="b76e5-137">이제 원하는 편집기에서 _templatepack.csproj_ 파일을 열고 콘텐츠를 다음 XML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-137">Next, open the _templatepack.csproj_ file in your favorite editor and replace the content with the following XML:</span></span>

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

<span data-ttu-id="b76e5-138">위 XML의 `<PropertyGroup>` 설정은 세 개의 그룹으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-138">The `<PropertyGroup>` settings in the XML above is broken into three groups.</span></span> <span data-ttu-id="b76e5-139">첫 번째 그룹은 NuGet 패키지에 필요한 속성을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-139">The first group deals with properties required for a NuGet package.</span></span> <span data-ttu-id="b76e5-140">세 `<Package` 설정은 NuGet 피드에서 패키지를 식별하는 NuGet 패키지 속성과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-140">The three `<Package` settings have to do with the NuGet package properties to identify your package on a NuGet feed.</span></span> <span data-ttu-id="b76e5-141">특히, `<PackageId>` 값은 디렉터리 경로 대신 단일 이름으로 템플릿 팩을 제거하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-141">Specifically the `<PackageId>` value is used to uninstall the template pack with a single name instead of a directory path.</span></span> <span data-ttu-id="b76e5-142">이 값을 사용하여 NuGet 피드에서 템플릿 팩을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-142">It can also be used to install the template pack from a NuGet feed.</span></span> <span data-ttu-id="b76e5-143">`<Title>` 및 `<PackageTags>`와 같은 나머지 설정은 NuGet 피드에 표시되는 메타데이터와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-143">The remaining settings such as `<Title>` and `<PackageTags>` have to do with metadata displayed on the NuGet feed.</span></span> <span data-ttu-id="b76e5-144">NuGet 설정에 대한 자세한 내용은 [NuGet 및 MSBuild 속성](/nuget/reference/msbuild-targets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b76e5-144">For more information about NuGet settings, see [NuGet and MSBuild properties](/nuget/reference/msbuild-targets).</span></span>

<span data-ttu-id="b76e5-145">pack 명령을 실행하여 프로젝트를 컴파일하고 압축할 때 MSBuild가 제대로 실행되도록 `<TargetFramework>` 설정을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-145">The `<TargetFramework>` setting must be set so that MSBuild will run properly when you run the pack command to compile and pack the project.</span></span>

<span data-ttu-id="b76e5-146">마지막 세 설정은 템플릿을 만들 때 NuGet 팩의 적절한 폴더에 포함되도록 프로젝트를 올바르게 구성하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-146">The last three settings have to do with configuring the project correctly to include the templates in the appropriate folder in the NuGet pack when it's created.</span></span>

<span data-ttu-id="b76e5-147">`<ItemGroup>`은 두 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-147">The `<ItemGroup>` contains two settings.</span></span> <span data-ttu-id="b76e5-148">첫째, `<Content>` 설정은 _templates_ 폴더의 모든 항목을 콘텐츠로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-148">First, the `<Content>` setting includes everything in the _templates_ folder as content.</span></span> <span data-ttu-id="b76e5-149">또한 _bin_ 폴더 또는 _obj_ 폴더를 제외하여 컴파일된 코드(템플릿을 테스트하여 컴파일한 경우)를 포함하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-149">It's also set to exclude any _bin_ folder or _obj_ folder to prevent any compiled code (if you tested and compiled your templates) from being included.</span></span> <span data-ttu-id="b76e5-150">둘째, `<Compile>` 설정은 위치에 상관없이 모든 코드 파일을 컴파일에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-150">Second, the `<Compile>` setting excludes all code files from compiling no matter where they're located.</span></span> <span data-ttu-id="b76e5-151">이 설정은 템플릿 팩을 만드는 데 사용 중인 프로젝트가 _templates_ 폴더 계층에서 코드를 컴파일하려고 시도하지 못하도록 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-151">This setting prevents the project being used to create a template pack from trying to compile the code in the _templates_ folder hierarchy.</span></span>

## <a name="build-and-install"></a><span data-ttu-id="b76e5-152">빌드 및 설치</span><span class="sxs-lookup"><span data-stu-id="b76e5-152">Build and install</span></span>

<span data-ttu-id="b76e5-153">이 파일을 저장한 다음 pack 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-153">Save this file and then run the pack command</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="b76e5-154">이 명령은 프로젝트를 빌드하고 _working\bin\Debug_ 폴더에 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-154">This command will build your project and create a NuGet package in This should be the _working\bin\Debug_ folder.</span></span>

```console
C:\working> dotnet pack
Microsoft (R) Build Engine version 16.2.0-preview-19278-01+d635043bd for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

<span data-ttu-id="b76e5-155">그런 다음 `dotnet new -i PATH_TO_NUPKG_FILE` 명령을 사용하여 템플릿 팩 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-155">Next, install the template pack file with the `dotnet new -i PATH_TO_NUPKG_FILE` command.</span></span>

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
```

<span data-ttu-id="b76e5-156">NuGet 패키지를 NuGet 피드에 업로드한 경우 `dotnet new -i PACKAGEID` 명령을 사용할 수 있습니다. 여기서 `PACKAGEID`는 _.csproj_ 파일의 `<PackageId>` 설정과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-156">If you uploaded the NuGet package to a NuGet feed, you can use the `dotnet new -i PACKAGEID` command where `PACKAGEID` is the same as the `<PackageId>` setting from the _.csproj_ file.</span></span> <span data-ttu-id="b76e5-157">이 패키지 ID는 NuGet 패키지 식별자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-157">This package ID is the same as the NuGet package identifier.</span></span>

## <a name="uninstall-the-template-pack"></a><span data-ttu-id="b76e5-158">템플릿 팩 제거</span><span class="sxs-lookup"><span data-stu-id="b76e5-158">Uninstall the template pack</span></span>

<span data-ttu-id="b76e5-159">_.nupkg_ 파일을 직접 사용하거나 NuGet 피드를 사용하는 등 템플릿 팩을 설치한 방법에 상관없이 템플릿 팩을 제거하는 방법은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-159">No matter how you installed the template pack, either with the _.nupkg_ file directly or by NuGet feed, removing a template pack is the same.</span></span> <span data-ttu-id="b76e5-160">제거하려는 템플릿의 `<PackageId>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-160">Use the `<PackageId>` of the template you want to uninstall.</span></span> <span data-ttu-id="b76e5-161">`dotnet new -u` 명령을 실행하여 설치된 템플릿 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-161">You can get a list of templates that are installed by running the `dotnet new -u` command.</span></span>

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
  AdatumCorporation.Utility.Templates
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="b76e5-162">`dotnet new -u AdatumCorporation.Utility.Templates`을 실행하여 템플릿을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-162">Run `dotnet new -u AdatumCorporation.Utility.Templates` to uninstall the template.</span></span> <span data-ttu-id="b76e5-163">`dotnet new` 명령은 이전에 설치한 템플릿을 생략해야 한다는 도움말 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-163">The `dotnet new` command will output help information that should omit the templates you previously installed.</span></span>

<span data-ttu-id="b76e5-164">지금까지</span><span class="sxs-lookup"><span data-stu-id="b76e5-164">Congratulations!</span></span> <span data-ttu-id="b76e5-165">템플릿 팩을 설치했다가 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="b76e5-165">you've installed and uninstalled a template pack.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b76e5-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b76e5-166">Next steps</span></span>

<span data-ttu-id="b76e5-167">대부분의 내용은 이미 살펴보았지만 템플릿에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](../tools/custom-templates.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b76e5-167">To learn more about templates, most of which you've already learned, see the [Custom templates for dotnet new](../tools/custom-templates.md) article.</span></span>

* <span data-ttu-id="b76e5-168">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)</span><span class="sxs-lookup"><span data-stu-id="b76e5-168">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)</span></span>
* <span data-ttu-id="b76e5-169">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="b76e5-169">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>
* [<span data-ttu-id="b76e5-170">*template.json* JSON 스키마 저장소에 대 한 스키마</span><span class="sxs-lookup"><span data-stu-id="b76e5-170">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
