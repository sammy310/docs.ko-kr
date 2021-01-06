---
title: .NET Core 3.1로의 마이그레이션 예제
description: .NET Framework를 대상으로 하는 샘플 응용 프로그램을 .NET Core 3.1로 마이그레이션하는 방법을 보여 줍니다.
ms.date: 05/12/2020
ms.openlocfilehash: 6a0311e9aaeb25ac39f3394d3a62e17046fe03d8
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "97866655"
---
# <a name="example-of-migrating-to-net-core-31"></a>.NET Core 3.1로의 마이그레이션 예제

이 장에서는 기존 응용 프로그램을 .NET Framework에서 .NET Core로 마이그레이션하는 데 도움이 되는 실용적인 지침을 제공 합니다.

이제는 잘 구성 된 프로세스를 수행 하 고 각 단계에서 고려해 야 할 가장 중요 한 사항을 제공 합니다.

그런 다음 WinForms 및 WPF 버전 둘 다에서 샘플 데스크톱 응용 프로그램에 대 한 단계별 마이그레이션 프로세스를 문서화 합니다.

## <a name="migration-process-overview"></a>마이그레이션 프로세스 개요

마이그레이션 프로세스는 다음과 같은 4 개의 순차적인 단계로 구성 됩니다.

1. **준비**: 프로젝트에 미리 정의 된 종속성을 이해 해야 합니다. 이 단계에서는 현재 프로젝트를 마이그레이션 시작 지점을 간소화 하는 상태로 전환 합니다.

2. **프로젝트 파일 마이그레이션:** .net Core 프로젝트는 새로운 SDK 스타일 프로젝트 형식을 사용 합니다. 이 형식을 사용 하 여 새 프로젝트 파일을 만들거나 SDK 스타일을 사용 해야 하는 프로젝트 파일을 업데이트 합니다.

3. **코드 수정 및 빌드:** .NET Framework와 .NET Core 간의 API 수준 차이를 해결 하는 .NET Core의 코드를 작성 합니다. 필요한 경우 .NET Core를 지 원하는 타사 패키지를 업데이트 합니다.

4. **실행 및 테스트:** 런타임까지 표시 되지 않는 차이점이 있을 수 있습니다. 따라서 응용 프로그램을 실행 하 고 모든 것이 예상 대로 작동 하는지 테스트 해야 합니다.

### <a name="preparation"></a>준비

#### <a name="migrate-packagesconfig-file"></a>packages.config 파일 마이그레이션

.NET Framework 응용 프로그램에서는 외부 패키지에 대 한 모든 참조가 *packages.config* 파일에 선언 됩니다. .NET Core에서는 더 이상 *packages.config* 파일을 사용할 필요가 없습니다. 대신 프로젝트 파일 내에서 [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) 속성을 사용 하 여 앱에 대 한 NuGet 패키지를 지정 합니다.

따라서 한 형식에서 다른 형식으로 전환 해야 합니다. 업데이트를 수동으로 수행 하 고, *packages.config* 파일에 포함 된 종속성을 가져와 형식의 프로젝트 파일로 마이그레이션할 수 있습니다 `PackageReference` . 또는 *packages.config* 파일을 마우스 오른쪽 단추로 클릭 하 고 **PackageReference로 packages.config 마이그레이션** 옵션을 선택 하 여 Visual Studio에서 작업을 수행 하도록 할 수 있습니다.

#### <a name="verify-every-dependency-compatibility-in-net-core"></a>.NET Core의 모든 종속성 호환성 확인

패키지 참조를 마이그레이션한 후에는 각 참조의 호환성을 확인 해야 합니다. 응용 프로그램이 [nuget.org](https://www.nuget.org/)에서 사용 하는 각 NuGet 패키지의 종속성을 탐색할 수 있습니다. 패키지에 .NET Standard 종속성이 있는 경우 .NET core 3.1은 모든 버전의 .NET Standard를 [지원](../../standard/net-standard.md#net-implementation-support) 하기 때문에 .net core에서 작동 합니다. 다음 이미지는 패키지에 대 한 종속성을 보여 줍니다 `Castle.Windsor` .

![Windsor 패키지에 대 한 NuGet 종속성의 스크린샷](./media/example-migration-core/nuget-dependencies.png)

패키지 호환성을 확인 하려면 <https://fuget.org> 버전 및 종속성에 대 한 자세한 정보를 제공 하는 도구를 사용할 수 있습니다.

프로젝트가 .NET Core를 지원 하지 않는 이전 패키지 버전을 참조 하지만 지원 되는 최신 버전을 찾을 수 있습니다. 따라서 패키지를 최신 버전으로 업데이트 하는 것이 일반적으로 좋은 권장 사항입니다. 그러나 패키지 버전을 업데이트 하면 코드를 업데이트 하는 데 적용 되는 몇 가지 주요 변경 사항이 발생할 수 있다는 점을 고려해 야 합니다.

호환 되는 버전을 찾지 못하면 어떻게 되나요? 이러한 주요 변경 내용으로 인해 패키지 버전을 업데이트 하지 않으려는 경우는 어떻게 되나요? .NET Core 응용 프로그램에서 .NET Framework 패키지에 의존할 수 있으므로 걱정할 필요가 없습니다. 외부 패키지가 .NET Core에서 사용할 수 없는 API를 호출 하는 경우 런타임 오류가 발생할 수 있으므로 광범위 하 게 테스트 해야 합니다. 업데이트 하지 않을 이전 패키지를 사용 하 고 .NET Core에서 작업을 대상으로 지정할 수 있는 경우에 유용 합니다.

#### <a name="check-for-api-compatibility"></a>API 호환성 확인

.NET Framework와 .NET Core의 API 화면은 동일 하지만 동일 하지 않기 때문에 .NET Core에서 사용할 수 있는 Api와이 아닌 Api를 확인 해야 합니다. .Net 이식성 분석기 도구를 사용 하 여 .NET Core에 없는 Api를 사용할 수 있습니다. 앱의 이진 수준을 확인 하 고, 호출 되는 모든 Api를 추출한 다음 대상 프레임 워크에서 사용할 수 없는 Api를 나열 합니다 (이 경우 .NET Core 3.1).

이 도구에 대 한 자세한 내용은 다음에서 확인할 수 있습니다.

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

이 도구의 흥미로운 측면은 사용자가 변경할 수 없는 외부 패키지의 코드가 아닌 사용자 고유의 코드에서 발생 하는 차이를 표시 하는 것입니다. 이러한 패키지는 대부분 .NET Core에서 작동 하도록 업데이트 해야 합니다.

### <a name="migrate-project-file"></a>프로젝트 파일 마이그레이션

#### <a name="create-the-new-net-core-project"></a>새 .NET Core 프로젝트 만들기

대부분의 경우 기존 프로젝트를 새 .NET Core 형식으로 업데이트 하는 것이 좋습니다. 그러나 기존 프로젝트를 유지 하면서 새 프로젝트를 만들 수도 있습니다. 이전 프로젝트를 업데이트 하는 경우의 주요 단점은 디자이너 지원이 손실 된다는 것입니다 .이는 사용자에 게 중요할 수 있습니다. 디자이너를 계속 사용 하려는 경우 기존 .NET Core 프로젝트를 사용 하 여 새 .NET Core 프로젝트를 만들고 자산을 공유 해야 합니다. 디자이너에서 UI 요소를 수정 해야 하는 경우 이전 프로젝트로 전환 하 여이 작업을 수행할 수 있습니다. 자산은 연결 되어 있으므로 .NET Core 프로젝트 에서도 업데이트 됩니다.

.NET Core에 대 한 [SDK 스타일 프로젝트](../../core/project-sdk/msbuild-props.md) 는 .NET Framework의 프로젝트 형식 보다 훨씬 더 간단 합니다. 앞에서 언급 한 항목과는 별도로 `PackageReference` 더 많은 작업을 수행할 필요가 없습니다. 새 프로젝트 형식에는 및 파일과 같이 [기본적으로](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects) `.cs` `.xaml` 프로젝트 파일에 명시적으로 포함할 필요 없이 특정 파일 확장명이 포함 됩니다.

#### <a name="assemblyinfo-considerations"></a>Assembly.info 고려 사항

특성은 .NET Core 프로젝트에서 자동으로 생성 됩니다. 프로젝트에 *AssemblyInfo.cs* 파일이 포함 되어 있으면 정의가 중복 되어 컴파일 충돌이 발생 합니다. .NET Core 프로젝트 파일에 다음 항목을 추가 하 여 이전 *AssemblyInfo.cs* 파일을 삭제 하거나 자동 생성을 사용 하지 않도록 설정할 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a>리소스

포함 리소스는 자동으로 포함 되지만 리소스는 아니지만 리소스를 새 프로젝트 파일로 마이그레이션해야 합니다.

#### <a name="package-references"></a>패키지 참조

**PackageReference로 packages.config 마이그레이션** 옵션을 사용 하면 앞에서 설명한 대로 외부 패키지 참조를 새 형식으로 쉽게 이동할 수 있습니다.

#### <a name="update-package-references"></a>패키지 참조 업데이트

이전 섹션에 나와 있는 것 처럼 호환 되는 것으로 확인 된 패키지의 버전을 업데이트 합니다.

### <a name="fix-the-code-and-build"></a>코드 수정 및 빌드

#### <a name="microsoftwindowscompatibility"></a>Microsoft. Windows 호환성

응용 프로그램이 레지스트리, Acl 또는 WCF와 같이 .NET Core에서 사용할 수 없는 Api를 사용 하는 경우 `Microsoft.Windows.Compatibility` 이러한 Windows 관련 api를 추가 하려면 패키지에 대 한 참조를 포함 해야 합니다. 이러한 도구는 .NET Core에서 작동 하지만 플랫폼 간에는 포함 되지 않습니다.

<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>코드와 호환 되지 않는 api를 식별 하는 데 도움이 되는 Api Analyzer () 라는 도구가 있습니다.

#### <a name="use-if-directives"></a>\#If 지시문 사용

.NET Framework 및 .NET Core를 대상으로 지정 하는 경우 다른 실행 경로가 필요한 경우 컴파일 상수를 사용 해야 합니다. 일부 \# if 지시문을 코드에 추가 하 여 두 대상에 대해 동일한 코드 베이스를 유지 합니다.

#### <a name="technologies-not-available-on-net-core"></a>.NET Core에서 사용할 수 없는 기술

다음과 같은 일부 기술은 .NET Core에서 사용할 수 없습니다.

* AppDomain
* 원격 통신
* 코드 액세스 보안
* WCF 서버
* Windows 워크플로

이러한 이유로 응용 프로그램에서 사용 하는 경우 이러한 기술을 대체 해야 합니다. 자세한 내용은 [.Net Core에서 사용할 수 없는 .NET Framework 기술](../../core/porting/net-framework-tech-unavailable.md) 문서를 참조 하세요.

#### <a name="regenerate-autogenerated-clients"></a>자동 생성 클라이언트 다시 생성

응용 프로그램에서 WCF 클라이언트와 같은 자동 생성 된 코드를 사용 하는 경우 .NET Core를 대상으로 하기 위해이 코드를 다시 생성 해야 할 수 있습니다. 경우에 따라 일부 누락 된 참조는 기본 .NET Core 어셈블리 집합의 일부로 포함 되지 않을 수 있기 때문에 찾을 수 있습니다. 와 같은 도구를 사용 하 여 <https://apisof.net/> 누락 된 참조가 상주 하는 어셈블리를 쉽게 찾아 NuGet에서 추가할 수 있습니다.

#### <a name="rolling-back-package-versions"></a>패키지 버전 롤백

일반적으로 .NET Core와 호환 되도록 모든 단일 패키지 버전을 더 잘 업데이트 한다고 이미 설명 했습니다. 그러나 어셈블리의 업데이트 된 버전과 호환 되는 버전을 대상으로 하는 것을 찾을 수 있습니다. 변경 비용이 허용 되지 않는 경우 .NET Framework에서 사용 하는 패키지 버전을 롤백하는 것을 고려할 수 있습니다. .NET Core를 대상으로 하지 않을 수도 있지만 지원 되지 않는 일부 Api를 호출 하지 않는 한 잘 작동 해야 합니다.

### <a name="run-and-test"></a>실행 및 테스트

응용 프로그램 빌드에 오류가 발생 하지 않으면 모든 기능을 테스트 하 여 마이그레이션의 마지막 단계를 시작할 수 있습니다.

이 마지막 단계에서는 응용 프로그램의 복잡성과 사용 중인 종속성 및 Api에 따라 여러 가지 문제를 찾을 수 있습니다.

예를 들어 구성 파일 (*app.config*)을 사용 하는 경우 구성 섹션과 같이 런타임에 몇 가지 오류가 발생할 수 있습니다. NuGet 패키지를 사용 하면 `Microsoft.Extensions.Configuration` 이 오류를 해결 해야 합니다.

오류가 발생 하는 또 다른 이유는 `BeginInvoke` `EndInvoke` .net Core에서 지원 되지 않기 때문에 및 메서드를 사용 하는 것입니다. .Net core에는 존재 하지 않는 원격 기능에 종속 되어 있기 때문에 .NET Core에서는 지원 되지 않습니다. 이 문제를 해결 하려면 `await` 키워드 (사용 가능한 경우) 또는 메서드를 사용 하십시오 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> .

호환성 분석기를 사용 하 여 코드에서 .NET Core로 런타임에 문제를 일으킬 수 있는 Api 및 코드 패턴을 식별할 수 있습니다. 로 이동 하 여 <https://github.com/dotnet/platform-compat> 프로젝트에서 .NET API analyzer를 사용 합니다.

## <a name="migrating-a-windows-forms-application"></a>Windows Forms 응용 프로그램 마이그레이션

Windows Forms 응용 프로그램의 전체 마이그레이션 프로세스를 소개 하기 위해에서 사용할 수 있는 eShop 샘플 응용 프로그램을 마이그레이션하도록 선택 했습니다 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> . 에서 마이그레이션의 전체 결과를 찾을 수 있습니다 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .

이 응용 프로그램은 제품 카탈로그를 표시 하 고 사용자가 제품을 탐색, 필터링 및 검색할 수 있도록 합니다. 아키텍처 관점에서 앱은 백 엔드 데이터베이스에 대 한 외관 역할을 하는 외부 WCF 서비스에 의존 합니다.

다음 그림에서 주 응용 프로그램 창을 볼 수 있습니다.

![주 응용 프로그램 창](./media/example-migration-core/main-application-window.png)

*.Csproj* 프로젝트 파일을 여는 경우 다음과 같은 내용이 표시 될 수 있습니다.

![.Csproj 파일 내용의 스크린샷](./media/example-migration-core/csproj-file.png)

앞에서 설명한 것 처럼 .NET Core 프로젝트에는 더 간결한 스타일이 있으며 프로젝트 구조를 새 .NET Core SDK 스타일로 마이그레이션해야 합니다.

솔루션 탐색기에서 Windows Forms 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 언로드**  >  **편집** 을 선택 합니다.

이제 .csproj 파일을 업데이트할 수 있습니다. 전체 콘텐츠를 삭제 하 고 다음 코드로 바꿉니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

프로젝트를 저장 하 고 다시 로드 합니다. 이제 프로젝트 파일 업데이트가 완료 되었으며 프로젝트가 .NET Core를 대상으로 합니다.

이 시점에서 프로젝트를 컴파일하면 WCF 클라이언트 참조와 관련 된 몇 가지 오류가 발견 됩니다. 이 코드는 자동으로 생성 되므로 .NET Core를 대상으로 다시 생성 해야 합니다.

![Visual Studio의 컴파일 오류 스크린샷](./media/example-migration-core/winforms-compilation-errors.png)

*Reference.cs* 파일을 삭제 하 고 새 서비스 클라이언트를 생성 합니다.

**연결된 서비스** 를 마우스 오른쪽 단추로 클릭 하 고 **연결 된 서비스 추가** 옵션을 선택 합니다.

![연결 된 서비스 추가 옵션이 선택 된 연결된 서비스 메뉴의 스크린샷](./media/example-migration-core/add-connected-service.png)

연결된 서비스 창이 열립니다. **MICROSOFT WCF 웹 서비스** 옵션을 선택 합니다.

![연결된 서비스 창의 스크린샷](./media/example-migration-core/connected-services-window.png)

이 예제와 동일한 솔루션에 WCF 서비스가 있는 경우 서비스 URL을 지정 하는 대신 **검색** 옵션을 선택할 수 있습니다.

![WCF 웹 서비스 참조 구성 창의 스크린샷](./media/example-migration-core/configure-wcf-reference.png)

서비스가 있으면이 도구는 서비스에 의해 구현 된 API 계약을 반영 합니다. 다음 이미지와 같이 네임 스페이스의 이름을로 변경 합니다 `eShopServiceReference` .

![API 계약 및 네임 스페이스 변경 된 스크린 샷](./media/example-migration-core/api-contract-namespace.png)

**마침** 단추를 선택 합니다. 잠시 후 생성 된 코드를 볼 수 있습니다.

세 개의 자동 생성 파일이 표시 됩니다.

1. *시작*: WCF에 대 한 일부 정보를 제공 하는 GitHub에 대 한 링크입니다.
2. *ConnectedService.json*: 서비스에 연결할 구성 매개 변수입니다.
3. *Reference.cs*: 실제 WCF 클라이언트 코드입니다.

![세 개의 자동 생성 파일을 사용 하는 솔루션 탐색기 창의 스크린샷](./media/example-migration-core/autogenerated-files.png)

다시 컴파일하는 경우에는 해당 *도우미* 폴더 내의 *.cs* 파일에서 발생 하는 많은 오류가 표시 됩니다. 이 폴더는 .NET Framework 버전에 있지만 이전 *.csproj* 에는 포함 되어 있지 않습니다. 그러나 새 SDK 스타일 프로젝트를 사용 하면 프로젝트 파일 위치 아래에 있는 모든 코드 파일이 기본적으로 포함 됩니다. 즉, 새 .NET Core 프로젝트는 *도우미* 폴더 내에서 파일을 컴파일하도록 시도 합니다. 해당 폴더가 필요 하지 않으므로 안전 하 게 삭제할 수 있습니다.

프로젝트를 다시 컴파일하여 실행 하면 제품 이미지가 표시 되지 않습니다. 문제는 이제 파일 경로가 약간 변경 되었다는 것입니다. 이 문제를 해결 하려면 경로에 다른 수준의 깊이를 추가 하 여 파일의 줄을 업데이트 해야 합니다 `CatalogView.cs` .

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

다음으로 변경:

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

이렇게 변경한 후에는 응용 프로그램이 시작 되 고 .NET Core에서 예상 대로 실행 되는지 확인할 수 있습니다.

## <a name="migrating-a-wpf-application"></a>WPF 응용 프로그램 마이그레이션

`Shop.ClassicWPF`예제 응용 프로그램을 사용 하 여 마이그레이션을 수행 합니다. 다음 이미지는 마이그레이션 전의 앱 스크린샷을 보여 줍니다.

![마이그레이션 전의 샘플 앱](./media/example-migration-core/app-before-migration.png)

이 응용 프로그램은 로컬 SQL Server Express 데이터베이스를 사용 하 여 제품 카탈로그 정보를 저장 합니다. 이 데이터베이스는 WPF 응용 프로그램에서 직접 액세스할 수 있습니다.

먼저 *.csproj* 파일을 .net Core 응용 프로그램에서 사용 하는 새 SDK 스타일로 업데이트 해야 합니다. Windows Forms 마이그레이션에 설명 된 것과 동일한 단계를 따릅니다. 프로젝트를 언로드하고 *.csproj* 파일을 열고 콘텐츠를 업데이트 하 고 프로젝트를 다시 로드 합니다.

이 경우 *.csproj* 파일의 내용을 모두 삭제 하 고 다음 코드로 바꿉니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWpf>true</UseWpf>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

프로젝트를 다시 로드 하 고 컴파일하면 다음과 같은 오류가 발생 합니다.

![Visual Studio의 컴파일 오류 스크린샷](./media/example-migration-core/wpf-compilation-error.png)

*.Csproj* 콘텐츠를 모두 삭제 했기 때문에 이전 프로젝트에 존재 하는 프로젝트 참조 사양이 손실 되었습니다. 프로젝트 참조를 다시 포함 하려면 .csproj 파일에이 줄을 추가 하기만 하면 *됩니다* .

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

**종속성** 노드를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 참조 추가** 를 선택 하 여 Visual Studio에서 도움을 줄 수도 있습니다. 솔루션에서 프로젝트를 선택 하 고 **확인을** 클릭 합니다.

![EShop. SqlProvider 프로젝트가 선택 된 참조 관리자 대화 상자의 스크린샷](./media/example-migration-core/reference-manager.png)

누락 된 프로젝트 참조를 추가 하면 응용 프로그램은 .NET Core에서 정상적으로 컴파일되고 실행 됩니다.

>[!div class="step-by-step"]
>[이전](windows-migration.md)
>[다음](deploy-modern-applications.md)
