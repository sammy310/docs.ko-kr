---
title: ASP.NET MVC 앱을 .NET 5로 업그레이드
description: .NET 업그레이드 도우미를 사용하여 기존 .NET Framework ASP.NET MVC 앱을 .NET 5로 업그레이드합니다. .NET 업그레이드 도우미는 .NET Framework에서 .NET 5로 앱을 마이그레이션하는 데 도움이 되는 CLI 도구입니다.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: 0c9af9e12b78df7c4a2aaed18155f7ee9f02870d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108360"
---
# <a name="upgrade-an-aspnet-mvc-app-to-net-5-with-the-net-upgrade-assistant"></a>.NET 업그레이드 도우미를 사용하여 ASP.NET MVC 앱을 .NET 5로 업그레이드

[.NET 업그레이드 도우미](upgrade-assistant-overview.md)는 .NET Framework ASP.NET MVC 앱을 .NET 5로 업그레이드하는 데 도움이 될 수 있는 명령줄 도구입니다. 이 문서에서는 다음을 제공합니다.

* .NET Framework ASP.NET MVC 앱에 대해 도구를 실행하는 방법의 데모
* 문제 해결 팁

## <a name="upgrade-net-framework-aspnet-mvc-apps"></a>.NET Framework ASP.NET MVC 앱 업그레이드

이 섹션에서는 .NET Framework 4.6.1을 대상으로 하는 새로 만든 ASP.NET MVC 앱에 대해 .NET 업그레이드 도우미를 실행하는 방법을 보여 줍니다. 도구를 설치하는 방법에 관한 자세한 내용은 [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)를 참조하세요.

### <a name="initial-demo-setup"></a>초기 데모 설정

고유한 .NET Framework 앱에 대해 .NET 업그레이드 도우미를 실행하는 경우 이 단계를 건너뛸 수 있습니다. 작동 방식만 확인하려는 경우 이 단계에서는 사용할 샘플 ASP.NET MVC 및 Web API(.NET Framework) 프로젝트를 설정하는 방법을 보여 줍니다.

Visual Studio를 사용하여 .NET Framework를 통해 새 ASP.NET 웹 애플리케이션 프로젝트를 만듭니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/new-project.png" alt-text="Visual Studio의 새 ASP.NET 웹 애플리케이션 프로젝트":::

프로젝트 이름을 **AspNetMvcTest** 로 지정합니다. **.NET Framework 4.6.1** 을 사용하도록 프로젝트를 구성합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/configure-project.png" alt-text="Visual Studio에서 ASP.NET 프로젝트 구성":::

다음 대화 상자에서 **MVC** 애플리케이션을 선택한 후 **만들기** 를 선택합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/create-mvc-webapi.png" alt-text="Visual Studio에서 ASP.NET MVC 프로젝트 만들기":::

만든 프로젝트와 해당 파일, 특히 해당 프로젝트 파일을 검토합니다.

### <a name="run-upgrade-assistant"></a>upgrade-assistant 실행

터미널을 열고 대상 프로젝트 또는 솔루션이 있는 폴더로 이동합니다. `upgrade-assistant` 명령을 실행하여 대상으로 지정할 프로젝트의 이름을 전달합니다(프로젝트 파일의 경로가 유효한 경우 어디서나 명령을 실행할 수 있음).

```console
upgrade-assistant .\AspNetMvcTest.csproj
```

도구가 실행되고 수행할 단계 목록을 표시합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/initial-run.png" alt-text=".NET 업그레이드 도우미 초기 화면":::

각 단계가 완료되면 도구는 사용자가 다음 단계를 적용하거나 건너뛰거나, 추가 세부 정보를 확인하거나, 로깅을 구성하거나, 프로세스를 종료할 수 있도록 하는 명령 세트를 제공합니다. 도구가 단계에서 작업을 수행하지 않을 것임을 감지하면 해당 단계를 자동으로 건너뛰고 수행할 작업이 있는 단계에 도달할 때까지 계속 다음 단계로 진행합니다. <kbd>Enter</kbd> 키를 누르면 다른 항목이 선택되지 않은 경우 다음 단계를 수행합니다.

이 예제에서는 매번 적용 단계가 선택됩니다. 첫 번째 단계는 프로젝트를 백업하는 것입니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/backup-project.png" alt-text=".NET 업그레이드 도우미 프로젝트 백업":::

도구는 백업을 위한 사용자 지정 경로를 입력하거나, 기본값을 사용하여 `.backup` 확장명을 사용하는 프로젝트 백업을 동일한 폴더에 배치할 것인지 묻는 메시지를 표시합니다. 도구가 수행하는 다음 단계는 프로젝트 파일을 SDK 스타일로 변환하는 것입니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/convert-project.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

프로젝트 형식이 업데이트된 후 다음 단계는 프로젝트의 TFM을 업데이트하는 것입니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-tfm.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

그런 다음, 도구는 프로젝트의 NuGet 패키지를 업데이트합니다. 여러 패키지에 업데이트가 필요하며 새 분석기 패키지가 추가됩니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-nuget-packages.png" alt-text=".NET 업그레이드 도우미 NuGet 패키지 업데이트":::

패키지가 업데이트된 후 다음 단계는 템플릿 파일(있는 경우)을 추가하는 것입니다. 도구는 추가해야 하는 4개의 예상 템플릿 항목을 기록한 후 추가합니다. 해당 항목에는 다음 파일이 포함됩니다.

- `Program.cs`
- `Startup.cs`
- `appsettings.json`
- `appsettings.Development.json`

해당 파일은 ASP.NET Core에서 [앱 시작](/aspnet/core/fundamentals/startup) 및 [구성](/aspnet/core/fundamentals/configuration)에 사용됩니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/add-template-files.png" alt-text=".NET 업그레이드 도우미 템플릿 파일 추가":::

그런 다음, 도구는 구성 파일을 마이그레이션합니다. 도구는 앱 설정을 식별하고 지원되지 않는 구성 섹션을 사용하지 않도록 설정한 다음, `appSettings` 구성 값을 마이그레이션합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config.png" alt-text=".NET 업그레이드 도우미 구성 마이그레이션":::

도구는 `system.web.webPages.razor/pages/namespaces`를 마이그레이션하여 구성 파일의 마이그레이션을 완료합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config2.png" alt-text=".NET 업그레이드 도우미 구성 마이그레이션":::

도구는 알려진 수정 사항을 적용하여 C# 참조를 새 대응 항목으로 마이그레이션합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-csharp.png" alt-text=".NET 업그레이드 도우미 C# 소스 업데이트":::

이는 마지막 프로젝트이므로, 다음 단계인 “다음 프로젝트로 이동”에서는 전체 솔루션을 마이그레이션하는 프로세스를 완료하라는 메시지를 표시합니다.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/complete-solution.png" alt-text=".NET 업그레이드 도우미 솔루션 완료":::

해당 프로세스가 완료된 후 프로젝트 파일을 열고 검토합니다. 다음과 같은 정적 파일을 찾습니다.

```xml
  <ItemGroup>
    <Content Include="fonts\glyphicons-halflings-regular.woff2" />
    <Content Include="fonts\glyphicons-halflings-regular.woff" />
    <Content Include="fonts\glyphicons-halflings-regular.ttf" />
    <Content Include="fonts\glyphicons-halflings-regular.eot" />
    <Content Include="Content\bootstrap.min.css.map" />
    <Content Include="Content\bootstrap.css.map" />
    <Content Include="Content\bootstrap-theme.min.css.map" />
    <Content Include="Content\bootstrap-theme.css.map" />
    <Content Include="Scripts\jquery-3.4.1.slim.min.map" />
    <Content Include="Scripts\jquery-3.4.1.min.map" />
  </ItemGroup>
```

웹 서버에서 제공해야 하는 정적 파일은 `wwwroot`라는 루트 수준 폴더 내의 적절한 폴더로 이동되어야 합니다. 자세한 내용은 [ASP.NET Core의 정적 파일](/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0)을 참조하세요. 파일이 이동된 후에는 이 파일에 해당하는 프로젝트 파일의 `<Content>` 요소가 삭제될 수 있습니다. 실제로 모든 `<Content>` 요소와 포함하는 그룹이 제거될 수 있습니다. 또한 `bootstrap` 또는 `jQuery`와 같은 클라이언트 쪽 라이브러리에 대한 `<PackageReference>`가 제거되어야 합니다.

기본적으로 프로젝트는 클래스 라이브러리로 변환됩니다. 첫 번째 줄의 `Sdk` 특성을 `Microsoft.NET.Sdk.Web`으로 변경하고 `<TargetFramework>`를 `net5.0`으로 설정합니다. 프로젝트를 컴파일합니다. 이때 오류 수는 상당히 적습니다. 새 ASP.NET 4.6.1 MVC 프로젝트를 이동할 때 나머지 오류는 `App_Start` 폴더의 파일을 참조합니다.

- BundleConfig.cs
- FilterConfig.cs
- RouteConfig.cs

해당 파일과 전체 `App_Start` 폴더가 삭제될 수 있습니다. 마찬가지로 `Global.asax` 및 `Global.asax.cs` 파일도 제거될 수 있습니다.

이때 남아 있는 오류만 묶음과 관련이 있습니다. [ASP.NET Core에서 묶음 및 축소를 구성하는 여러 가지 방법](/aspnet/core/migration/mvc?view=aspnetcore-5.0#configure-bundling-and-minification)이 있습니다. 프로젝트에 가장 적합한 항목을 선택합니다.

## <a name="troubleshooting-tips"></a>문제 해결 팁

.NET 업그레이드 도우미를 사용하는 경우 발생할 수 있는 여러 가지 알려진 문제가 있습니다. 경우에 따라 해당 문제는 .NET 업그레이드 도우미가 내부적으로 사용하는 [try-convert 도구](https://github.com/dotnet/try-convert)와 관련이 있습니다. 해당 도구는 더 많은 시나리오를 해결하기 위해 자주 업데이트되므로 최신 버전을 사용하고 있는지 확인하세요.

- **try-convert** 도구를 설치하고 _0.7.212201_ 버전 이상으로 업데이트해야 합니다.
- 이전 버전의 **try-convert** 도구는 사용자 지정 대상 또는 props 파일을 지원하지 않았습니다. 최신 버전으로 업그레이드할 수 없는 경우 해당 문제를 수동으로 해결해야 할 수 있습니다. 사용자 지정 대상 또는 props 파일에 대한 참조가 대상 프로젝트 파일에 포함된 경우 .NET 업그레이드 도우미가 실행되기 전에 해당 참조를 파일에서 수동으로 삭제해야 할 수 있습니다.

```xml
<Import Project="packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props" Condition="Exists('packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props')" />
```

[도구의 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues)에는 더 많은 문제 해결 팁과 알려진 문제가 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET 업그레이드 도우미를 사용하여 WPF 앱을 .NET 5로 업그레이드](upgrade-assistant-wpf-framework.md)
- [.NET 업그레이드 도우미를 사용하여 Windows Forms 앱을 .NET 5로 업그레이드](upgrade-assistant-winforms-framework.md)
- [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)
- [.NET 업그레이드 도우미 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant)
