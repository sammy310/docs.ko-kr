---
title: .NET 5로의 마이그레이션 예제
description: .NET Framework를 대상으로 하는 샘플 애플리케이션을 .NET 5로 마이그레이션하는 방법을 보여 줍니다.
ms.date: 01/19/2021
ms.openlocfilehash: 02a45859dfca891598e235e3de1ed968aefb5bf4
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605167"
---
# <a name="example-of-migrating-to-net"></a>.NET으로의 마이그레이션 예제

이 장에서는 기존 애플리케이션을 .NET Framework에서 .NET으로 마이그레이션하는 데 도움이 되는 실용적인 지침을 제공합니다.

또한 수행할 수 있는 잘 구성된 프로세스 및 각 단계에서 고려해야 할 가장 중요한 사항을 제공합니다.

다음으로 WinForms 및 WPF 버전의 샘플 데스크톱 애플리케이션에 대한 단계별 마이그레이션 프로세스를 문서화합니다.

## <a name="migration-process-overview"></a>마이그레이션 프로세스 개요

마이그레이션 프로세스는 다음과 같은 순차적인 4단계로 구성됩니다.

1. **준비**: 프로젝트에서 미래를 파악하기 위해 필요한 종속성을 이해합니다. 이 단계에서는 마이그레이션의 시작 지점을 간소화하는 상태로 현재 프로젝트를 전환합니다.

2. **프로젝트 파일 마이그레이션:** .NET 프로젝트는 새로운 SDK 스타일 프로젝트 형식을 사용합니다. 이 형식을 사용하여 새 프로젝트 파일을 만들거나 SDK 스타일을 사용해야 하는 프로젝트 파일을 업데이트합니다.

3. **코드 수정 및 빌드:** .NET Framework와 .NET 간의 API 수준 차이를 해결하는 코드를 .NET에서 빌드합니다. 필요한 경우 .NET을 지원하는 패키지로 타사 패키지를 업데이트합니다.

4. **실행 및 테스트:** 런타임까지 표시되지 않는 차이점이 있을 수 있습니다. 따라서 애플리케이션을 실행하고 모든 항목이 예상대로 작동하는지 테스트해야 합니다.

### <a name="preparation"></a>준비

#### <a name="migrate-packagesconfig-file"></a>packages.config 파일 마이그레이션

.NET Framework 애플리케이션에서는 외부 패키지에 대한 모든 참조가 *packages.config* 파일에 선언됩니다. .NET에서는 *packages.config* 파일을 더 이상 사용할 필요가 없습니다. 대신 프로젝트 파일 내에서 [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) 속성을 사용하여 앱에 대한 NuGet 패키지를 지정합니다.

따라서 한 형식에서 다른 형식으로 전환해야 합니다. *packages.config* 파일에 포함된 종속성을 가져와 `PackageReference` 형식으로 프로젝트 파일로 마이그레이션하여 수동으로 업데이트를 수행할 수 있습니다. 또는 *packages.config* 파일을 마우스 오른쪽 단추로 클릭하고 **packages.config를 PackageReference로 마이그레이션** 옵션을 선택하여 Visual Studio에서 작업을 수행하도록 할 수 있습니다.

#### <a name="verify-every-dependency-compatibility-in-net"></a>.NET의 모든 종속성 호환성 확인

패키지 참조를 마이그레이션한 다음에는 각 참조에서 호환성을 확인해야 합니다. 애플리케이션에서 사용하고 있는 각 NuGet 패키지의 종속성은 [nuget.org](https://www.nuget.org/)에서 확인할 수 있습니다. .NET은 모든 버전의 .NET Standard를 [지원](../../standard/net-standard.md#net-implementation-support)하므로 패키지에 .NET Standard 종속성이 있으면 .NET 5.0에서 작동합니다. 다음 이미지는 `Castle.Windsor` 패키지에 대한 종속성을 보여 줍니다.

![Castle.Windsor 패키지에 대한 NuGet 종속성 스크린샷](./media/example-migration-core/nuget-dependencies.png)

패키지 호환성을 확인하려면 버전 및 종속성에 대한 자세한 정보를 제공하는 <https://fuget.org> 도구를 사용할 수 있습니다.

프로젝트가 .NET을 지원하지 않는 이전 패키지 버전을 참조하고 있지만 지원하는 최신 버전을 찾을 수 있습니다. 따라서 패키지를 최신 버전으로 업데이트하는 것이 일반적으로 가장 좋습니다. 그러나 패키지 버전을 업데이트하면 몇 가지 호환성이 손상되는 변경이 발생하여 코드를 강제로 업데이트해야 할 수 있습니다.

호환되는 버전을 찾지 못하면 어떻게 되나요? 이러한 호환성이 손상되는 변경 때문에 패키지 버전을 업데이트하지 않으려는 경우는 어떻게 되나요? .NET 애플리케이션의 .NET Framework 패키지에 종속될 수 있기 때문에 걱정하지 않아도 됩니다. 다만 외부 패키지가 .NET에서 사용할 수 없는 API를 호출하는 경우 런타임 오류가 발생할 수 있으므로 광범위하게 테스트해야 합니다. 이 방법은 업데이트하지 않으려는 이전 패키지를 사용하고 있고 .NET에서 작동하도록 변경하려는 경우에 적합합니다.

#### <a name="check-for-api-compatibility"></a>API 호환성 확인

.NET Framework와 .NET의 API 화면은 유사하지만 동일하지는 않으므로 .NET에서 사용할 수 있는 API와 사용할 수 없는 API를 확인해야 합니다. .NET 이식성 분석기 도구를 사용하면 .NET에 없는 API를 사용하도록 표시할 수 있습니다. 앱의 이진 수준을 확인하고 호출되는 모든 API를 추출한 다음, 대상 프레임워크(이 경우 .NET 5.0)에서 사용할 수 없는 API를 나열합니다.

이 도구에 대한 자세한 내용은 다음에서 확인할 수 있습니다.

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

이 도구의 흥미로운 측면은 변경할 수 없는 외부 패키지의 코드가 아니라 사용자 코드의 차이점만 표시한다는 점입니다. 이러한 패키지가 .NET에서 작동하도록 하려면 대부분의 패키지를 업데이트해야 합니다.

### <a name="migrate-with-try-convert-tool"></a>Try Convert 도구를 사용하여 마이그레이션

[Try Convert](https://github.com/dotnet/try-convert/releases) 도구는 프로젝트를 마이그레이션하는 좋은 방법입니다. 프로젝트 파일을 이전 스타일에서 새 SDK 스타일로 업그레이드하려고 시도하고 적용 가능한 프로젝트를 .NET 5로 변경하는 글로벌 도구입니다. 설치되면 다음 명령을 실행할 수 있습니다.

```dotnetcli
try-convert -p "<path to your project file>"
```

또는

```dotnetcli
try-convert -w "<path to your solution>"
```

> [!NOTE]
> try-convert 도구는 [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)의 일부로 자동으로 실행됩니다. Try Convert만이 아니라 전체 업그레이드 도우미를 실행하는 것이 좋습니다.

도구에서 변환을 시도한 후 Visual Studio에서 파일을 다시 로드하여 실행하고 테스트합니다. 프로젝트의 세부 사항으로 인해 Try Convert에서 변환하지 못할 수 있습니다. 이런 경우 다음 단계를 참조할 수 있습니다.

#### <a name="migrate-manually"></a>수동으로 마이그레이션

1. 새 .NET 프로젝트 만들기

대부분의 경우 기존 프로젝트를 새 .NET 형식으로 업데이트하는 것이 좋습니다. 그러나 이전 프로젝트를 유지하면서 새 프로젝트를 만들 수도 있습니다. 이전 프로젝트를 업데이트하는 경우의 주요 단점은 사용자와 개발 팀에 중요할 수 있는 디자이너를 사용할 수 없다는 것입니다. 디자이너를 계속 사용하려면 이전 프로젝트를 사용하여 병렬로 새 .NET 프로젝트를 만들고 자산을 공유해야 합니다. 디자이너에서 UI 요소를 수정하려면 이전 프로젝트로 전환하면 됩니다. 자산은 연결되어 있으므로 .NET 프로젝트에서도 업데이트됩니다.

.NET용 [SDK 스타일 프로젝트](../../core/project-sdk/msbuild-props.md)는 .NET Framework의 프로젝트 형식보다 훨씬 더 간단합니다. 앞에서 설명한 `PackageReference` 항목과 별개로 훨씬 더 많은 작업을 수행할 필요가 없습니다. 새 프로젝트 형식에는 `.cs` 및 `.xaml` 파일과 같이 [기본적으로 특정 확장명을 사용하는 파일이 포함](../../core/project-sdk/overview.md#default-includes-and-excludes)되어 프로젝트 파일에 명시적으로 포함할 필요가 없습니다.

#### <a name="assemblyinfo-considerations"></a>AssemblyInfo 고려 사항

특성은 .NET 프로젝트에서 자동 생성됩니다. 프로젝트에 *AssemblyInfo.cs* 파일이 포함되어 있으면 정의가 중복되어 컴파일 충돌이 발생합니다. .NET 프로젝트 파일에 다음 항목을 추가하여 이전 *AssemblyInfo.cs* 파일을 삭제하거나 자동 생성을 사용하지 않도록 설정할 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a>리소스

포함 리소스는 자동으로 포함되지만 리소스는 포함되지 않으므로 새 프로젝트 파일로 리소스를 마이그레이션해야 합니다.

#### <a name="package-references"></a>패키지 참조

**packages.config를 PackageReference로 마이그레이션** 옵션을 사용하면 앞에서 설명한 대로 외부 패키지 참조를 새 형식으로 쉽게 이동할 수 있습니다.

#### <a name="update-package-references"></a>패키지 참조 업데이트

이전 섹션에 표시된 대로 호환되는 것으로 확인된 패키지의 버전을 업데이트합니다.

### <a name="fix-the-code-and-build"></a>코드 수정 및 빌드

#### <a name="microsoftwindowscompatibility"></a>Microsoft.Windows.Compatibility

애플리케이션이 레지스트리, ACL, WCF 등 .NET에서 사용할 수 없는 API에 종속되는 경우 이러한 Windows 관련 API를 추가하려면 `Microsoft.Windows.Compatibility` 패키지에 대한 참조를 포함해야 합니다. 이러한 API는 플랫폼 간 API가 아니므로 .NET에서 작동은 하지만 포함되지는 않습니다.

코드와 호환되지 않는 API를 식별하는 데 도움이 되는 API 분석기(<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>)라는 도구가 있습니다.

#### <a name="use-if-directives"></a>\#if 지시문 사용

.NET Framework 및 .NET을 대상으로 하는 경우 다른 실행 경로가 필요하면 컴파일 상수를 사용해야 합니다. 일부 \#if 지시문을 코드에 추가하여 두 대상에 대해 동일한 코드베이스를 유지합니다.

#### <a name="technologies-not-available-on-net"></a>.NET에서 사용할 수 없는 기술

다음과 같은 일부 기술은 .NET에서 사용할 수 없습니다.

* AppDomain
* 원격 통신
* 코드 액세스 보안
* WCF 서버
* Windows Workflow

따라서 애플리케이션에서 이러한 기술을 사용하고 있는 경우 대체할 기술을 찾아야 합니다. 자세한 내용은 [.NET Core 및 .NET 5+에서 사용할 수 없는 .NET Framework 기술](../../core/porting/net-framework-tech-unavailable.md) 문서를 참조하세요.

#### <a name="regenerate-autogenerated-clients"></a>자동 생성된 클라이언트 다시 생성

애플리케이션에서 WCF 클라이언트와 같은 자동 생성된 코드를 사용하는 경우 .NET을 대상으로 하도록 이 코드를 다시 생성해야 할 수 있습니다. 경우에 따라 기본 .NET 어셈블리 집합의 일부로 포함되지 않아 일부 참조가 누락된 것을 확인할 수 있습니다. <https://apisof.net/> 같은 도구를 사용하여 누락된 참조가 있는 어셈블리를 쉽게 찾아 NuGet에서 추가할 수 있습니다.

#### <a name="rolling-back-package-versions"></a>패키지 버전 롤백

일반적으로 모든 단일 패키지 버전을 .NET과 호환되도록 업데이트하는 것이 좋다고 앞에서 설명했습니다. 그러나 어셈블리의 업데이트된 버전과 호환되는 버전을 대상으로 하면 효과가 없을 수 있습니다. 변경 비용이 허용되지 않는 경우 패키지 버전을 롤백하여 .NET Framework에서 사용하는 버전을 유지하는 것이 좋습니다. .NET을 대상으로 하지 않을 수 있지만 지원되지 않는 일부 API를 호출하지 않는 한 제대로 작동합니다.

### <a name="run-and-test"></a>실행 및 테스트

애플리케이션을 오류 없이 빌드했으면 모든 기능을 테스트하여 마이그레이션의 마지막 단계를 시작할 수 있습니다.

이 최종 단계에서는 애플리케이션의 복잡성 및 사용 중인 종속성과 API에 따라 여러 가지 문제가 발생할 수 있습니다.

예를 들어 구성 파일(*app.config*)을 사용하는 경우 구성 섹션이 없음과 같은 일부 오류가 런타임에 발생할 수 있습니다. `Microsoft.Extensions.Configuration` NuGet 패키지를 사용하여 해당 오류를 해결해야 합니다.

오류가 발생하는 또 다른 이유는 .NET에서 지원되지 않는 `BeginInvoke` 및 `EndInvoke` 메서드의 사용입니다. 이러한 메서드는 .NET에 없는 원격에 종속성이 있기 때문에 .NET에서 지원되지 않습니다. 이 문제를 해결하려면 `await` 키워드(사용 가능한 경우) 또는 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> 메서드를 사용하세요.

호환성 분석기를 사용하면 .NET에서 런타임에 문제를 발생시킬 수 있는 API 및 코드 패턴을 코드에서 식별할 수 있습니다. <https://github.com/dotnet/platform-compat>으로 이동하여 프로젝트에서 .NET API 분석기를 사용합니다.

## <a name="migrating-a-windows-forms-application"></a>Windows Forms 애플리케이션 마이그레이션

Windows Forms 애플리케이션의 전체 마이그레이션 프로세스를 보여 주기 위해 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>에서 제공되는 eShop 샘플 애플리케이션을 마이그레이션하도록 선택했습니다. 마이그레이션의 전체 결과는 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>에서 확인할 수 있습니다.

이 애플리케이션은 제품 카탈로그를 보여 주고 사용자가 제품을 탐색, 필터링, 검색할 수 있도록 합니다. 아키텍처 관점에서 앱은 백 엔드 데이터베이스의 외관 역할을 하는 외부 WCF 서비스를 사용합니다.

주 애플리케이션 창은 다음 그림과 같이 표시됩니다.

![주 애플리케이션 창](./media/example-migration-core/main-application-window.png)

*.csproj* 프로젝트 파일을 열면 다음과 같이 표시됩니다.

![csproj 파일 내용 스크린샷](./media/example-migration-core/csproj-file.png)

앞에서 설명한 대로 .NET 프로젝트 스타일은 더 간결하며 프로젝트 구조를 새로운 .NET SDK 스타일로 마이그레이션해야 합니다.

솔루션 탐색기에서 Windows Forms 프로젝트를 마우스 오른쪽 단추로 클릭하고 **프로젝트 언로드** > **편집** 을 선택합니다.

이제 .csproj 파일을 업데이트할 수 있습니다. 전체 내용을 삭제하고 다음 코드로 바꿉니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

프로젝트를 저장하고 다시 로드합니다. 이제 프로젝트 파일 업데이트가 완료되었으며 프로젝트가 .NET을 대상으로 합니다.

이때 프로젝트를 컴파일하면 WCF 클라이언트 참조와 관련된 몇 가지 오류가 발생합니다. 이 코드는 자동으로 생성되므로 .NET을 대상으로 하도록 다시 생성해야 합니다.

![오류를 보여 주는 Visual Studio의 오류 목록](./media/example-migration-core/winforms-compilation-errors.png)

*Reference.cs* 파일을 삭제하고 새 서비스 클라이언트를 생성합니다.

**연결된 서비스** 를 마우스 오른쪽 단추로 클릭하고 **연결된 서비스 추가** 옵션을 선택합니다.

![연결된 서비스 추가 옵션이 선택된 연결된 서비스 메뉴의 스크린샷](./media/example-migration-core/add-connected-service.png)

연결된 서비스 창이 열립니다. **Microsoft WCF Web Service** 옵션을 선택합니다.

![연결된 서비스 창의 스크린샷](./media/example-migration-core/connected-services-window.png)

이 예제와 동일한 솔루션에 WCF 서비스가 있는 경우 서비스 URL을 지정하는 대신 **검색** 옵션을 선택할 수 있습니다.

![WCF Web Service Reference 구성 창의 스크린샷](./media/example-migration-core/configure-wcf-reference.png)

서비스가 있으면 서비스에 의해 구현된 API 계약이 도구에 반영됩니다. 다음 이미지와 같이 네임스페이스의 이름을 `eShopServiceReference`로 변경합니다.

![API 계약 및 변경된 네임스페이스의 스크린샷](./media/example-migration-core/api-contract-namespace.png)

**마침** 단추를 선택합니다. 잠시 후 생성된 코드가 표시됩니다.

자동 생성된 세 개의 파일이 표시됩니다.

1. *Getting Started*: WCF에 대한 몇 가지 정보를 제공하는 GitHub에 대한 링크입니다.
2. *ConnectedService.json*: 서비스에 연결하는 구성 매개 변수입니다.
3. *Reference.cs*: 실제 WCF 클라이언트 코드입니다.

![자동 생성된 세 개의 파일이 있는 솔루션 탐색기 창의 스크린샷](./media/example-migration-core/autogenerated-files.png)

다시 컴파일하면 *Helper* 폴더 내의 *.cs* 파일에서 발생하는 많은 오류가 표시됩니다. 이 폴더는 .NET Framework 버전에 있지만 이전 *.csproj* 에는 포함되지 않습니다. 그러나 새로운 SDK 스타일 프로젝트를 사용하면 프로젝트 파일 위치 아래에 있는 모든 코드 파일이 기본적으로 포함됩니다. 즉, 새 .NET Core 프로젝트는 *Helper* 폴더 내의 파일을 컴파일하려고 합니다. 해당 폴더는 필요하지 않으므로 삭제해도 안전합니다.

프로젝트를 다시 컴파일하고 실행하면 제품 이미지가 표시되지 않습니다. 문제는 파일 경로가 약간 변경되었다는 점입니다. 이 문제를 해결하려면 경로에 다른 수준의 깊이를 추가하여 `CatalogView.cs` 파일에서 다음 줄을 업데이트해야 합니다.

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

을

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

이렇게 변경하면 애플리케이션이 .NET Core에서 예상대로 시작되고 실행되는 것을 확인할 수 있습니다.

## <a name="migrating-a-wpf-application"></a>WPF 애플리케이션 마이그레이션

`Shop.ClassicWPF` 샘플 애플리케이션을 사용하여 마이그레이션을 수행합니다. 다음 이미지는 마이그레이션 전의 앱 스크린샷을 보여 줍니다.

![마이그레이션 전의 샘플 앱](./media/example-migration-core/app-before-migration.png)

이 애플리케이션은 로컬 SQL Server Express 데이터베이스를 사용하여 제품 카탈로그 정보를 저장합니다. 이 데이터베이스는 WPF 애플리케이션에서 직접 액세스합니다.

먼저 *.csproj* 파일을 .NET Core 애플리케이션에서 사용하는 새 SDK 스타일로 업데이트해야 합니다. Windows Forms 마이그레이션에서 설명한 것과 동일한 단계를 수행합니다. 프로젝트를 언로드하고 *.csproj* 파일을 열고 내용을 업데이트하고 프로젝트를 다시 로드합니다.

이 경우 *.csproj* 파일의 내용을 모두 삭제하고 다음 코드로 바꿉니다.

```xml
 <Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWpf>true</UseWpf>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

프로젝트를 다시 로드하고 컴파일하면 다음과 같은 오류가 표시됩니다.

![단일 오류 CS0234를 보여 주는 Visual Studio의 오류 목록](./media/example-migration-core/wpf-compilation-error.png)

*.csproj* 내용을 모두 삭제했으므로 이전 프로젝트에 있던 프로젝트 참조 사양이 손실되었습니다. 프로젝트 참조를 다시 포함하려면 *.csproj* 파일에 다음 줄을 추가하면 됩니다.

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

Visual Studio에서 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **프로젝트 참조 추가** 를 클릭하여 도움을 줄 수도 있습니다. 솔루션에서 프로젝트를 선택하고 **확인** 을 클릭합니다.

![eShop.SqlProvider 프로젝트가 선택된 참조 관리자 대화 상자의 스크린샷](./media/example-migration-core/reference-manager.png)

누락된 프로젝트 참조를 추가하면 애플리케이션이 .NET에서 예상대로 컴파일되고 실행됩니다.

>[!div class="step-by-step"]
>[이전](windows-migration.md)
>[다음](deploy-modern-applications.md)
