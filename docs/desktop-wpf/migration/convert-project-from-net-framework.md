---
title: WPF 앱을 .NET Core 3.0으로 마이그레이션
description: WPF(Windows Presentation Foundation) 앱을 .NET Core 3.0으로 마이그레이션하는 방법을 알아봅니다.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: fda4f618ddb4a3edbe6f2dd9fba0b10bc618e88d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201568"
---
# <a name="migrating-wpf-apps-to-net-core"></a>WPF 앱을 .NET Core로 마이그레이션

이 문서에서는 WPF(Windows Presentation Foundation) 앱을 .NET Framework에서 .NET Core 3.0으로 마이그레이션하는 데 필요한 단계를 설명합니다. 이식할 WPF 앱이 없지만 프로세스를 시도해보려면 [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader)에 제공되는 **Bean Trader** 샘플 앱을 사용하면 됩니다. 원래 앱(.NET Framework 4.7.2 대상)은 NetFx\BeanTraderClient 폴더에 있습니다. 먼저 앱을 이식하는 데 필요한 일반인 단계를 설명한 다음, **Bean Trader** 샘플에 적용되는 특정한 변경 사항을 살펴보겠습니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

.NET Core로 마이그레이션하려면 먼저 다음을 수행해야 합니다.

01. NuGet 종속성 이해 및 업데이트:

    01. `<PackageReference>` 형식을 사용하도록 NuGet 종속성을 업그레이드합니다.
    01. .NET Core 또는 .NET Standard 호환성에 대한 최상위 NuGet 종속성을 검토합니다.
    01. NuGet 패키지를 최신 버전으로 업그레이드합니다.
    01. [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 사용하여 .NET 종속성을 이해합니다.

01. 프로젝트 파일을 새로운 SDK 스타일 형식으로 마이그레이션:

    01. .NET Core와 .NET Framework 모두를 대상으로 할지, 아니면 .NET Core만 대상으로 할지 선택합니다.
    01. 관련 프로젝트 파일 속성 및 항목을 새 프로젝트 파일에 복사합니다.

01. 빌드 문제 해결:

    01. [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) 패키지에 대한 참조를 추가합니다.
    01. API 수준의 차이를 찾아서 수정합니다.
    01. `appSettings` 또는 `connectionStrings`가 아닌 *app.config* 섹션을 제거합니다.
    01. 필요한 경우 생성된 코드를 다시 생성합니다.

01. 런타임 테스트:

    01. 이식된 앱이 예상대로 작동하는지 확인합니다.
    01. <xref:System.NotSupportedException> 예외에 유의합니다.

## <a name="about-the-sample"></a>샘플 정보

이 문서에서는 [Bean Trader 샘플 앱](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader)을 참조합니다. 이 앱에는 실제 WPF 앱에 사용되는 종속성과 유사한 종속성이 다양하게 사용되기 때문입니다. 이 앱은 크지 않지만 복잡성 측면에서 'Hello World'에서 한 단계 업그레이드된 앱입니다. 이 앱은 실제 앱을 이식하는 동안 발생할 수 있는 몇 가지 문제를 보여줍니다. 이 앱은 WCF 서비스와 통신하기 때문에 제대로 실행되려면, BeanTraderServer 프로젝트(동일한 GitHub 리포지토리에서 사용 가능)를 실행하고 BeanTraderClient 구성이 올바른 엔드포인트를 가리키도록 해야 합니다. (기본적으로 이 샘플은 서버가 `http://localhost:8090`의 동일한 컴퓨터에서 실행되는 것으로 가정하며, BeanTraderServer를 로컬에서 시작하면 동일한 상황이 됩니다.)

이 샘플 앱으로 .NET Core 이식의 어려움과 솔루션을 시연할 예정입니다. WPF 모범 사례를 시연하려는 것은 아닙니다. 사실은, 이식하는 동안 적어도 몇 가지 흥미로운 문제가 발생할 수 있도록 몇 가지 안티 패턴이 의도적으로 포함되어 있습니다.

## <a name="getting-ready"></a>준비

.NET Framework 앱을 .NET Core로 마이그레이션하는 경우 주된 문제는, 종속성이 다르게 작동하거나 전혀 작동하지 않을 수 있다는 것입니다. 마이그레이션은 이전보다 훨씬 더 쉬워졌고 이제 많은 NuGet 패키지가 .NET Standard를 대상으로 합니다. .NET Core 2.0부터는 .NET Framework와 .NET Core의 노출 영역이 비슷해졌습니다. 그래도 몇 가지 차이점(NuGet 패키지의 지원 및 사용 가능한 .NET API)이 있습니다. 마이그레이션의 첫 단계는 앱의 종속성을 검토하고 참조가 .NET Core로 쉽게 마이그레이션되는 형식인지 확인하는 것입니다.

### <a name="upgrade-to-packagereference-nuget-references"></a>`<PackageReference>` NuGet 참조로 업그레이드

이전 .NET Framework 프로젝트는 NuGet 종속성이 일반적으로 *packages.config* 파일에 나열됩니다. 새로운 SDK 스타일 프로젝트 파일 형식은 NuGet 패키지를 별도의 구성 파일이 아닌 csproj 파일 자체의 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 요소로 참조합니다.

마이그레이션할 때 `<PackageReference>` 스타일 참조를 사용하면 두 가지 이점이 있습니다.

- 이 스타일은 새 .NET Core 프로젝트 파일에 필요한 NuGet 참조 스타일입니다. `<PackageReference>`를 이미 사용하고 있으면, 해당 프로젝트 파일 요소를 복사하여 새 프로젝트에 바로 붙여넣을 수 있습니다.
- packages.config 파일과 달리 `<PackageReference>` 요소는 프로젝트가 직접 종속된 최상위 종속성만 참조합니다. 다른 모든 전이적 NuGet 패키지는 복원 시 결정되며 자동 생성된 obj\project.assets.json 파일에 기록됩니다. 따라서, 프로젝트의 종속성을 훨씬 더 쉽게 확인할 수 있기 때문에 필요한 종속성이 .NET Core에서 작동할지 여부를 확인할 때 유용합니다.

.NET Framework 앱을 .NET Core로 마이그레이션하는 첫 번째 단계는 `<PackageReference>` NuGet 참조를 사용하도록 업데이트하는 것입니다. Visual Studio를 사용하면 간단합니다. Visual Studio의 **솔루션 탐색기**에서 프로젝트의 *packages.config* 파일을 마우스 오른쪽 단추로 클릭한 다음, **packages.config를 PackageReference로 마이그레이션**을 선택하면 됩니다.

![PackageReference로 업그레이드](./media/convert-project-from-net-framework/package-reference-migration.png)

계산된 최상위 NuGet 종속성을 보여주는 대화 상자가 나타나고, 다른 어떤 NuGet 패키지를 최상위 수준으로 승격해야 하는지 묻는 메시지가 표시됩니다. 다른 패키지 중에 Bean Trader 샘플의 최상위 수준으로 승격해야 하는 패키지가 없으므로, 해당 확인란의 선택을 모두 취소하면 됩니다. 그런 다음, **Ok**을 클릭하면 *packages.config* 파일이 제거되고 `<PackageReference>` 요소가 프로젝트 파일에 추가됩니다.

`<PackageReference>` 스타일 참조는 NuGet 패키지를 로컬 패키지 폴더에 저장하지 않습니다. 대신, 최적화로 전역적으로 저장됩니다. 마이그레이션이 완료되면 csproj 파일을 편집하고 이전에 *..\packages* 디렉터리에서 가져온 분석기를 참조하는 `<Analyzer>` 요소를 제거합니다. 그래도 NuGet 패키지 참조가 아직 있기 때문에 분석기는 프로젝트에 포함됩니다. 이전 packages.config 스타일 `<Analyzer>` 요소만 정리하면 됩니다.

### <a name="review-nuget-packages"></a>NuGet 패키지 검토

이제 프로젝트가 종속된 최상위 NuGet 패키지를 볼 수 있으므로, .NET Core에서 해당 패키지를 사용할 수 있는지 여부를 검토할 수 있습니다. [nuget.org](https://www.nuget.org/)에 대한 종속성을 살펴보고 패키지가 .NET Core를 지원하는지 여부를 확인할 수 있습니다. 커뮤니티에서 만든 [fuget.org](https://www.fuget.org/) 사이트에는 이 정보가 패키지 정보 페이지 맨 위에 두드러지게 표시됩니다.

.NET Core 3.0을 대상으로 하는 경우 .NET Core 또는 .NET Standard를 대상으로 하는 모든 패키지가 작동해야 합니다. (.NET Core는 .NET Standard 노출 영역을 구현하기 때문입니다.) 사용되는 특정 버전의 패키지는 .NET Core나 .NET Standard를 대상으로 하지 않지만 최신 버전은 대상으로 하는 경우가 있습니다. 이런 경우에는 최신 버전의 패키지로 업그레이드하는 것이 좋습니다.

.NET Framework를 대상으로 하는 패키지도 사용할 수 있지만 약간의 위험이 있습니다. .NET Core와 .NET Framework 노출 영역은 종속성이 대체로 작동할 만큼 유사하기 때문에, .NET Core에서 .NET Framework로 종속성은 허용됩니다. 하지만, 패키지가 .NET Core에 없는 .NET API를 사용하려고 하면 런타임 예외가 발생합니다. 따라서 다른 옵션이 없는 경우에만 .NET Framework 패키지를 참조해야 하며 이렇게 하면 테스트 부담이 발생한다는 것을 이해해야 합니다.

.NET Core나 .NET Standard를 대상으로 하지 않는 패키지가 참조된 경우에는 다른 대안을 고려해야 합니다.

- 대신 사용할 수 있는 다른 유사한 패키지가 있나요? NuGet 작성자가 특히 .NET Core를 대상으로 하는 별도의 '.Core' 버전 라이브러리를 게시하는 경우가 있습니다. 엔터프라이즈 라이브러리 패키지는 커뮤니티 게시 ".NetCore" 대안의 예입니다. 다른 경우에는 특정 서비스에 대한 최신 SDK를(때로는 다른 패키지 이름으로) .NET Standard에 사용할 수 있습니다. 대안이 없으면 .NET Framework 대상 패키지를 계속 사용할 수 있습니다. 다만, .NET Core에서 실행한 후에는 철저한 테스트가 필요하다는 점에 유의해야 합니다.

Bean Trader 샘플에 있는 최상위 NuGet 종속성은 다음과 같습니다.

- [**Castle.Windsor, 버전 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  이 패키지는 .NET Standard 1.6을 대상으로 하므로 .NET Core에서 작동합니다.

- [**Microsoft.CodeAnalysis.FxCopAnalyzers, 버전 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  메타 패키지이므로 어떤 플랫폼을 지원하는지가 즉시 분명하지는 않지만, 최신 버전(2.9.2)이 .NET Framework와 .NET Core 모두에서 작동한다는 내용이 [설명서](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers)에 나와 있습니다.

- [**Nito.AsyncEx, 버전 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  이 패키지는 .NET Core를 대상으로 하지 않지만 최신 5.0 버전은 대상으로 합니다. 최근 많은 NuGet 패키지에 .NET Standard 지원이 추가되었지만 이전 프로젝트 버전은 .NET Framework만 대상으로 하기 때문에, 마이그레이션하는 경우 일반적입니다. 버전 차이가 작으면 최신 버전으로 업그레이드하기 쉬운 경우가 많습니다. 이 경우에는 버전 차이가 크기 때문에 패키지에 호환성이 손상되는 변경이 있을 수 있으므로 주의하여 업그레이드해야 합니다. 하지만 방법이 있으므로 가능합니다.

- [**MahApps.Metro, 버전 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  이 패키지도 .NET Core를 대상으로 하지 않지만 최신 시험판(2.0-alpha)은 대상으로 합니다. 역시, 호환성이 손상되는 변경이 있는지 확인해야 하지만, 최신 패키지를 사용하는 것이 좋습니다.

Bean Trader 샘플의 NuGet 종속성은 모두 .NET Standard/.NET Core를 대상으로 하거나, 이것을 대상으로 하는 최신 버전이 있습니다. 따라서 차단 문제가 있을 가능성은 거의 없습니다.

### <a name="upgrade-nuget-packages"></a>NuGet 패키지 업그레이드

가능하면, .NET Core나 .NET Standard만 대상으로 하는 패키지 버전을 이 시점(프로젝트가 아직 .NET Framework를 대상으로 하는)에 최신 버전으로 업그레이드하여 호환성이 손상되는 변경이 있으면 초기에 찾아서 처리하는 것이 좋습니다.

기존 .NET Framework 버전의 앱을 실질적으로 변경하지 않으려면, .NET Core를 대상으로 하는 새 프로젝트 파일이 준비될 때까지 연기할 수 있습니다. 하지만 NuGet 패키지를 .NET Core 호환 버전으로 미리 업그레이드하고 새 프로젝트 파일을 만들면 마이그레이션 프로세스가 훨씬 더 쉬워지고, .NET Framework 버전과 .NET Core 버전 앱의 차이가 줄어듭니다.

Bean Trader 샘플을 사용하면, 필요한 모든 업그레이드를 쉽게 수행할 수 있지만(Visual Studio의 NuGet 패키지 관리자를 사용하여) 한 가지 예외가 있습니다. **MahApps.Metro 1.6.5**에서 **2.0**으로 업그레이드하면 테마 및 강조 관리 API와 관련하여 호환성이 손상되는 변경이 드러납니다.

앱이 최신 버전의 패키지를 사용하도록 업데이트되는 것이 가장 좋습니다(.NET Core에서 작동할 가능성이 높기 때문). 하지만 이 방법이 적합하지 않은 경우도 있습니다. 이러한 경우 **MahApps.Metro**를 업그레이드하지 마십시오. 필요한 변경 사항이 사소하지 않으며, 이 자습서는 **MahApps.Metro 2.** 가 아닌 .NET Core 3으로 마이그레이션하는 데 중점을 두고 있기 때문입니다. 또한 Bean Trader 앱은 **MahApps.Metro**의 작은 부분만 실행하기 때문에 위험 수준이 낮은 .NET Framework 종속성입니다. 물론 마이그레이션이 완료되면 모든 것이 제대로 작동하는지 확인하는 테스트가 필요합니다. 실제 시나리오인 경우 마이그레이션을 수행하지 않으면 기술적인 문제를 남기기 때문에 **MahApps.Metro** 버전 2.0으로 이동하는 작업을 추적하는 문제를 제기하는 것이 좋습니다.

NuGet 패키지가 최신 버전으로 업데이트되면 Bean Trader 샘플 프로젝트 파일의 `<PackageReference>` 항목 그룹은 다음과 같은 모양입니다.

```xml
<ItemGroup>
  <PackageReference Include="Castle.Windsor">
    <Version>4.1.1</Version>
  </PackageReference>
  <PackageReference Include="MahApps.Metro">
    <Version>1.6.5</Version>
  </PackageReference>
  <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers">
    <Version>2.9.2</Version>
  </PackageReference>
  <PackageReference Include="Nito.AsyncEx">
    <Version>5.0.0</Version>
  </PackageReference>
</ItemGroup>
```

### <a name="net-framework-portability-analysis"></a>.NET Framework 이식성 분석

프로젝트의 NuGet 종속성 상태를 이해했으면, 다음으로 고려할 사항은 .NET Framework API 종속성입니다. [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) 도구는 프로젝트에 사용되는 .NET API 중 어떤 API를 다른 .NET 플랫폼에서 사용할 수 있는지 파악하는 데 유용합니다.

이 도구는 [Visual Studio 플러그인](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), [명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases)로 제공되거나 [간단한 GUI](https://github.com/Microsoft/dotnet-apiport-ui)로 래핑되어 옵션을 간소화합니다. GUI를 사용하여 .NET 이식성 분석기(API 포트)를 사용하는 방법에 대한 자세한 내용은 [Porting desktop apps to .NET Core](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/)(데스크톱 앱을 .NET Core로 이식) 블로그 게시물을 참조하세요. 명령줄을 사용하려는 경우 필요한 단계는 다음과 같습니다.

1. [.NET 이식성 분석기](https://github.com/Microsoft/dotnet-apiport/releases)가 아직 없으면 다운로드합니다.
1. 이식할 .NET Framework 앱이 성공적으로 빌드되었는지 확인합니다. (마이그레이션하기 전에 수행하는 것이 좋습니다.)
1. 아래와 같은 명령줄을 사용하여 API 포트를 실행합니다.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    `-f` 인수는 분석할 이진이 포함된 경로를 지정합니다. `-r` 인수는 원하는 출력 파일 형식을 지정합니다. `-t` 인수는 API 사용을 분석할 .NET 플랫폼을 지정합니다. 이 경우에는 .NET Core가 필요합니다.

HTML 보고서를 열면 첫 번째 섹션에는 분석된 모든 이진과 대상 플랫폼에서 사용할 수 있는 .NET API의 백분율이 나열됩니다. 백분율 자체로는 의미가 없습니다. 누락된 특정 API를 보는 것이 더 유용합니다. 이렇게 하려면 어셈블리 이름을 선택하거나 개별 어셈블리에 대한 보고서까지 아래로 스크롤합니다.

소스 코드를 소유하는 어셈블리에 중점을 둡니다. 예를 들어 Bean Trader ApiPort 보고서에는 많은 이진이 나열되지만 대부분이 NuGet 패키지에 속합니다. `Castle.Windsor`는 .NET Core에 없는 몇 가지 System.Web API에 종속된 것으로 나타납니다. 이 점은 `Castle.Windsor`가 .NET Core를 지원한다는 것을 이전에 확인했으므로 문제가 되지 않습니다. NuGet 패키지에는 다양한 .NET 플랫폼에 사용할 서로 다른 이진이 있는 것이 일반적입니다. 따라서 패키지가 .NET Standard나 .NET Core(이 경우 대상임)를 대상으로 하는 한 `Castle.Windsor`의 .NET Framework 버전이 System.Web API를 사용하는지 여부는 상관이 없습니다.

Bean Trader 샘플에서 고려해야 하는 유일한 이진은 **BeanTraderClient**이며 보고서에는 두 가지 .NET API 즉, `System.ServiceModel.ClientBase<T>.Close` 및 `System.ServiceModel.ClientBase<T>.Open`만 없는 것으로 표시됩니다.

![BeanTraderClient 이식성 보고서](./media/convert-project-from-net-framework/portability-report.png)

WCF 클라이언트 API는 .NET Core에서 (대부분) 지원되기 때문에 차단 문제가 발생할 가능성이 낮습니다. 따라서 중앙 API에 사용 가능한 대안이 있어야 합니다. 실제로 `System.ServiceModel`의 .NET Core 노출 영역(<https://apisof.net> 사용)을 살펴보면, .NET Core에 비동기 대안이 있는 것을 알 수 있습니다.

이 보고서와 이전 NuGet 종속성 분석에 기반하면, Bean Trader 샘플을 .NET Core로 마이그레이션하는 데 큰 문제가 없는 것으로 보입니다. 실제로 마이그레이션을 시작하는 다음 단계를 수행할 준비가 되었습니다.

## <a name="migrating-the-project-file"></a>프로젝트 파일 마이그레이션

앱에 새로운 [SDK 스타일 프로젝트 파일 형식](../../core/tools/csproj.md)이 사용되지 않으면 .NET Core를 대상으로 하는 새 프로젝트 파일이 필요합니다. 기존 csproj 파일을 교체하거나, 기존 프로젝트를 현재 상태에서 그대로 유지하려면 .NET Core를 대상으로 하는 새 csproj 파일을 추가하면 됩니다. [멀티 타기팅](../../standard/library-guidance/cross-platform-targeting.md)(여러 `<TargetFrameworks>` 대상 지정)이 포함된 단일 SDK 스타일 프로젝트 파일을 사용하여 .NET Framework와 .NET Core용 앱 버전을 빌드할 수 있습니다.

새 프로젝트 파일을 만들려면 Visual Studio에서 새 WPF 프로젝트를 만들거나, 임시 디렉터리에서 `dotnet new wpf` 명령을 사용하여 프로젝트 파일을 만든 다음, 올바른 위치로 복사하고 이름을 변경하면 됩니다. 커뮤니티에서 만든 도구인 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017)도 있으며, 프로젝트 파일 마이그레이션의 일부를 자동화할 수 있습니다. 이 도구는 유용하지만 그래도 사람이 결과를 검토하여 마이그레이션의 모든 세부 사항이 올바른지 확인해야 합니다. 이 도구가 최적으로 처리하지 못하는 한 가지 영역은 *packages.config* 파일에서 NuGet 패키지를 마이그레이션하는 것입니다. *packages.config* 파일을 사용하여 NuGet 패키지를 참조하는 프로젝트 파일에서 도구를 실행하면, `<PackageReference>` 요소로 자동 마이그레이션되지만 최상위 패키지뿐만 아니라 모든 패키지에 대해 `<PackageReference>` 요소가 추가됩니다. Visual Studio를 사용하여 `<PackageReference>` 요소로 이미 마이그레이션한 경우에는(이 샘플에서 수행한 것처럼), 이 도구가 나머지 변환에 유용할 수 있습니다. Scott Hanselman이 [csproj 파일 마이그레이션에 대한 블로그 게시물](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx)에서 권장하듯이, 수동으로 이식하면 교육적이며 이식할 프로젝트가 적다면 더 나은 결과를 얻을 수 있습니다. 하지만 수십 또는 수백 개의 프로젝트 파일을 이식하는 경우에는 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017)과 같은 도구가 유용할 수 있습니다.

Bean Trader 샘플에 대한 새 프로젝트 파일을 만들려면 임시 디렉터리에서 `dotnet new wpf`를 실행하여 생성된 *.csproj* 파일을 *BeanTraderClient* 폴더로 옮기고 이름을 **BeanTraderClient.Core.csproj**로 바꿉니다.

새 프로젝트 파일 형식에는 C# 파일, *resx* 파일, XAML 파일이 해당 디렉터리 내에 자동으로 포함되기 때문에 프로젝트 파일은 이미 거의 완성되었습니다! 마이그레이션을 마치려면 이전 프로젝트 파일과 새 프로젝트 파일을 나란히 열어두고 이전 파일을 살펴보면서 포함된 정보 중 마이그레이션이 필요한 정보가 있는지 확인합니다. Bean Trader 샘플의 경우, 다음 항목을 새 프로젝트에 복사해야 합니다.

- `<RootNamespace>`, `<AssemblyName>`, `<ApplicationIcon>` 속성을 모두 복사해야 합니다.

- Bean Trader 샘플은 AssemblyInfo.cs 파일에 어셈블리 수준 속성(예: `[AssemblyTitle]`)이 포함되어 있기 때문에 새 프로젝트 파일에 `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` 속성도 추가해야 합니다. 기본적으로 새 SDK 스타일 프로젝트는 csproj 파일의 속성을 기반으로 이러한 특성을 자동으로 생성합니다. 이 경우에는 이렇게 수행되는 것을 원하지 않기 때문에(자동 생성된 특성이 AssemblyInfo.cs의 특성과 충돌함), `<GenerateAssemblyInfo>`를 사용하여 자동 생성된 특성을 비활성화합니다.

- *resx* 파일은 포함된 리소스로 자동 포함되지만 이미지와 같은 다른 `<Resource>` 항목은 그렇지 않습니다. 따라서 이미지와 아이콘 파일을 포함하기 위해 `<Resource>` 요소를 복사합니다. 와일드 카드 사용 패턴(`<Resource Include="**\*.png" />`)에 대한 새 프로젝트 파일 형식의 지원을 사용하면 png 참조를 한 줄로 간소화할 수 있습니다.

- 마찬가지로 `<None>` 항목은 자동으로 포함되지만, 기본적으로 출력 디렉터리에 복사되지 않습니다. Bean Trader 프로젝트에는 출력 디렉터리에 복사된(`PreserveNewest` 동작을 사용하여) `<None>` 항목이 포함되어 있기 때문에, 이 파일에 대해 자동으로 채워진 `<None>` 항목을 다음과 같이 업데이트해야 합니다.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- Bean Trader 샘플에는 XAML 파일(Default.Accent.xaml)이 `Page`가 아닌 `Content`로 포함되어 있습니다. 이 파일에 정의된 테마와 강조는 앱 자체에 포함되지 않고 런타임 시 파일의 XAML에서 로드되기 때문입니다. 새 프로젝트 시스템은 이 파일을 `<Page>`로 자동 포함합니다. 하지만 이것은 XAML 파일이기 때문에, 페이지로 포함된 XAML 파일을 제거하고(`<Page Remove="**\Default.Accent.xaml" />`) 콘텐츠로 추가해야 합니다.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- 마지막으로 모든 `<ItemGroup>`을 `<PackageReference>` 요소와 함께 복사하여 NuGet 참조를 추가합니다. 이전에 NuGet 패키지를 .NET Core 호환 버전으로 업그레이드하지 않았으면, 이제 패키지 참조가 .NET Core 관련 프로젝트에 있으므로 지금 할 수 있습니다.

이제 BeanTrader 솔루션에 새 프로젝트를 추가하고 Visual Studio에서 열 수 있습니다. 프로젝트가 **솔루션 탐색기**에서 올바르게 표시되고 `dotnet restore BeanTraderClient.Core.csproj`는 패키지를 성공적으로 복원해야 합니다(.NET Framework를 대상으로 하는 사용 중인 MahApps.Metro 버전과 관련된 두 가지 경고가 예상됨).

두 프로젝트 파일을 나란히 유지하는 것이 가능하더라도(기존 프로젝트를 그대로 빌드하려는 경우에는 바람직할 수도 있지만), 마이그레이션 프로세스가 복잡해지고(두 프로젝트가 동일한 bin 및 obj 폴더를 사용하려고 함) 대개는 그럴 필요가 없습니다. .NET Core와 .NET Framework 대상 모두에 대해 빌드하려면 새 프로젝트 파일의 `<TargetFramework>netcoreapp3.0</TargetFramework>` 속성을 대신 `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>`로 바꾸면 됩니다. Bean Trader 샘플의 경우 이전 프로젝트 파일(BeanTraderClient.csproj)이 더 이상 필요하지 않으므로 삭제합니다. 두 프로젝트 파일을 모두 유지하려면 서로 다른 출력 및 중간 출력 경로로 빌드해야 합니다.

## <a name="fix-build-issues"></a>빌드 문제 해결

이식 프로세스의 세 번째 단계는 프로젝트를 빌드하는 것입니다. 어떤 앱은 프로젝트 파일이 SDK 스타일 프로젝트로 변환되면 이미 빌드에 성공합니다. 이런 경우에 해당하는 앱이라면, 축하드립니다! 4단계로 이동하면 됩니다. 다른 앱은 .NET Core용으로 빌드하기 위해 업데이트가 필요합니다. 예를 들어, Bean Trader 샘플 프로젝트에서 `dotnet build`를 실행(또는 Visual Studio에서 빌드)하려고 하면 많은 오류가 발생하겠지만 신속하게 해결할 수 있습니다.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>System.ServiceModel 참조 및 Microsoft.Windows.Compatibility

일반적인 오류의 원인은 .NET Core에서 사용 가능하지만 .NET Core 앱 메타 패키지에는 자동으로 포함되지 않는 API에 대한 참조가 누락된 것입니다. 이 문제를 해결하려면 `Microsoft.Windows.Compatibility` 패키지를 참조해야 합니다. 호환성 패키지에는 Windows 데스크톱 앱에서 일반적으로 사용되는 광범위한 API 세트(예: WCF 클라이언트, 디렉터리 서비스, 레지스트리, 구성, ACL API 등)가 포함되어 있습니다.

Bean Trader 샘플에서 대부분의 빌드 오류는 <xref:System.ServiceModel> 형식이 누락되었기 때문입니다. 이것은 필요한 WCF NuGet 패키지를 참조하여 해결할 수 있습니다. WCF 클라이언트 API는 `Microsoft.Windows.Compatibility` 패키지에 포함되어 있으므로 호환성 패키지를 참조하는 것이 더 나은 솔루션입니다. (호환성 패키지에 제공되는 WCF 문제에 대한 솔루션뿐만 아니라 API 관련 문제도 해결되기 때문입니다.) `Microsoft.Windows.Compatibility` 패키지는 대부분의 .NET Core 3.0 WPF 및 WinForms 이식 시나리오에 유용합니다. `Microsoft.Windows.Compatibility`에 NuGet 참조를 추가하면 빌드 오류가 하나만 남습니다!

### <a name="cleaning-up-unused-files"></a>사용되지 않는 파일 정리

자주 발생하는 마이그레이션 문제 중 한 가지 형식은, 이전에는 빌드에 포함되지 않은 C# 및 XAML 파일이 모든 소스를 자동으로 포함하는 새로운 SDK 스타일 프로젝트에서 선택되는 것과 관련이 있습니다.

Bean Trader 샘플에 보이는 다음 빌드 오류는 *OldUnusedViewModel.cs*의 잘못된 인터페이스 구현을 나타냅니다. 파일 이름에 힌트가 있지만 검사를 하면 소스 파일이 잘못된 것을 알 수 있습니다. 원래 .NET Framework 프로젝트에는 포함되지 않았기 때문에 이전에는 문제가 발생하지 않았습니다. 디스크에 있어도 이전 *csproj*에는 포함되지 않았던 소스 파일이 이제 자동으로 포함되어 있습니다.

이와 같이 한 번만 있는 문제는 이전 *csproj*와 비교하여 파일이 필요하지 않은 것을 확인한 다음, `<Compile Remove="" />` 처리하거나 소스 파일이 더 이상 필요하지 않으면 삭제하는 것이 쉽습니다. 이 경우 *OldUnusedViewModel.cs*를 삭제하는 것이 안전합니다.

이런 방식으로 제외해야 하는 소스 파일이 많으면, 프로젝트 파일에서 `<EnableDefaultCompileItems>` 속성을 false로 설정하여 C# 파일의 자동 포함을 비활성화하면 됩니다. 그런 다음, 포함하려는 소스만 빌드되도록 이전 프로젝트 파일의 `<Compile Include>` 항목을 새 프로젝트 파일로 복사하면 됩니다. 마찬가지로 `<EnableDefaultPageItems>`을 사용하여 XAML 페이지의 자동 포함을 해제할 수 있고 `<EnableDefaultItems>`는 단일 속성으로 둘 다 제어가 가능합니다.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>멀티 패스 컴파일러에 대한 간략한 설명

Bean Trader 샘플에서 문제가 되는 파일을 제거한 후 다시 빌드하면 오류 4개가 발생합니다. 전에는 1개 아니었나요? 오류 수가 왜 증가했나요? C# 컴파일러는 [멀티 패스 컴파일러](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)입니다. 즉, 각 소스 파일을 두 번 살펴봅니다. 처음에는, 컴파일러가 각 소스 파일에서 메타데이터와 선언을 살펴보고 선언 수준 문제가 있는지 확인합니다. 이러한 문제는 해결한 오류입니다. 그런 다음, 코드를 다시 살펴보고 C# 소스를 IL로 빌드합니다. 이것이 지금 보이는 두 번째 오류 세트입니다.

> [!NOTE]
> C# 컴파일러는 [두 번 이상의 패스](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)를 수행하지만, 최종 결과는 이와 같은 대량 코드 변경에 대한 컴파일러 오류가 두 번에 걸쳐 제공되는 경향이 있습니다.

### <a name="third-party-dependency-fixes-castlewindsor"></a>타사 종속성 해결(Castle.Windsor)

일부 마이그레이션 시나리오에서 발생하는 또 다른 문제는 .NET Framework와 .NET Core 버전 종속성 간의 API 차이점입니다. NuGet 패키지가 .NET Framework와 .NET Standard 모두를 또는 .NET Core를 대상으로 하더라도 여러 .NET 대상에 다른 라이브러리를 사용할 수 있습니다. 이렇게 하면 패키지가 여러 .NET 플랫폼을 지원할 수 있으며 따라서 여러 구현이 필요할 수 있습니다. 또한 여러 .NET 플랫폼을 대상으로 하는 경우, 라이브러리마다 API에 약간의 차이가 있을 수 있습니다.

Bean Trader 샘플에서 볼 다음 오류 세트는 `Castle.Windsor` API와 관련이 있습니다. .NET Core Bean Trader 프로젝트는 .NET Framework 대상 프로젝트(4.1.1)와 동일한 버전의 `Castle.Windsor`를 사용하지만, 두 가지 플랫폼에 대한 구현은 약간 다릅니다.

이 경우 수정해야 하는 문제는 다음과 같습니다.

1. .NET Core에서는 `Castle.MicroKernel.Registration.Classes.FromThisAssembly`를 사용할 수 없습니다. 하지만 유사한 API인 `Classes.FromAssemblyContaining`을 사용할 수 있으므로 `Classes.FromThisAssembly()` 사용을 `Classes.FromAssemblyContaining(t)` 호출로 대체할 수 있습니다. 여기에서 `t`는 호출을 수행하는 형식입니다.
1. 마찬가지로 *Bootstrapper.cs*에는 `Castle.Windsor.Installer.FromAssembly`가 있는데, .NET Core에서는 사용할 수 없습니다. 대신 이 호출을 `FromAssembly.Containing(typeof(Bootstrapper))`로 바꿀 수 있습니다.

### <a name="updating-wcf-client-usage"></a>WCF 클라이언트 사용 업데이트

`Castle.Windsor` 차이를 해결했으므로, .NET Core Bean Trader 프로젝트에 마지막으로 남은 빌드 오류는 `BeanTraderServiceClient`(`DuplexClientBase`에서 파생됨)에 `Open` 메서드가 없는 것입니다. 마이그레이션 프로세스를 시작할 때 .NET 이식성 분석기에 강조 표시된 API이기 때문에 알고 있는 내용입니다. 하지만, `BeanTraderServiceClient`를 살펴보면 더 큰 문제에 주목하게 됩니다. [Svcutil.exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구에서 WCF 클라이언트가 자동으로 생성되었습니다.

**Svcutil에서 생성된 WCF 클라이언트는 .NET Framework에서만 사용이 가능합니다.**

svcutil에서 생성된 WCF 클라이언트를 사용하는 솔루션은 .NET Core에 사용할 .NET Standard 호환 클라이언트를 다시 생성해야 합니다. 이전 클라이언트가 작동하지 않는 주된 이유 중 하나는 앱 구성에 의존하여 WCF 바인딩과 엔드포인트를 정의한다는 점입니다. .NET Standard WCF API는 플랫폼 간 작동이 가능하기 때문에(System.Configuration API를 사용할 수 없는 경우), .NET Core 및 .NET Standard 시나리오의 WCF 클라이언트는 구성이 아닌 프로그래밍 방식으로 바인딩과 엔드포인트를 정의해야 합니다.

실제로, `<system.serviceModel>` app.config 섹션에 종속된 WCF 클라이언트(Svcutil에서 생성되거나 수동으로 생성한) 사용이 .NET Core에서 작동하려면 변경해야 합니다.

.NET Standard 호환 WCF 클라이언트를 자동으로 생성하는 방법은 두 가지입니다.

- `dotnet-svcutil` 도구는 Svcutil의 이전 작동 방식과 유사하게 WCF 클라이언트를 생성하는 .NET 도구입니다.
- Visual Studio는 자체 연결된 서비스 기능의 [WCF Web Service Reference](../../core/additional-tools/wcf-web-service-reference-guide.md) 옵션을 사용하여 WCF 클라이언트를 생성할 수 있습니다.

어느 방식이든 괜찮습니다. 물론 WCF 클라이언트 코드를 직접 작성할 수도 있습니다. 이 샘플에서는 Visual Studio 연결된 서비스 기능을 사용하겠습니다. 그러려면, Visual Studio의 솔루션 탐색기에서 *BeanTraderClient.Core* 프로젝트를 마우스 오른쪽 단추로 클릭하고, **추가** > **연결된 서비스**를 선택합니다. 다음으로 WCF Web Service Reference Provider를 선택합니다. 그러면 대화 상자가 열리고 백 엔드 Bean Trader 웹 서비스의 주소(로컬에서 서버를 실행하는 경우 `localhost:8080`) 및 생성된 형식을 사용해야 하는 네임스페이스(예: **BeanTrader.Service**)를 지정할 수 있습니다

![WCF Web Service Reference 연결된 서비스 대화 상자](./media/convert-project-from-net-framework/connected-service-dialog.png)

**마침** 단추를 선택하면, 새로운 연결된 서비스 노드가 프로젝트에 추가되고 이 노드(Bean Trader 서비스에 액세스하기 위한 새 .NET Standard WCF 클라이언트가 포함됨) 아래에 Reference.cs 파일이 추가됩니다. 이 파일에서 `GetEndpointAddress`나 또는 `GetBindingForEndpoint` 메서드를 살펴보면 바인딩과 엔드포인트가 이제 프로그래밍 방식으로(앱 구성을 통하지 않고) 생성된 것을 볼 수 있습니다. '연결된 서비스 추가' 기능이 프로젝트 파일의 일부 System.ServiceModel 패키지에 대한 참조를 추가할 수도 있지만 필요한 모든 WCF 패키지가 Microsoft.Windows.Compatibility를 통해 포함되기 때문에 필요하지 않습니다. csproj를 확인하여 System.ServiceModel `<PackageReference>` 항목이 더 추가되었는지 확인하고 그런 경우에는 제거합니다.

이제 프로젝트에 새 WCF 클라이언트 클래스가 있지만(*Reference.cs*에) 아직 이전 클래스도 있습니다(BeanTrader.cs에). 이 시점에는 두 가지 옵션이 있습니다.

- 원래 .NET Framework 프로젝트(새로운 .NET Core 대상 프로젝트와 함께)를 빌드하려면, .NET Framework와 .NET Core 버전의 앱이 서로 다른 WCF 클라이언트를 사용하도록 .NET Core 프로젝트의 csproj 파일에 `<Compile Remove="BeanTrader.cs" />` 항목을 사용하면 됩니다. 이렇게 하면 기존 .NET Framework 프로젝트를 변경하지 않고 그대로 두는 이점이 있지만, 생성된 WCF 클라이언트를 사용하는 코드가 .NET Core의 경우 .NET Framework 프로젝트의 경우와 약간 다를 수 있다는 단점이 있습니다. 따라서 `#if` 지시문을 사용하여 .NET Core용으로 빌드할 때와 .NET Framework 용으로 빌드할 때가 다르게 작동하도록 일부 WCF 클라이언트 사용(예: 클라이언트 생성)을 조건부로 컴파일해야 합니다.

- 반면에 기존 .NET Framework 프로젝트에서 일부 코드 변경이 허용되는 경우 *BeanTrader.cs*를 모두 제거할 수 있습니다. 새 WCF 클라이언트는 .NET Standard용으로 빌드되었기 때문에 .NET Core와 .NET Framework 시나리오 모두에서 작동합니다. .NET Core용 외에도 .NET Framework용 빌드를 수행하는 경우(멀티 타기팅을 통해 또는 csproj 파일을 두 개 사용하여), 두 대상 모두에 새 *Reference.cs* 파일을 사용할 수 있습니다. 이 방식은 두 가지 다른 WCF 클라이언트를 지원하기 위해 코드를 분기할 필요가 없다는 장점이 있습니다. 동일한 코드가 모든 곳에 사용됩니다. 단점은 .NET Framework 프로젝트(가정상 안정적인) 변경과 관련이 있습니다.

Bean Trader 샘플의 경우, 마이그레이션이 더 편해진다면 원래 프로젝트를 약간 변경할 수 있습니다. 따라서 다음 단계에 따라 WCF 클라이언트 사용을 조정할 수 있습니다.

01. 솔루션 탐색기에서 '기존 항목 추가'라는 상황에 맞는 메뉴를 사용하여 새 Reference.cs 파일을 .NET Framework *BeanTraderClient.csproj* 프로젝트에 추가합니다. 두 프로젝트에 동일한 파일이 사용되도록 '링크로' 추가해야 합니다(C# 파일을 복사하는 것이 아님). 단일 csproj(멀티 타기팅을 사용하여)로 .NET Core와 .NET Framework용 빌드를 모두 수행하는 경우에는 이 단계가 필요하지 않습니다.

01. *BeanTrader.cs*를 삭제합니다.

01. 새 WCF 클라이언트는 이전 WCF 클라이언트와 비슷하지만 생성된 코드에서 다수의 네임스페이스가 다릅니다. 따라서, WCF 클라이언트 형식이 BeanTrader.Model 대신 또는 네임스페이스 없이 BeanTrader.Service(또는 선택한 네임스페이스 이름)에서 사용되도록 프로젝트를 업데이트해야 합니다. *BeanTraderClient.Core.csproj*를 빌드하면 이러한 변경이 필요한 위치를 식별하는 데 도움이 됩니다. C#과 XAML 소스 파일 모두에서 수정이 필요합니다.

01. 마지막으로 `BeanTraderServiceClient` 형식에 사용할 수 있는 생성자가 변경되었으니 *BeanTraderServiceClientFactory.cs*에 오류가 있는 것을 알게 됩니다. 이전에는 `InstanceContext` 인수(`Castle.Windsor` IoC 컨테이너의 `CallbackHandler`를 사용하여 생성됨)를 제공할 수 있었습니다. 새 생성자는 새로운 `CallbackHandler`를 생성합니다. 하지만 `BeanTraderServiceClient`의 기본 형식에는 필요한 것과 일치하는 생성자가 있습니다. 자동 생성된 WCF 클라이언트 코드는 모두 partial 클래스에 있으므로 쉽게 확장할 수 있습니다. 이렇게 하려면 *BeanTraderServiceClient.cs*라는 새 파일을 만든 다음, 동일한 이름(BeanTrader.Service 네임스페이스 사용)으로 partial 클래스를 만듭니다. 그런 다음, 부분 형식(Partial Type)에 생성자를 하나 추가합니다(아래 참조).

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

변경이 완료되면 이제 Bean Trader 샘플에 새로운 .NET Standard 호환 WCF 클라이언트가 사용되며, *TradingService.cs*에서 `Open` 호출에 `await OpenAsync`가 대신 사용되도록 변경하는 마지막 수정 작업을 수행할 수 있습니다.

WCF 문제가 해결되면 .NET Core 버전의 Bean Trader 샘플이 이제 깔끔하게 빌드됩니다!

## <a name="runtime-testing"></a>런타임 테스트

프로젝트가 .NET Core에 대해 깔끔하게 빌드되는 즉시 마이그레이션 작업이 완료되는 것이 아니라는 사실을 잊기 쉽습니다. 이식된 앱을 테스트할 시간을 남겨 두는 것도 중요합니다. 빌드가 완료되고 나면, 앱이 실행되고 예상대로 작동하는지 확인해야 합니다. 특히 .NET Framework를 대상으로 하는 패키지를 사용하는 경우에는 반드시 필요합니다.

이식된 Bean Trader 앱을 시작하여 어떻게 작동하는지 살펴보겠습니다. 앱에 곧 장애가 발생하고 다음 예외가 발생합니다.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

물론, 이는 적절합니다. WCF에는 앱 구성이 더 이상 사용되지 않습니다. 따라서 app.config 파일의 이전 system.serviceModel 섹션을 제거해야 합니다. 업데이트된 WCF 클라이언트는 동일한 모든 정보가 코드에 포함되기 때문에 구성 섹션이 더 이상 필요하지 않습니다. app.config에서 WCF 엔드포인트를 구성할 수 있게 하려면 해당 항목을 앱 설정으로 추가하고, 구성에서 WCF 서비스 엔드포인트를 검색하도록 WCF 클라이언트 코드를 업데이트할 수 있습니다.

*app.config*의 system.serviceModel 섹션을 제거하면 앱이 실행되지만 사용자가 로그인하면 다른 예외로 인해 실패합니다.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

지원되지 않는 API는 `Func<T>.BeginInvoke`입니다. [dotnet/corefx#5940](https://github.com/dotnet/corefx/issues/5940)의 설명대로 .NET Core는 기본 원격 종속성으로 인해 대리자 형식에서 `BeginInvoke` 및 `EndInvoke` 메서드를 지원하지 않습니다. 이 문제와 해결 방법은 [Migrating Delegate.BeginInvoke Calls for .NET Core](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/)(.NET Core에 대한 Delegate.BeginInvoke 호출 마이그레이션) 블로그 게시물에 자세히 설명되어 있지만, 요지는 `BeginInvoke`와 `EndInvoke` 호출을 `Task.Run`(또는 가능한 경우 비동기 대안)으로 바꿔야 한다는 것입니다. 여기에서 일반적인 솔루션을 적용하면 `BeginInvoke` 호출을 `Task.Run`에서 시작한 `Invoke` 호출로 바꿀 수 있습니다.

```csharp
Task.Run(() =>
{
    return userInfoRetriever.Invoke();
}).ContinueWith(result =>
{
    // BeginInvoke's callback is replaced with ContinueWith
    var task = result.ConfigureAwait(false);
    CurrentTrader = task.GetAwaiter().GetResult();
}, TaskScheduler.Default);
```

`BeginInvoke` 사용을 제거하면 Bean Trader 앱이 .NET Core에서 성공적으로 실행됩니다!

![.NET Core에서 실행되는 Bean Trader](./media/convert-project-from-net-framework/running-on-core.png)

모든 앱은 서로 다릅니다. 따라서 각자의 앱을 .NET Core로 마이그레이션하는 데 필요한 구체적인 단계는 다양합니다. 하지만, Bean Trader 샘플을 통해 일반적인 워크플로와 예상할 수 있는 문제 유형을 참고하실 수 있기를 바랍니다. 문서의 길이는 장황하지만, Bean Trader 샘플이 .NET Core에서 작동하도록 만들기 위해 실제로 변경해야 하는 내용은 상당히 제한적입니다. 많은 앱이 .NET Core에 동일한 방식으로 마이그레이션되며, 코드 변경은 제한적이거나 전혀 필요하지 않습니다.
