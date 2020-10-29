---
title: .NET Standard
description: .NET Standard, 해당 버전 및 .NET Standard를 지원하는 .NET 구현에 대해 알아봅니다.
ms.date: 10/05/2020
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: a4736e46eb7c25b64278bed8f2c2457002936b81
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224153"
---
# <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard)는 여러 .NET 구현에서 사용할 수 있는 .NET API의 공식 규격입니다. .NET Standard는 .NET 에코시스템의 통일성을 높이기 위한 것이었습니다. 그러나 .NET 5는 균일성을 설정하는 데 다른 접근 방식을 채택하고 있으며 이 새로운 접근 방식은 많은 시나리오에서 .NET Standard가 필요하지 않습니다. 자세한 내용은 이 문서 뒷부분의 [.NET 5 및 .NET Standard](#net-5-and-net-standard)를 참조하세요.

## <a name="net-implementation-support"></a>.NET 구현체 지원

다양한 .NET 구현체는 특정 버전의 .NET Standard를 대상으로 합니다. 각 .NET 구현체 버전은 지원하는 최신 .NET Standard 버전을 보급합니다. 이는 이전 버전도 지원함을 의미합니다. 예를 들어 .NET Framework 4.6에서는 .NET Standard 1.3을 구현합니다. 즉, .NET Standard 버전 1.0에서 1.3까지에 정의된 모든 API를 표시합니다. 마찬가지로 .NET Framework 4.6.1에서는 .NET Standard 1.4를 구현하지만 .NET 5.0에서는 .NET Standard 2.1을 구현합니다.

다음 표에서는 각 .NET Standard 버전을 지원하는 **최소** 구현 버전을 나열합니다. 즉, 목록에 있는 구현의 차후 버전에서는 해당하는 .NET Standard 버전도 지원합니다. 예를 들어 .NET Core 2.1 이상 버전은 .NET Standard 2.0 이전 버전을 지원합니다.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

대상으로 지정할 수 있는 가장 높은 버전의 .NET Standard를 찾으려면 다음 단계를 수행합니다.

1. 실행할 .NET 구현체를 나타내는 행을 찾습니다.
1. 해당 행의 오른쪽에서 왼쪽으로 사용 중인 버전을 나타내는 열을 찾습니다.
1. 열 헤더는 대상에서 지원하는 .NET Standard 버전을 나타냅니다. 더 낮은 .NET Standard 버전을 대상으로 할 수도 있습니다. 더 높은 .NET Standard 버전은 구현체도 지원합니다.
1. 대상으로 지정할 각 플랫폼에 대해 이 프로세스를 반복합니다. 대상 플랫폼이 두 개 이상 있으면 더 낮은 버전을 선택해야 합니다. 예를 들어 .NET Framework 4.8 및 .NET 5.0에서 실행하려는 경우 사용할 수 있는 가장 높은 .NET Standard 버전은 .NET Standard 2.0입니다.

### <a name="which-net-standard-version-to-target"></a>대상으로 지정할 .NET 표준 버전

대상으로 할 .NET Standard 버전을 선택할 때는 다음과 같이 상충되는 요소를 고려해야 합니다.

- 버전이 높을수록 라이브러리의 코드에 더 많은 API를 사용할 수 있습니다.
- 버전이 낮을수록 더 많은 앱과 라이브러리가 라이브러리를 사용할 수 있습니다.

일반적으로 가능한 .NET Standard의 *가장 낮은* 버전을 대상으로 지정하는 것이 좋습니다. 따라서 대상으로 지정할 수 있는 가장 높은 .NET 표준 버전을 찾은 후 다음 단계에 따릅니다.

1. 다음으로 낮은 버전의 .NET 표준을 대상으로 지정하고 프로젝트를 빌드합니다.
2. 프로젝트가 성공적으로 빌드되면 1단계를 반복합니다. 그렇지 않으면 다음으로 높은 버전으로 대상을 변경합니다. 이 버전을 사용해야 합니다.

그러나 하위 .NET Standard 버전을 대상으로 지정하면 많은 지원 종속성이 도입됩니다. 프로젝트에서 .NET 1.x를 대상으로 지정하는 경우에는 .NET Standard 2.0 ‘또한 대상으로 지정’하는 것이 좋습니다. 이렇게 하면 .NET Standard 2.0 호환 구현에서 실행되는 라이브러리의 사용자에 대한 종속성 그래프가 단순화되고 다운로드해야 하는 패키지 수가 감소합니다.

### <a name="net-standard-versioning-rules"></a>.NET 표준 버전 관리 규칙

두 가지 기본 버전 관리 규칙이 있습니다.

- 추가: .NET 표준 버전은 논리적으로 동심원입니다. 더 높은 버전이 이전 버전의 모든 API를 통합합니다. 버전 간에 큰 차이는 없습니다.
- 변경할 수 없음: 제공되고 나면 .NET 표준 버전은 고정됩니다.

2\.1 후에는 새로운 .NET Standard 버전이 없습니다. 자세한 내용은 이 문서 뒷부분의 [.NET 5 및 .NET Standard](#net-5-and-net-standard)를 참조하세요.

## <a name="specification"></a>규격

.NET Standard 규격은 표준화된 API의 집합입니다. 이 규격은 .NET을 구현한 사람, 특히 Microsoft(.NET Framework, .NET Core, Mono 포함)와 Unity에서 유지 관리합니다.

### <a name="official-artifacts"></a>공식 아티팩트

공식 규격은 표준의 일부인 API를 정의하는 *.cs* 파일 세트입니다. [dotnet/standard repository](https://github.com/dotnet/standard)(dotnet/표준 리포지토리)의 [ref directory](https://github.com/dotnet/standard/tree/master/src/netstandard/ref)(ref 디렉터리)는 .NET Standard API를 정의합니다.

[NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) 메타패키지([소스](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props))는 하나 이상의 .NET Standard 버전을 부분적으로 정의하는 라이브러리 집합에 대해 설명합니다.

`System.Runtime` 등의 지정된 구성 요소는 다음에 대해 설명합니다.

- .NET 표준의 일부(해당 범위만)
- 해당 범위에 대한 .NET 표준의 여러 버전

보다 편리하게 읽을 수 있고 특정 개발자 시나리오(예: 컴파일러 사용)를 지원할 수 있도록 파생 아티팩트가 제공됩니다.

- [API list in markdown](https://github.com/dotnet/standard/tree/master/docs/versions)(Markdown의 API 목록)
- NuGet 패키지로 배포되고 [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/) 메타패키지에서 참조되는 참조 어셈블리입니다.

### <a name="package-representation"></a>패키지 표현

.NET Standard 참조 어셈블리의 기본 배포 수단은 NuGet 패키지입니다. 구현체는 각 .NET 구현에 적절한 다양한 방법으로 제공됩니다.

NuGet 패키지는 하나 이상의 [프레임워크](frameworks.md)를 대상으로 합니다. .NET Standard 패키지는 “.NET Standard” 프레임워크를 대상으로 합니다. `netstandard` [압축 TFM](frameworks.md)(예: `netstandard1.4`)을 사용하여 .NET Standard 프레임워크를 대상으로 지정할 수 있습니다. .NET의 여러 구현에서 실행되도록 만들어진 라이브러리는 이 프레임워크를 대상으로 해야 합니다. 광범위한 API의 경우 사용 가능한 API 수가 .NET Standard 1.6과 2.0 간에 세 배 이상 증가하므로 `netstandard2.0`을 대상으로 지정합니다.

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/) 메타패키지는 .NET Standard를 정의하는 NuGet 패키지의 전체 집합을 참조합니다.  `netstandard`를 대상으로 지정하는 가장 일반적인 방법은 이 메타패키지를 참조하는 것입니다. 이 메타패키지는 최대 40개의 .NET 라이브러리 및 .NET 표준을 정의하는 관련 API를 설명하고 액세스할 수 있도록 합니다. 추가 API에 액세스하기 위해 `netstandard`를 대상으로 하는 추가 패키지를 참조할 수 있습니다.

### <a name="versioning"></a>버전 관리

사양은 단수형이 아니라 선형적으로 버전이 지정되는 API 집합입니다. 첫 번째 버전의 표준에서는 API의 기준 집합을 설정합니다. 이후 버전에서는 API를 추가하고 이전 버전에서 정의한 API를 상속받습니다. 표준에서 API 제거와 관련하여 정해진 규정은 없습니다.

.NET Standard는 어느 하나의 .NET 구현에 특정되지 않고, 이러한 구현 중 하나의 버전 관리 체계와 일치하지도 않습니다.

앞에서 설명한 것처럼 2.1 이후에는 새로운 .NET Standard 버전이 없습니다.

## <a name="target-net-standard"></a>.NET Standard 대상 지정

`netstandard` 프레임워크와 `NETStandard.Library` 메타패키지의 조합을 사용하여 [.NET Standard 라이브러리를 빌드](../core/tutorials/libraries.md)할 수 있습니다.

## <a name="net-framework-compatibility-mode"></a>.NET Framework 호환 모드

.NET Standard 2.0부터 .NET Framework 호환성 모드가 도입되었습니다. 이 호환 모드를 사용하면 .NET Standard 프로젝트가 .NET Standard에 컴파일된 것처럼 .NET Framework 라이브러리를 참조할 수 있습니다. .NET Framework 라이브러리를 참조하는 작업은 라이브러리가 WPF(Windows Presentation Foundation) API를 사용하는 것처럼 일부 프로젝트에서 작동하지 않습니다.

자세한 내용은 [.NET Framework 호환 모드](../core/porting/third-party-deps.md#net-framework-compatibility-mode)를 참조하세요.

## <a name="net-standard-libraries-and-visual-studio"></a>.NET Standard 라이브러리 및 Visual Studio

Visual Studio에서 .NET Standard 라이브러리를 빌드하기 위해 Windows에 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 또는 Visual Studio 2017 버전 15.3 이상이 설치되어 있거나 macOS에 [Mac용 Visual Studio 버전 7.1](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) 이상이 설치되어 있는지 확인합니다.

프로젝트에서 .NET Standard 2.0 라이브러리를 사용해야 하는 경우 Visual Studio 2015에서 수행할 수도 있습니다. 그러나 NuGet 클라이언트 3.6 이상을 설치해야 합니다. [NuGet 다운로드](https://www.nuget.org/downloads) 페이지에서 Visual Studio 2015에 대한 NuGet 클라이언트를 다운로드할 수 있습니다.

## <a name="net-5-and-net-standard"></a>.NET 5 및 .NET Standard

.NET 5는 Microsoft에서 적극적으로 개발하고 있는 .NET의 구현입니다. Windows 데스크톱 앱과 크로스 플랫폼 콘솔 앱, 클라우드 서비스 및 웹 사이트에 사용할 수 있는 일관된 기능 및 API 집합을 갖춘 단일 제품입니다. .NET 5.0 [TFM](frameworks.md)은 다음과 같은 광범위한 시나리오를 반영합니다.

* `net5.0`

  이 TFM은 어디서나 실행되는 코드에 대한 것입니다. 몇 가지 예외를 제외하고 플랫폼 간에 작동하는 기술만 포함됩니다. .NET 5 코드의 경우 `net5.0`은 `netcoreapp` 및 `netstandard` TFM을 모두 대체합니다.

* `net5.0-windows`

  이는 `net5.0`이 참조하는 모든 것에 OS별 기능을 추가하는 [OS별 TFM](frameworks.md#net-5-os-specific-tfms)의 예입니다.

### <a name="when-to-target-net50-vs-netstandard"></a>net5.0을 대상으로 하는 경우와 netstandard를 대상으로 하는 경우 비교

`netstandard`를 대상으로 하는 기존 코드의 경우 TFM을 `net5.0`으로 변경할 필요가 없습니다. .NET 5.0은 .NET Standard 2.1 이전 버전을 구현합니다. .NET Standard에서 .NET 5.0으로 대상을 변경하는 유일한 이유는 더 많은 런타임 기능, 언어 기능 또는 API에 대한 액세스 권한을 얻기 위한 것입니다. 예를 들어 C# 9를 사용하려면 .NET 5.0을 대상으로 해야 합니다. .NET 5.0 및 .NET Standard를 다중 대상으로 지정하여 새로운 기능에 액세스할 수 있고 다른 .NET 구현에서 라이브러리를 계속 사용할 수 있습니다.

다음은 .NET 5용 새 코드에 대한 몇 가지 지침입니다.

* 앱 구성 요소

  라이브러리를 사용하여 애플리케이션을 여러 구성 요소로 나누는 경우 `net5.x`를 대상으로 하는 것이 좋습니다. 여기서 `5.x`는 애플리케이션이 대상으로 할 수 있는 가장 빠른 .NET 5 버전입니다. 단순성을 위해 애플리케이션을 구성하는 모든 프로젝트를 동일한 .NET 버전에서 유지하는 것이 가장 좋습니다. 그러면 어디에서나 동일한 BCL 기능을 사용할 수 있습니다.

* 재사용 가능한 라이브러리

  NuGet에 제공하려는 재사용 가능한 라이브러리를 구축하는 경우 도달 범위와 사용 가능한 기능 집합 간의 절충을 고려하세요. .NET Standard 2.0은 .NET Framework에서 지원하는 최신 버전이므로 상당히 큰 기능 집합을 제공합니다. 도달 범위를 최소화하기 위해 사용 가능한 기능 집합을 제한하므로 .NET Standard 1.x를 대상으로 지정하지 않는 것이 좋습니다.

  .NET Framework를 지원할 필요가 없는 경우 .NET Standard 2.1 또는 .NET 5를 사용할 수 있습니다. .NET Standard 2.1을 건너뛰고 바로 .NET 5로 이동하는 것이 좋습니다. 가장 널리 사용되는 라이브러리는 .NET Standard 2.0 및 .NET 5 모두에 대해 다중 대상 지정이 됩니다. .NET Standard 2.0을 지원하면 최대한의 도달 범위를 얻는 반면, .NET 5를 지원하면 이미 .NET 5를 사용하는 고객을 위해 최신 플랫폼 기능을 활용할 수 있습니다.

### <a name="net-standard-problems"></a>.NET Standard 문제

다음은 .NET 5가 왜 플랫폼과 워크로드에서 코드를 공유하는 더 좋은 방법인지를 설명하는 데 도움이 되는 .NET Standard의 몇 가지 문제입니다.

- 새 API 추가의 속도 저하

  .NET Standard는 모든 .NET 구현이 지원해야 하는 API 집합으로 만들어졌기 때문에 새 API 추가를 제안하기 위한 검토 프로세스가 있습니다. 이는 현재 및 미래의 모든 .NET 플랫폼에서 구현할 수 있는 API만 표준화하기 위한 것이었습니다. 그로 인해 기능이 특정 릴리스를 놓친 경우 표준 버전에 추가되기까지 몇 년을 기다려야 할 수도 있습니다. 그런 다음, .NET Standard의 새 버전이 널리 지원되기까지 더 오랜 시간이 걸릴 수 있습니다.

  **.NET 5의 솔루션:** 기능이 구현되면 코드 기반이 공유되기 때문에 모든 .NET 5 앱 및 라이브러리에서 이미 사용할 수 있습니다. 그리고 API 사양과 구현 간에 차이가 없기 때문에 .NET Standard보다 훨씬 빠르게 새로운 기능을 활용할 수 있습니다.

- 복잡한 버전 관리

  API 규격을 구현과 분리하면 API 규격 버전과 구현 버전 간의 매핑이 복잡해집니다. 이러한 복잡성은 이 문서의 앞부분에 나와 있는 표와 해석 방법에 대한 지침에서 분명히 확인할 수 있습니다.

  **.NET 5의 솔루션:** .NET 5.x API 사양과 그 구현 사이에는 분리가 없습니다. 그 결과로 나온 것이 단순화된 TFM 체계입니다. 모든 워크로드에 대해 하나의 TFM 접두사가 있습니다. `net5.0`은 라이브러리, 콘솔 앱 및 웹앱에 사용됩니다. 유일한 변형은 `net5.0-windows`와 같은 특정 플랫폼에 대한 [플랫폼별 API를 지정하는 접미사](frameworks.md#net-5-os-specific-tfms)입니다. 이 TFM 명명 규칙 덕분에 주어진 앱이 주어진 라이브러리를 사용할 수 있는지 쉽게 알 수 있습니다. .NET Standard의 버전 번호와 같은 버전 번호 표가 필요하지 않습니다.

- 런타임 시 플랫폼에서 지원되지 않는 예외

  .NET Standard는 플랫폼별 API를 노출합니다. 코드는 오류 없이 컴파일될 수 있으며 이식 가능하지 않더라도 모든 플랫폼에 이식 가능한 것처럼 보일 수 있습니다. 지정된 API에 대한 구현이 없는 플랫폼에서 실행되면 런타임 오류가 발생합니다.

  **.NET 5의 솔루션:** .NET 5 SDK에는 기본적으로 활성화되는 코드 분석기가 포함되어 있습니다. 플랫폼 호환성 분석기는 실행하려는 플랫폼에서 지원되지 않는 API의 의도하지 않은 사용을 감지합니다. 자세한 내용은 [플랫폼 호환성 분석기](analyzers/platform-compat-analyzer.md)를 참조하세요.

### <a name="net-standard-not-deprecated"></a>.NET Standard 사용되지 않음

.NET Standard는 여러 .NET 구현에서 사용할 수 있는 라이브러리에 계속 필요합니다. 다음 시나리오에서는 .NET Standard를 대상으로 하는 것이 좋습니다.

* `netstandard2.0`을 사용하여 .NET Framework와 기타 .NET의 모든 구현 간에 코드를 공유합니다.
* `netstandard2.1`를 사용하여 Mono, Xamarin 및 .NET Core 3.x 간에 코드를 공유합니다.

## <a name="see-also"></a>참고 항목

- [.NET Standard 버전(소스)](https://github.com/dotnet/standard/blob/master/docs/versions.md)
- [.NET Standard 버전(대화형 UI)](https://dotnet.microsoft.com/platform/dotnet-standard#versions)
- [.NET Standard 라이브러리 빌드](../core/tutorials/library-with-visual-studio.md)
- [플랫폼 간 대상 지정](./library-guidance/cross-platform-targeting.md)
