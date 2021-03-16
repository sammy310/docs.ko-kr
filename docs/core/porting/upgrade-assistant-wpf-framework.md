---
title: WPF 앱을 .NET 5로 업그레이드
description: .NET 업그레이드 도우미를 사용하여 기존 .NET Framework WPF 앱을 .NET 5로 업그레이드합니다. .NET 업그레이드 도우미는 .NET Framework에서 .NET 5로 앱을 마이그레이션하는 데 도움이 되는 CLI 도구입니다.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: e71cdc0ef5b72fcb7ae3985a26672e23ed0c1f12
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108294"
---
# <a name="upgrade-a-wpf-app-to-net-5-with-the-net-upgrade-assistant"></a>.NET 업그레이드 도우미를 사용하여 WPF 앱을 .NET 5로 업그레이드

[.NET 업그레이드 도우미](upgrade-assistant-overview.md)는 .NET Framework WPF 앱을 .NET 5로 업그레이드하는 데 도움이 될 수 있는 명령줄 도구입니다. 이 문서에서는 다음을 제공합니다.

* .NET Framework WPF 앱에 대해 도구를 실행하는 방법의 데모
* 문제 해결 팁

## <a name="upgrade-net-framework-wpf-apps"></a>.NET Framework WPF 앱 업그레이드

이 섹션에서는 .NET Framework 4.6.1을 대상으로 하는 새로 만든 WPF 앱에 대해 .NET 업그레이드 도우미를 실행하는 방법을 보여 줍니다. 도구를 설치하는 방법에 관한 자세한 내용은 [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)를 참조하세요.

### <a name="initial-demo-setup"></a>초기 데모 설정

고유한 .NET Framework 앱에 대해 .NET 업그레이드 도우미를 실행하는 경우 이 단계를 건너뛸 수 있습니다. 작동 방식만 확인해 보려는 경우 이 단계에서는 사용할 샘플 .NET WPF 프로젝트를 설정하는 방법을 보여 줍니다.

Visual Studio를 사용하여 .NET Framework를 통해 새 WPF 앱을 만듭니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/new-project.png" alt-text="Visual Studio의 새 WPF 프로젝트":::

프로젝트 이름을 **WpfTest** 로 지정합니다. **.NET Framework 4.6.1** 을 사용하도록 프로젝트를 구성합니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/configure-project.png" alt-text="Visual Studio에서 Windows Forms 프로젝트 구성":::

만든 프로젝트와 해당 파일, 특히 해당 프로젝트 파일을 검토합니다.

### <a name="run-upgrade-assistant"></a>upgrade-assistant 실행

터미널을 열고 대상 프로젝트 또는 솔루션이 있는 폴더로 이동합니다. `upgrade-assistant` 명령을 실행하여 대상으로 지정할 프로젝트의 이름을 전달합니다(프로젝트 파일의 경로가 유효한 경우 어디서나 명령을 실행할 수 있음).

```console
upgrade-assistant .\WpfTest.csproj
```

도구가 실행되고 수행할 단계 목록을 표시합니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/initial-run.png" alt-text=".NET 업그레이드 도우미 초기 화면":::

각 단계가 완료되면 도구는 사용자가 다음 단계를 적용하거나 건너뛰거나, 추가 세부 정보를 확인하거나, 로깅을 구성하거나, 프로세스를 종료할 수 있도록 하는 명령 세트를 제공합니다. 도구가 단계에서 작업을 수행하지 않을 것임을 감지하면 해당 단계를 자동으로 건너뛰고 수행할 작업이 있는 단계에 도달할 때까지 계속 다음 단계로 진행합니다. Enter 키를 누르면 다른 항목이 선택되지 않은 경우 다음 단계를 수행합니다.

이 예제에서는 매번 적용 단계가 선택됩니다. 첫 번째 단계는 프로젝트를 백업하는 것입니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/backup-project.png" alt-text=".NET 업그레이드 도우미 프로젝트 백업":::

도구는 백업을 위한 사용자 지정 경로를 입력하거나, 기본값을 사용하여 `.backup` 확장명을 사용하는 프로젝트 백업을 동일한 폴더에 배치할 것인지 묻는 메시지를 표시합니다. 도구가 수행하는 다음 단계는 프로젝트 파일을 SDK 스타일로 변환하는 것입니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/convert-project.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

프로젝트 형식이 업데이트된 후 다음 단계는 프로젝트의 TFM을 업데이트하는 것입니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/update-tfm.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

그런 다음, 도구는 프로젝트의 NuGet 패키지를 업데이트합니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/update-nuget-packages.png" alt-text=".NET 업그레이드 도우미 NuGet 패키지 업데이트":::

패키지가 업데이트된 후 다음 단계는 템플릿 파일(있는 경우)을 추가하는 것입니다. 이 경우 추가해야 하는 템플릿 파일이 없습니다. 이 단계에서는 아래와 같이 계속해서 앱 구성 파일을 마이그레이션하고 C# 소스를 업데이트하여 수정 내용을 적용합니다. 이 프로젝트에서는 구성 파일이나 소스 코드를 변경할 필요가 없으므로 해당 단계가 자동으로 진행되었습니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/add-template-files.png" alt-text=".NET 업그레이드 도우미 템플릿 파일 추가 및 구성 마이그레이션":::

이는 마지막 프로젝트이므로, 다음 단계인 “다음 프로젝트로 이동”에서는 전체 솔루션을 마이그레이션하는 프로세스를 완료하라는 메시지를 표시합니다.

:::image type="content" source="media/upgrade-assistant-wpf-framework/complete-solution.png" alt-text=".NET 업그레이드 도우미 솔루션 완료":::

이 프로세스가 완료된 후 마이그레이션된 WPF 프로젝트는 다음과 같이 표시됩니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0-windows</TargetFramework>
    <OutputType>WinExe</OutputType>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <UseWPF>true</UseWPF>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
    <PackageReference Include="Microsoft.DotNet.UpgradeAssistant.Extensions.Default.Analyzers" Version="0.2.211942">
      <PrivateAssets>all</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.2" />
  </ItemGroup>
</Project>
```

또한 .NET 업그레이드 도우미는 업그레이드 프로세스를 계속하는 데 도움이 되는 분석기를 프로젝트에 추가합니다.

## <a name="troubleshooting-tips"></a>문제 해결 팁

.NET 업그레이드 도우미를 사용하는 경우 발생할 수 있는 여러 가지 알려진 문제가 있습니다. 경우에 따라 해당 문제는 .NET 업그레이드 도우미가 내부적으로 사용하는 [try-convert 도구](https://github.com/dotnet/try-convert)와 관련이 있습니다. 해당 도구는 더 많은 시나리오를 해결하기 위해 자주 업데이트되므로 최신 버전을 사용하고 있는지 확인하세요.

- try-convert 도구를 설치하고 _0.7.21201_ 버전 이상으로 업데이트해야 합니다.
- 이전 버전의 try-convert 도구는 사용자 지정 대상 또는 props 파일을 지원하지 않았습니다. 최신 버전으로 업그레이드할 수 없는 경우 해당 문제를 수동으로 해결해야 할 수 있습니다. 사용자 지정 대상 또는 props 파일에 대한 참조가 대상 프로젝트 파일에 포함된 경우 .NET 업그레이드 도우미가 실행되기 전에 해당 참조를 파일에서 수동으로 삭제해야 할 수 있습니다.

[도구의 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues)에는 더 많은 문제 해결 팁과 알려진 문제가 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET 업그레이드 도우미를 사용하여 Windows Forms 앱을 .NET 5로 업그레이드](upgrade-assistant-winforms-framework.md)
- [.NET 업그레이드 도우미를 사용하여 ASP.NET MVC 앱을 .NET 5로 업그레이드](upgrade-assistant-aspnetmvc.md)
- [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)
- [.NET 업그레이드 도우미 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant)
