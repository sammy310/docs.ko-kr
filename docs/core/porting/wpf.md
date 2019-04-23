---
title: WPF 앱을 .NET Core 3.0으로 포트
description: Windows용 .NET Core 3.0에 .NET Framework Windows Presentation Foundation 애플리케이션을 포팅하는 방법을 설명합니다.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 5c7e3aca0a473abb831693244d1b194985f2ef7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342208"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a>방법: WPF 데스크톱 앱을 .NET Core로 포트

이 문서에서는 .NET Framework에서 .NET Core 3.0으로 WPF(Windows Presentation Foundation) 기반 데스크톱 앱을 포팅하는 방법을 설명합니다. .NET Core 3.0 SDK는 WPF 애플리케이션을 지원합니다. WPF는 Windows 전용 프레임워크이고 Windows에서만 실행됩니다. 이 예제에서는 .NET Core SDK CLI를 사용하여 프로젝트를 만들고 관리합니다.

이 문서에서는 마이그레이션에 사용되는 파일의 유형을 식별하기 위해 다양한 이름이 사용됩니다. 프로젝트를 마이그레이션할 때 파일 이름이 다르게 지정되므로 파일을 아래 나열된 파일과 대조합니다.

| 파일 | 설명 |
| ---- | ----------- |
| **MyApps.sln** | 솔루션 파일의 이름입니다. |
| **MyWPF.csproj** | 포팅할 .NET Framework WPF 프로젝트의 이름입니다. |
| **MyWPFCore.csproj** | 만들 새 .NET Core 프로젝트의 이름입니다. |
| **MyAppCore.exe** | .NET Core WPF 앱은 실행 가능합니다. |

## <a name="prerequisites"></a>전제 조건

- 수행할 디자이너 작업용 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

  다음 Visual Studio 워크로드를 설치합니다.
  - .NET 데스크톱 개발
  - .NET 플랫폼 간 개발

- 문제 없이 빌드하고 실행하는 솔루션에서 작동하는 WPF 프로젝트입니다.
- 프로젝트는 C#으로 코딩되어야 합니다. 
- 최신 [.NET Core 3.0](https://aka.ms/netcore3download) 미리 보기를 설치합니다.

>[!NOTE]
>**Visual Studio 2017**은 .NET Core 3.0 프로젝트를 지원하지 않습니다. **Visual Studio 2019**는 .NET Core 3.0 프로젝트를 지원하지만 .NET Core 3.0 WPF 프로젝트의 시각적 디자이너는 아직 지원하지 않습니다. 시각적 디자이너를 사용하려면 .NET Core 프로젝트와 해당 파일을 공유하는 .NET WPF 프로젝트가 솔루션에 있어야 합니다.

### <a name="consider"></a>Consider

.NET Framework WPF 애플리케이션을 포팅할 때 고려해야 할 몇 가지 항목이 있습니다.

01. 애플리케이션이 마이그레이션에 적합한 후보인지 확인합니다.

    [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 사용하여 프로젝트가 .NET Core 3.0으로 마이그레이션되는지 확인합니다. 프로젝트에 .NET Core 3.0 관련 문제가 있는 경우 분석기는 해당 문제를 식별하는 데 도움이 됩니다.

01. 다른 버전의 WPF를 사용하고 있습니다.

    .NET Core 3.0 미리 보기 1이 릴리스될 때 WPF는 GitHub에서 오픈 소스가 됩니다. .NET Core WPF의 코드는 .NET Framework WPF 코드베이스의 포크입니다. 몇 가지 차이가 있을 수 있고 앱은 포팅되지 않습니다.

01. [Windows 호환성 팩][compat-pack]이 마이그레이션하는 데 도움이 될 수 있습니다.

    .NET Framework에서 사용할 수 있는 일부 API는 .NET Core 3.0에서 사용할 수 없습니다. [Windows 호환성 팩][compat-pack]은 이와 같은 다양한 API를 추가하며, WPF 앱이 .NET Core와 호환되도록 도와줍니다.

01. 프로젝트에서 사용되는 NuGet 패키지를 업데이트합니다.

    마이그레이션하기 전에 항상 NuGet 패키지의 최신 버전을 사용하는 것이 좋습니다. 애플리케이션이 NuGet 패키지를 참조하는 경우 최신 버전으로 업데이트합니다. 애플리케이션이 성공적으로 빌드되었는지 확인합니다. 업그레이드한 후 패키지 오류가 있는 경우에는 코드를 중단하지 않는 최신 버전으로 패키지를 다운그레이드합니다.

01. Visual Studio 2019는 .NET Core 3.0용 WPF 디자이너를 아직 지원하지 않습니다.

    현재 Visual Studio에서 WPF 디자이너를 사용하려면 기존 .NET Framework WPF 프로젝트 파일을 유지해야 합니다.

## <a name="create-a-new-sdk-project"></a>새 SDK 프로젝트 만들기

만들려는 새 .NET Core 3.0 프로젝트는 .NET Framework 프로젝트와 다른 디렉터리에 있어야 합니다. 둘 다 동일한 디렉터리에 있는 경우 **obj** 디렉터리에서 생성된 파일과 충돌할 수 있습니다. 이 예제에서는 **SolutionFolder** 디렉터리에 **MyWPFAppCore**라는 디렉터리를 만듭니다.

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

다음으로, **MyWPFAppCore** 디렉터리에 **MyWPFCore.csproj** 프로젝트를 만들어야 합니다. 선택한 텍스트 편집기를 사용하여 이 파일을 수동으로 만들 수 있습니다. 다음 XML에 붙여넣습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

프로젝트 파일을 수동으로 만들지 않으려면 Visual Studio 또는 .NET Core SDK를 사용하여 프로젝트를 생성하면 됩니다. 그러나 프로젝트 파일을 제외하고 프로젝트 템플릿에서 생성된 다른 모든 파일을 삭제해야 합니다. SDK를 사용하려면 **SolutionFolder** 디렉터리에서 다음 명령을 실행합니다.

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

**MyWPFCore.csproj**를 만든 후에 디렉터리 구조체는 다음과 같이 표시되어야 합니다.

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

**SolutionFolder** 디렉터리에서 Visual Studio 또는 .NET Core CLI를 사용하여 **MyWPFCore.csproj** 프로젝트를 **MyApps.sln**에 추가하려고 합니다.

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a>어셈블리 정보 생성 수정

.NET Framework로 만든 Windows Presentation Foundation 프로젝트에는 생성할 어셈블리 버전과 같은 어셈블리 특성을 포함하는 `AssemblyInfo.cs` 파일이 포함됩니다. SDK 스타일 프로젝트는 SDK 프로젝트 파일을 기반으로 이 정보를 자동으로 생성합니다. 두 유형의 “어셈블리 정보”가 모두 있으면 충돌이 발생합니다. 자동 생성을 비활성화하여 이 문제를 해결합니다. 그러면 프로젝트가 기존 `AssemblyInfo.cs` 파일을 강제로 사용합니다.

기본 `<PropertyGroup>` 노드에 추가할 세 가지 설정이 있습니다. 

- **GenerateAssemblyInfo**\
이 속성을 `false`로 설정하면 어셈블리 특성이 생성되지 않습니다. 따라서 .NET Framework 프로젝트의 기존 `AssemblyInfo.cs` 파일과 충돌하지 않습니다.

- **AssemblyName**\
이 속성 값은 컴파일할 때 생성되는 출력 이진입니다. 이름에 확장명을 추가할 필요가 없습니다. 예를 들어 `MyCoreApp`을 사용하면 `MyCoreApp.exe`가 생성됩니다.

- **RootNamespace**\
프로젝트에서 사용되는 기본 네임스페이스입니다. 이 네임스페이스는 .NET Framework 프로젝트의 기본 네임스페이스와 일치해야 합니다.

`MyWPFCore.csproj` 파일의 `<PropertyGroup>` 노드에 다음 세 개의 요소를 추가합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>소스 코드 추가
현재는 **MyWPFCore.csproj** 프로젝트가 코드를 컴파일하지 않습니다. 기본적으로 .NET Core 프로젝트는 현재 디렉터리 및 자식 디렉터리에 있는 모든 소스 코드를 자동으로 포함합니다. 상대 경로를 사용하여 .NET Framework 프로젝트의 코드를 포함하도록 프로젝트를 구성해야 합니다. .NET Framework 프로젝트가 창 및 제어의 아이콘과 리소스에 **.resx** 파일을 사용한 경우 해당 파일도 포함해야 합니다. 

프로젝트에 추가해야 하는 첫 번째 `<ItemGroup>` 노드에는 앱이 사용하는 시작 구성 및 리소스를 나타내는 **App.xaml** 파일이 포함됩니다. **App.xaml** 파일은 해당하는 **App.xaml.cs** 파일도 포함하지만 다른 `<ItemGroup>`에도 자동으로 포함됩니다.

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

다음으로, 다음과 같은 `<ItemGroup>` 노드를 프로젝트에 추가합니다. 각 문에는 자식 디렉터리를 포함하는 파일 GLOB 패턴이 포함됩니다. 프로젝트, 설정 파일 및 리소스에 대한 소스 코드가 포함됩니다. **obj** 디렉터리는 명시적으로 제외됩니다.

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

다음으로, **App.xaml**을 제외한 프로젝트의 **xaml** 파일마다 `<Page>` 항목을 포함하는 다른 `<ItemGroup>` 노드가 포함됩니다. **xaml** 형식인 창, 페이지 및 리소스를 모두 포함합니다. 여기에서 glob 패턴을 사용할 수 없고, 파일마다 항목을 추가하고 사용된 `<Generator>`를 나타내야 합니다.

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a>NuGet 패키지 추가

.NET Framework 프로젝트에서 참조하는 각 NuGet 패키지를 .NET Core 프로젝트에 추가합니다. 

대부분의 경우 .NET Framework WPF 앱에는 프로젝트에서 참조하는 모든 NuGet 패키지의 목록을 포함하는 **packages.config** 파일이 있습니다. 이 목록을 보고 .NET Core 프로젝트에 추가할 NuGet 패키지를 결정할 수 있습니다. 예를 들어, .NET Framework 프로젝트가 `MahApps.Metro` NuGet 패키지를 참조하는 경우 Visual Studio를 사용하여 프로젝트에 추가합니다. **SolutionFolder** 디렉터리에서 .NET Core CLI를 사용하여 패키지 참조를 추가할 수도 있습니다.

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

이전 명령은 **MyWPFCore.csproj** 프로젝트에 다음 NuGet 참조를 추가합니다.

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>컴파일 문제

프로젝트를 컴파일하는 데 문제가 있는 경우 .NET Framework에서 사용할 수 있지만 .NET Core에서는 사용할 수 없는 일부 Windows 전용 API를 사용하고 있는 것일 수 있습니다. [Windows 호환성 팩][compat-pack] NuGet 패키지를 프로젝트에 추가해 볼 수 있습니다. 이 패키지는 Windows에서만 실행되고 .NET Core 및 .NET Standard 프로젝트에 20,000개 정도의 Windows API를 추가합니다.

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

이전 명령은 **MyWPFCore.csproj** 프로젝트에 다음을 추가합니다.

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a>WPF Designer

이 문서에 설명된 대로, Visual Studio 2019만 .NET Framework 프로젝트의 WPF 디자이너를 지원합니다. 동시에 .NET Core 프로젝트를 만들면 .NET Framework 프로젝트를 사용하여 양식을 디자인하는 동안 .NET Core를 사용하여 프로젝트를 테스트할 수 있습니다. 솔루션 파일에는 .NET Framework 및 .NET Core 프로젝트가 모두 포함됩니다. .NET Framework 프로젝트에서 양식과 컨트롤을 추가 및 디자인합니다. 그러면 .NET Core 프로젝트에 추가한 파일 GLOB 패턴을 기반으로 새 파일이나 변경된 파일이 자동으로 .NET Core 프로젝트에 포함됩니다.

Visual Studio 2019가 WPF 디자이너를 지원하면 .NET Core 프로젝트 파일의 콘텐츠를 .NET Framework 프로젝트 파일로 복사하여 붙여넣을 수 있습니다. 그런 다음, `<Source>` 및 `<EmbeddedResource>` 항목과 함께 추가된 파일 GLOB 패턴을 삭제합니다. 앱에서 사용하는 프로젝트 참조의 경로를 수정합니다. 이렇게 하면 .NET Framework 프로젝트가 .NET Core 프로젝트로 효과적으로 업그레이드됩니다.
 
## <a name="next-steps"></a>다음 단계

* [Windows 호환성 팩][compat-pack]에 대해 자세히 알아봅니다.
* .NET Framework WPF 프로젝트를 .NET Core에 [포팅하는 방법에 대한 비디오](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt)을 시청하세요.

[compat-pack]: windows-compat-pack.md
