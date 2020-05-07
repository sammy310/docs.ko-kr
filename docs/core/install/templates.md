---
title: SDK 템플릿 설치 및 관리 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core 템플릿을 설치하는 방법을 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 0a3c8655d55bf63de1e91337ce3a2ac399b07d0f
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200602"
---
# <a name="manage-net-project-and-item-templates"></a>.NET 프로젝트 및 항목 템플릿 관리

.NET Core는 사용자가 NuGet, NuGet 패키지 파일 또는 파일 시스템 디렉터리에서 템플릿을 설치하거나 제거할 수 있도록 하는 템플릿 시스템을 제공합니다. 이 문서에서는 .NET Core SDK CLI를 통해 .NET Core 템플릿을 관리하는 방법을 설명합니다.

템플릿 만들기에 관한 자세한 내용은 [자습서: 템플릿 만들기](../tutorials/cli-templates-create-item-template.md)를 참조하세요.

## <a name="install-template"></a>템플릿 설치

템플릿은 `-i` 매개 변수를 사용하여 [dotnet new](../tools/dotnet-new.md) SDK 명령을 통해 설치됩니다. 템플릿의 NuGet 패키지 식별자를 제공하거나 템플릿 파일이 포함된 폴더를 제공할 수 있습니다.

### <a name="nuget-hosted-package"></a>NuGet 호스티드 패키지

.NET CLI 템플릿은 광범위한 배포를 위해 [NuGet](https://www.nuget.org/)에 업로드됩니다. 템플릿은 프라이빗 피드에서 설치할 수도 있습니다. NuGet 피드에 템플릿을 업로드하는 대신 [로컬 NuGet 패키지](#local-nuget-package) 섹션에 설명된 대로 *nupkg* 템플릿 파일을 배포하고 수동으로 설치할 수 있습니다.

NuGet 피드를 구성하는 방법에 관한 자세한 내용은 [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)를 참조하세요.

기본 NuGet 피드에서 템플릿 팩을 설치하려면 `dotnet new -i {package-id}` 명령을 사용합니다.

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

특정 버전으로 기본 NuGet 피드에서 템플릿 팩을 설치하려면 `dotnet new -i {package-id}::{version}` 명령을 사용합니다.

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a>로컬 NuGet 패키지

템플릿 팩을 만들면 *nupkg* 파일이 생성됩니다. 템플릿을 포함하는 *nupkg* 파일이 있는 경우 `dotnet new -i {path-to-package}` 명령을 사용하여 설치할 수 있습니다.

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

### <a name="folder"></a>폴더

*nupkg* 파일에서 템플릿을 설치하는 대신 `dotnet new -i {folder-path}` 명령을 사용하여 폴더에서 직접 템플릿을 설치할 수도 있습니다. 지정된 폴더는 찾은 템플릿의 템플릿 팩 식별자로 처리됩니다. 지정된 폴더의 계층 구조에 있는 모든 템플릿이 설치됩니다.

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

명령에 지정된 `{folder-path}`는 찾은 모든 템플릿의 템플릿 팩 식별자가 됩니다. [목록 템플릿](#list-templates) 섹션에 지정된 대로 `dotnet new -u` 명령을 사용하여 설치된 템플릿 목록을 가져올 수 있습니다. 이 예제에서 템플릿 팩 식별자는 설치에 사용되는 폴더로 표시됩니다.

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

## <a name="uninstall-template"></a>템플릿 제거

템플릿은 `-u` 매개 변수를 사용하여 [dotnet new](../tools/dotnet-new.md) SDK 명령을 통해 제거됩니다. 템플릿의 NuGet 패키지 식별자를 제공하거나 템플릿 파일이 포함된 폴더를 제공할 수 있습니다.

### <a name="nuget-package"></a>NuGet 패키지

NuGet 템플릿 팩을 설치한 후에는 NuGet 피드 또는 *nupkg* 파일에서 NuGet 패키지 식별자를 참조하여 해당 템플릿 팩을 제거할 수 있습니다.

템플릿 팩을 제거하려면 `dotnet new -u {package-id}` 명령을 사용합니다.

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a>폴더

템플릿이 [폴더 경로](#folder)를 통해 설치되면 폴더 경로는 템플릿 팩 식별자가 됩니다.

템플릿 팩을 제거하려면 `dotnet new -u {package-folder-path}` 명령을 사용합니다.

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

## <a name="list-templates"></a>목록 템플릿

패키지 식별자 없이 표준 제거 명령을 사용하여 각 템플릿을 제거하는 명령과 함께 설치된 템플릿 목록을 볼 수 있습니다.

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

## <a name="install-templates-from-other-sdks"></a>다른 SDK에서 템플릿 설치

SDK 2.0, SDK 2.1 등을 차례로 설치하는 것과 같이 각 버전의 SDK를 순차적으로 설치한 경우 SDK의 모든 템플릿이 설치됩니다. 그러나 3.1 같은 이후 SDK 버전으로 시작하는 경우 [LTS(장기 지원) 릴리스](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)(SDK 3.1 릴리스 시점을 기준으로 SDK 2.1 및 SDK 3.1)용 템플릿만 포함됩니다. 다른 릴리스용 템플릿은 포함되지 않습니다.

.NET Core 템플릿은 NuGet에서 사용할 수 있으며 다른 템플릿처럼 설치할 수 있습니다. 자세한 내용은 [NuGet 호스티드 패키지 설치](#nuget-hosted-package)를 참조하세요.

| SDK              | NuGet 패키지 식별자                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| .NET Core 2.1    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| .NET Core 2.2    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| .NET Core 3.0    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| .NET Core 3.1    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| ASP.NET Core 2.1 | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| ASP.NET Core 2.2 | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| ASP.NET Core 3.0 | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| ASP.NET Core 3.1 | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

예를 들어 .NET Core SDK에는 .NET Core 2.1 및 .NET Core 3.1을 대상으로 하는 콘솔 앱용 템플릿이 포함됩니다. .NET Core 3.0을 대상으로 하려면 3.0 템플릿을 설치해야 합니다.

01. .NET Core 3.0을 대상으로 하는 앱을 만들어 보세요.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    오류 메시지가 표시되면 템플릿을 설치해야 합니다.

    > 입력과 일치하는 설치된 템플릿을 찾을 수 없어 온라인에서 일치하는 템플릿을 찾고 있습니다...

01. .NET Core 3.0 프로젝트 템플릿을 설치합니다.

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. 앱을 다시 만들어 보세요.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    프로젝트가 생성되었음을 나타내는 메시지가 표시됩니다.

    > “콘솔 애플리케이션” 템플릿을 만들었습니다.
    >
    > 생성 후 작업을 처리하는 중... path-to-project-file.csproj에서 'dotnet restore'를 실행하는 중... 복원할 프로젝트를 확인하는 중... path-to-project-file.csproj의 복원이 1.05초 이내에 완료되었습니다.
    >
    > 복원했습니다.

## <a name="see-also"></a>참조

- [자습서: 항목 템플릿 만들기](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
