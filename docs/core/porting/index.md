---
title: .NET Framework에서 .NET Core로 이식
description: 이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET Core로 이식할 때 유용한 도구에 관해 알아보세요.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: 74fe4519e41a07bc78a4dc346f8d1b52b5c7d092
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502771"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>.NET Framework에서 .NET Core로의 이식 개요

현재 .NET Framework에서 실행되는 코드를 .NET Core로 이식해야 하는 경우가 있습니다. 이 문서에서는 다음을 제공합니다.

* 이식 프로세스 개요
* 코드를 .NET Core로 이식할 때 유용하게 사용할 수 있는 도구 목록

## <a name="overview-of-the-porting-process"></a>포팅 프로세스 개요

여러 프로젝트에 대해 .NET Framework에서 .NET Core(또는 .NET Standard)로 포팅하는 작업은 비교적 간단합니다. 몇 가지 변경이 필요하긴 하나, 대부분 아래에서 설명하는 패턴을 따릅니다. .NET Core에 앱 모델이 있는 프로젝트(라이브러리, 콘솔 앱, 데스크톱 애플리케이션 등)에는 보통 적은 수의 변경만 필요합니다. ASP.NET에서 ASP.NET Core로의 전환과 같이 새로운 앱 모델이 필요한 프로젝트는 비교적 많은 작업이 필요하지만, 전환에서 사용할 수 있는 비슷한 패턴이 다수 존재합니다. 이 문서는 사용자가 코드 기반을 대상 .NET Standard 또는 .NET Core로 성공적으로 변환하는 데 사용한 주요 전략을 식별하는 데 도움이 되며, 두 가지 수준(솔루션 전체와 프로젝트별)에서 변환을 다룹니다. 앱 모델별 변환에 대한 지침은 맨 아래에 있는 링크를 참조하세요.

프로젝트를 .NET Core로 이식할 때는 다음과 같은 프로세스를 사용하는 것이 권장됩니다. 각 단계에서는 동작 변경이 발생할 수 있는 위치가 도입되므로 다음 단계로 넘어가기 전에 라이브러리 또는 애플리케이션을 적절히 테스트하세요. 첫 번째 단계는 .NET Standard 또는 .NET Core로의 전환을 위해 프로젝트를 준비하는 것입니다. 단위 테스트가 있는 경우에는 작업 중인 제품에서 계속해서 변경 사항을 테스트할 수 있도록 단위 테스트를 먼저 변환하는 것이 좋습니다. .NET Core로 이식하면 코드베이스가 많이 변경되기 때문에 코드를 이식할 때 테스트를 실행할 수 있도록 테스트를 이식하는 것이 좋습니다. MSTest, xUnit 및 NUnit은 모두 .NET Core에서 작동합니다.

## <a name="getting-started"></a>시작

다음은 프로세스 전반에서 사용하게 될 도구입니다.

- Visual Studio 2019
- [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) 다운로드
- (선택 사항) [dotnet try-convert](https://github.com/dotnet/try-convert) 설치

## <a name="porting-a-solution"></a>솔루션 이식

솔루션에 여러 프로젝트가 있는 경우에는 프로젝트를 특정 순서에 따라 처리해야 하므로 이식이 더 복잡하게 느껴질 수 있습니다. 변환 프로세스는 솔루션의 다른 프로젝트에 종속되지 않은 프로젝트를 먼저 변환한 후에 전체 솔루션으로 계속 진행하는 상향식 접근 방식이어야 합니다.

프로젝트를 마이그레이션할 순서를 확인하려면 다음과 같은 도구가 필요합니다.

- [Visual Studio의 종속성 다이어그램](/visualstudio/modeling/create-layer-diagrams-from-your-code)을 사용하여 솔루션에 포함된 코드의 방향성 그래프를 만들 수 있습니다.
- `msbuild _SolutionPath_ /t:GenerateRestoreGraphFile /p:RestoreGraphOutputPath=graph.dg.json`을 실행하여 프로젝트 참조 목록을 포함하는 json 문서를 생성합니다.
- `-r DGML` 스위치를 사용해 [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 실행하여 어셈블리의 종속성 다이어그램을 검색합니다. 자세한 내용은 [여기](../../standard/analyzers/portability-analyzer.md#solution-wide-view)를 참조하세요.

종속성 정보를 확보한 후 해당 정보를 사용하여 리프 노드에서 시작하고 종속성 트리 작업을 차근차근 진행하여 다음 섹션의 단계를 적용하는 작업까지 계속 진행할 수 있습니다.

## <a name="per-project-steps"></a>프로젝트 단계별

다음은 프로젝트를 .NET Core로 이식할 때 사용 권장되는 프로세스입니다.

1. [Visual Studio의 변환 도구](/nuget/consume-packages/migrate-packages-config-to-package-reference)를 사용하여 `packages.config` 종속성을 모두 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 형식으로 변환합니다.

   이 단계에서는 종속성을 레거시 `packages.config` 형식에서 변환하는 작업이 이루어집니다. `packages.config`는 .NET Core에서 작동하지 않으므로 패키지 종속성이 있는 경우 이 변환이 필요합니다. 또한 프로젝트에서 직접 사용하는 종속성만 필요하며, 이는 관리해야 하는 종속성의 개수를 줄여 줌으로써 이후 단계를 더 쉽게 만들어 줍니다.

1. 프로젝트 파일을 새로운 SDK 스타일 파일 구조체로 변환합니다. .NET Core를 위한 새 프로젝트를 만들고 소스 파일을 복사하거나 도구를 사용하여 기존 프로젝트 파일의 변환을 시도할 수 있습니다.

   .NET Core는 .NET Framework와 다른 단순화된 [프로젝트 파일 형식](../tools/csproj.md)을 사용합니다. 계속하려면 프로젝트 파일을 이 형식으로 변환해야 합니다. 이 프로젝트 스타일에서는 이 시점에서 아직 대상으로 삼아야 하는 .NET Framework를 대상으로 지정할 수 있도록 지원합니다.

   [dotnet try-convert](https://github.com/dotnet/try-convert) 도구를 사용하여 한 번에 보다 작은 솔루션 또는 개별 프로젝트를 .NET Core 프로젝트 파일 형식으로 이식해 볼 수 있습니다. `dotnet try-convert`가 모든 프로젝트에서 작동한다는 보장은 없으며, 종속성의 대상이 되는 동작이 미묘하게 변경될 수도 있습니다. 이 도구는 자동화가 가능한 기본 항목들을 자동화하기 위한 _‘시작점’_ 으로 사용됩니다. 기존 스타일의 프로젝트 파일에 비해 SDK 스타일 프로젝트에서 사용하는 대상에는 여러 가지 차이점이 있으므로 이것은 프로젝트 마이그레이션을 위해 보장되는 솔루션은 아닙니다.

1. 이식하려는 모든 프로젝트의 대상을 .NET Framework 4.7.2 이상으로 다시 지정합니다.

   이 단계에서는 .NET Core에서 특정 API를 지원하지 않는 경우 .NET Framework 특정 대상에 대한 API 대안을 사용할 수 있도록 합니다.

1. 모든 종속성을 최신 버전으로 업데이트합니다. 프로젝트가 .NET Standard가 지원되지 않는 오래된 버전의 라이브러리를 사용하고 있을 수 있습니다. 하지만 최신 버전에서는 간단한 전환만으로 .NET Standard를 지원할 수 있습니다. 라이브러리에 호환성이 손상되는 변경이 있는 경우 이를 위해 코드 변경이 필요할 수 있습니다.

1. [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)로 어셈블리를 분석하여 .NET Core로 이식 가능한지 확인합니다.

   .NET 이식성 분석기 도구는 컴파일된 어셈블리를 분석하고 보고서를 생성합니다. 이 보고서에서는 개괄적인 이식성 요약과 현재 사용 중인 API 중에서 .NET Core에서 사용할 수 없는 API 각각의 내역을 보여 줍니다. 이 도구를 사용할 때는 잠재적으로 필요한 API 변경 사항에 집중할 수 있도록 변환하는 개별 프로젝트만 제출하세요. 사용자가 전환하려는 .NET Core에서는 대다수의 API가 동일한 가용성을 갖습니다.

   분석기에서 생성한 보고서를 살펴볼 때 중요한 정보는 대상 플랫폼의 지원 백분율이 아니라 사용되고 있는 실제 API입니다. 대다수의 API가 .NET Standard와 Core에서 동일한 옵션을 가지므로 라이브러리 또는 애플리케이션에서 해당 API를 필요로 하는 시나리오를 이해하면 이식의 영향을 확인하는 데 도움이 됩니다.

   API가 동일하지 않아 컴파일러 전처리기 지시문(`#if NET45`)을 통해 플랫폼을 특별 케이스로 처리해야 하는 경우가 있습니다. 지금은 프로젝트가 여전히 .NET Framework를 대상으로 지정하고 있습니다. 대상으로 지정된 각 케이스에 대해 시나리오로 이해될 수 있는 잘 알려진 조건을 사용하는 것이 좋습니다.  예를 들어 .NET Core에서 AppDomain 지원은 제한적이지만 어셈블리의 로드 및 로드 취소 시나리오의 경우 .NET Core에 없는 새로운 API가 있습니다. 코드에서 이를 처리하는 일반적인 방법은 다음과 같습니다.

   ```csharp
   #if FEATURE_APPDOMAIN_LOADING
   // Code that uses appdomains
   #elif FEATURE_ASSEMBLY_LOAD_CONTEXT
   // Code that uses assembly load context
   #else
   #error Unsupported platform
   #endif
   ```

1. [.NET API 분석기](../../standard/analyzers/api-analyzer.md)를 프로젝트에 설치하여 일부 플랫폼에서 <xref:System.PlatformNotSupportedException>을 throw하는 API와 그 밖의 잠재적인 호환성 문제를 식별합니다.

   이 도구는 이식성 분석기와 비슷하나, .NET Core에서 빌드가 가능한지를 분석하는 대신 런타임에 <xref:System.PlatformNotSupportedException>을 throw하는 방식으로 API를 사용하고 있는지 여부를 분석합니다. .NET Framework 4.7.2 이상에서 이식할 때 이 예외가 throw되는 경우는 드물긴 하지만 확인하는 것이 좋습니다. .NET Core에서 예외를 throw하는 API에 대한 자세한 내용은 [.NET Core에서 항상 예외를 throw하는 API](../compatibility/unsupported-apis.md)를 참조하세요.

1. 이 시점에서는 .NET Core(일반적으로 애플리케이션의 경우) 또는 .NET Standard(라이브러리의 경우)로 대상을 전환할 수 있습니다.

   .NET Core와 .NET Standard 중 어느 것을 선택할지는 프로젝트가 어디에서 실행될지에 크게 좌우됩니다. 프로젝트가 다른 애플리케이션에 의해 사용되거나 NuGet을 통해 배포될 라이브러리이면 보통 .NET Standard를 대상으로 지정하는 것이 좋습니다. 그러나 성능이나 그 밖의 이유로 인해 .NET Core에서만 사용 가능한 API가 있을 수 있으며, 이 경우에는 .NET Core를 대상으로 지정하되 성능 또는 기능이 저하된 .NET Standard 빌드도 만드는 것이 좋습니다. .NET Standard를 대상으로 지정하면 프로젝트를 새로운 플랫폼(예: WebAssembly)에서 실행할 준비가 됩니다. 프로젝트가 특정 앱 프레임워크(예: ASP.NET Core)에서 종속성을 갖는 경우 대상은 해당 종속성이 지원하는 것으로 제한됩니다.

   .NET Framework 또는 .NET Standard에 대해 코드를 조건부로 컴파일할 전처리기 지시문이 없는 경우 이것은 프로젝트 파일에서 다음을 찾아서

   ```xml
   <TargetFramework>net472</TargetFramework>
   ```

   원하는 프레임워크로 전환하는 간단한 작업이 됩니다. .NET Core 3.1의 경우에는 다음과 같습니다.

   ```xml
   <TargetFramework>netcoreapp3.1</TargetFramework>
   ```

   그러나 프로젝트가 계속해서 .NET Framework 빌드를 지원해야 하는 라이브러리인 경우 이를 다음으로 바꾸어서 [대상을 여러 개 지정](../../standard/library-guidance/cross-platform-targeting.md)할 수 있습니다.

   ```xml
   <TargetFrameworks>net472;netstandard2.0</TargetFrameworks>
   ```

   Windows 전용 API(예: 레지스트리 액세스)를 사용하는 경우에는 [Windows 호환 기능 팩](./windows-compat-pack.md)을 설치하세요.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [종속성 분석](third-party-deps.md)
> [NuGet 패키지 패키징](../deploying/creating-nuget-packages.md)
> [ASP.NET에서 ASP.NET Core로 마이그레이션](/aspnet/core/migration/proper-to-2x)
