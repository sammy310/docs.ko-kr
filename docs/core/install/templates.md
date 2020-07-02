---
title: SDK 템플릿 설치 및 관리 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core 템플릿을 설치하는 방법을 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324489"
---
# <a name="manage-net-project-and-item-templates"></a><span data-ttu-id="7ff74-103">.NET 프로젝트 및 항목 템플릿 관리</span><span class="sxs-lookup"><span data-stu-id="7ff74-103">Manage .NET project and item templates</span></span>

<span data-ttu-id="7ff74-104">.NET Core는 사용자가 NuGet, NuGet 패키지 파일 또는 파일 시스템 디렉터리에서 템플릿을 설치하거나 제거할 수 있도록 하는 템플릿 시스템을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-104">.NET Core provides a template system that enables users to install or uninstall templates from NuGet, a NuGet package file, or a file system directory.</span></span> <span data-ttu-id="7ff74-105">이 문서에서는 .NET Core SDK CLI를 통해 .NET Core 템플릿을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-105">This article describes how to manage .NET Core templates through the .NET Core SDK CLI.</span></span>

<span data-ttu-id="7ff74-106">템플릿 만들기에 관한 자세한 내용은 [자습서: 템플릿 만들기](../tutorials/cli-templates-create-item-template.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff74-106">For more information about creating templates, see [Tutorial: Create templates](../tutorials/cli-templates-create-item-template.md).</span></span>

## <a name="install-template"></a><span data-ttu-id="7ff74-107">템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="7ff74-107">Install template</span></span>

<span data-ttu-id="7ff74-108">템플릿은 [dotnet new](../tools/dotnet-new.md) SDK 명령에 `-i` 매개 변수를 사용하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-108">Templates are installed through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-i` parameter.</span></span> <span data-ttu-id="7ff74-109">템플릿의 NuGet 패키지 식별자를 제공하거나 템플릿 파일이 포함된 폴더를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-109">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-hosted-package"></a><span data-ttu-id="7ff74-110">NuGet 호스티드 패키지</span><span class="sxs-lookup"><span data-stu-id="7ff74-110">NuGet hosted package</span></span>

<span data-ttu-id="7ff74-111">.NET CLI 템플릿은 광범위한 배포를 위해 [NuGet](https://www.nuget.org/)에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-111">.NET CLI templates are uploaded to [NuGet](https://www.nuget.org/) for wide distribution.</span></span> <span data-ttu-id="7ff74-112">템플릿은 프라이빗 피드에서 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-112">Templates can also be installed from a private feed.</span></span> <span data-ttu-id="7ff74-113">NuGet 피드에 템플릿을 업로드하는 대신 [로컬 NuGet 패키지](#local-nuget-package) 섹션에 설명된 대로 *nupkg* 템플릿 파일을 배포하고 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-113">Instead of uploading a template to a NuGet feed, *nupkg* template files can be distributed and manually installed, as described in the [Local NuGet package](#local-nuget-package) section.</span></span>

<span data-ttu-id="7ff74-114">NuGet 피드를 구성하는 방법에 대한 자세한 내용은 [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff74-114">For more information about configuring NuGet feeds, see [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="7ff74-115">기본 NuGet 피드에서 템플릿 팩을 설치하려면 `dotnet new -i {package-id}` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-115">To install a template pack from the default NuGet feed, use the `dotnet new -i {package-id}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

<span data-ttu-id="7ff74-116">특정 버전으로 기본 NuGet 피드에서 템플릿 팩을 설치하려면 `dotnet new -i {package-id}::{version}` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-116">To install a template pack from the default NuGet feed with a specific version, use the `dotnet new -i {package-id}::{version}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a><span data-ttu-id="7ff74-117">로컬 NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="7ff74-117">Local NuGet package</span></span>

<span data-ttu-id="7ff74-118">템플릿 팩을 만들면 *nupkg* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-118">When a template pack is created, a *nupkg* file is generated.</span></span> <span data-ttu-id="7ff74-119">템플릿을 포함하는 *nupkg* 파일이 있는 경우 `dotnet new -i {path-to-package}` 명령을 사용하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-119">If you have a *nupkg* file containing templates, you can install it with the `dotnet new -i {path-to-package}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a><span data-ttu-id="7ff74-120">폴더</span><span class="sxs-lookup"><span data-stu-id="7ff74-120">Folder</span></span>

<span data-ttu-id="7ff74-121">*nupkg* 파일에서 템플릿을 설치하는 대신 `dotnet new -i {folder-path}` 명령을 사용하여 폴더에서 직접 템플릿을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-121">As an alternative to installing template from a *nupkg* file, you can also install templates from a folder directly with the `dotnet new -i {folder-path}` command.</span></span> <span data-ttu-id="7ff74-122">지정된 폴더는 찾은 템플릿의 템플릿 팩 식별자로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-122">The folder specified is treated as the template pack identifier for any template found.</span></span> <span data-ttu-id="7ff74-123">지정된 폴더의 계층 구조에 있는 모든 템플릿이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-123">Any template found in the specified folder's hierarchy is installed.</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

<span data-ttu-id="7ff74-124">명령에 지정된 `{folder-path}`는 찾은 모든 템플릿의 템플릿 팩 식별자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-124">The `{folder-path}` specified on the command becomes the template pack identifier for all templates found.</span></span> <span data-ttu-id="7ff74-125">[목록 템플릿](#list-templates) 섹션에 지정된 대로 `dotnet new -u` 명령을 사용하여 설치된 템플릿 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-125">As specified in the [List templates](#list-templates) section, you can get a list of templates installed with the `dotnet new -u` command.</span></span> <span data-ttu-id="7ff74-126">이 예제에서 템플릿 팩 식별자는 설치에 사용되는 폴더로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-126">In this example, the template pack identifier is shown as the folder used for install:</span></span>

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a><span data-ttu-id="7ff74-127">템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="7ff74-127">Uninstall template</span></span>

<span data-ttu-id="7ff74-128">템플릿은 [dotnet new](../tools/dotnet-new.md) SDK 명령에 `-u` 매개 변수를 사용하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-128">Templates are uninstalled through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-u` parameter.</span></span> <span data-ttu-id="7ff74-129">템플릿의 NuGet 패키지 식별자를 제공하거나 템플릿 파일이 포함된 폴더를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-129">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-package"></a><span data-ttu-id="7ff74-130">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="7ff74-130">NuGet package</span></span>

<span data-ttu-id="7ff74-131">NuGet 템플릿 팩을 설치한 후에는 NuGet 피드 또는 *nupkg* 파일에서 NuGet 패키지 식별자를 참조하여 해당 템플릿 팩을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-131">After a NuGet template pack is installed, either from a NuGet feed or a *nupkg* file, you can uninstall it by referencing the NuGet package identifier.</span></span>

<span data-ttu-id="7ff74-132">템플릿 팩을 제거하려면 `dotnet new -u {package-id}` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-132">To uninstall a template pack, use the `dotnet new -u {package-id}` command:</span></span>

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a><span data-ttu-id="7ff74-133">폴더</span><span class="sxs-lookup"><span data-stu-id="7ff74-133">Folder</span></span>

<span data-ttu-id="7ff74-134">템플릿이 [폴더 경로](#folder)를 통해 설치되면 폴더 경로는 템플릿 팩 식별자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-134">When templates are installed through a [folder path](#folder), the folder path becomes the template pack identifier.</span></span>

<span data-ttu-id="7ff74-135">템플릿 팩을 제거하려면 `dotnet new -u {package-folder-path}` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-135">To uninstall a template pack, use the `dotnet new -u {package-folder-path}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a><span data-ttu-id="7ff74-136">목록 템플릿</span><span class="sxs-lookup"><span data-stu-id="7ff74-136">List templates</span></span>

<span data-ttu-id="7ff74-137">패키지 식별자 없이 표준 제거 명령을 사용하여 각 템플릿을 제거하는 명령과 함께 설치된 템플릿 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-137">By using the standard uninstall command without a package identifier, you can see a list of installed templates along with the command that uninstalls each template.</span></span>

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a><span data-ttu-id="7ff74-138">다른 SDK에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="7ff74-138">Install templates from other SDKs</span></span>

<span data-ttu-id="7ff74-139">SDK 2.0, SDK 2.1 등을 차례로 설치하는 것과 같이 각 버전의 SDK를 순차적으로 설치한 경우 SDK의 모든 템플릿이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-139">If you've installed each version of the SDK sequentially, for example you installed SDK 2.0, then SDK 2.1, and so on, you'll have every SDK's templates installed.</span></span> <span data-ttu-id="7ff74-140">그러나 3.1 같은 이후 SDK 버전으로 시작하는 경우 [LTS(장기 지원) 릴리스](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)(SDK 3.1 릴리스 시점을 기준으로 SDK 2.1 및 SDK 3.1)용 템플릿만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-140">However, if you start with a later SDK version, like 3.1, only the templates for [LTS (long term support) releases](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) are included, which at the time of the SDK 3.1 release is SDK 2.1 and SDK 3.1.</span></span> <span data-ttu-id="7ff74-141">다른 릴리스용 템플릿은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-141">Templates for any other release aren't included.</span></span>

<span data-ttu-id="7ff74-142">.NET Core 템플릿은 NuGet에서 사용할 수 있으며 다른 템플릿처럼 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-142">The .NET Core templates are available on NuGet, and you can install them like any other template.</span></span> <span data-ttu-id="7ff74-143">자세한 내용은 [NuGet 호스티드 패키지 설치](#nuget-hosted-package)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff74-143">For more information, see [Install NuGet hosted package](#nuget-hosted-package).</span></span>

| <span data-ttu-id="7ff74-144">SDK</span><span class="sxs-lookup"><span data-stu-id="7ff74-144">SDK</span></span>              | <span data-ttu-id="7ff74-145">NuGet 패키지 식별자</span><span class="sxs-lookup"><span data-stu-id="7ff74-145">NuGet Package Identifier</span></span>                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7ff74-146">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7ff74-146">.NET Core 2.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| <span data-ttu-id="7ff74-147">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7ff74-147">.NET Core 2.2</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| <span data-ttu-id="7ff74-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7ff74-148">.NET Core 3.0</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| <span data-ttu-id="7ff74-149">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7ff74-149">.NET Core 3.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| <span data-ttu-id="7ff74-150">ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7ff74-150">ASP.NET Core 2.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| <span data-ttu-id="7ff74-151">ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7ff74-151">ASP.NET Core 2.2</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| <span data-ttu-id="7ff74-152">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7ff74-152">ASP.NET Core 3.0</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| <span data-ttu-id="7ff74-153">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7ff74-153">ASP.NET Core 3.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

<span data-ttu-id="7ff74-154">예를 들어 .NET Core SDK에는 .NET Core 2.1 및 .NET Core 3.1을 대상으로 하는 콘솔 앱용 템플릿이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-154">For example, the .NET Core SDK includes templates for a console app targeting .NET Core 2.1 and .NET Core 3.1.</span></span> <span data-ttu-id="7ff74-155">.NET Core 3.0을 대상으로 하려면 3.0 템플릿을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-155">If you wanted to target .NET Core 3.0, you would need to install the 3.0 templates.</span></span>

01. <span data-ttu-id="7ff74-156">.NET Core 3.0을 대상으로 하는 앱을 만들어 보세요.</span><span class="sxs-lookup"><span data-stu-id="7ff74-156">Try creating an app that targets .NET Core 3.0.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="7ff74-157">오류 메시지가 표시되면 템플릿을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-157">If you see an error message, you need to install the templates.</span></span>

    > <span data-ttu-id="7ff74-158">입력과 일치하는 설치된 템플릿을 찾을 수 없어 온라인에서 일치하는 템플릿을 찾고 있습니다...</span><span class="sxs-lookup"><span data-stu-id="7ff74-158">Couldn't find an installed template that matches the input, searching online for one that does...</span></span>

01. <span data-ttu-id="7ff74-159">.NET Core 3.0 프로젝트 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-159">Install the .NET Core 3.0 project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. <span data-ttu-id="7ff74-160">앱을 다시 만들어 보세요.</span><span class="sxs-lookup"><span data-stu-id="7ff74-160">Try creating the app a second time.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="7ff74-161">프로젝트가 생성되었음을 나타내는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-161">And you should see a message indicating the project was created.</span></span>

    > <span data-ttu-id="7ff74-162">“콘솔 애플리케이션” 템플릿을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-162">The template "Console Application" was created successfully.</span></span>
    >
    > <span data-ttu-id="7ff74-163">생성 후 작업을 처리하는 중... path-to-project-file.csproj에서 'dotnet restore'를 실행하는 중... 복원할 프로젝트를 확인하는 중... path-to-project-file.csproj의 복원이 1.05초 이내에 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-163">Processing post-creation actions... Running 'dotnet restore' on path-to-project-file.csproj... Determining projects to restore... Restore completed in 1.05 sec for path-to-project-file.csproj.</span></span>
    >
    > <span data-ttu-id="7ff74-164">복원했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff74-164">Restore succeeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ff74-165">참조</span><span class="sxs-lookup"><span data-stu-id="7ff74-165">See also</span></span>

- [<span data-ttu-id="7ff74-166">자습서: 항목 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="7ff74-166">Tutorial: Create an item template</span></span>](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
