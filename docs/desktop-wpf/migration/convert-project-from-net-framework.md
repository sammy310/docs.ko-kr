---
title: WPF 앱을 .NET 코어 3.0으로 마이그레이션
description: Windows 프레젠테이션 기반(WPF) 앱을 .NET Core 3.0으로 마이그레이션하는 방법을 알아봅니다.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: f52005e7c8a6312b8c4e09a950f1f635af1894e4
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "81432595"
---
# <a name="migrating-wpf-apps-to-net-core"></a>WPF 앱에서 .NET 코어로 마이그레이션

이 문서에서는 .NET Framework에서 .NET Core 3.0으로 Windows 프레젠테이션 기반(WPF) 앱을 마이그레이션하는 데 필요한 단계를 설명합니다. 포트에 손에 WPF 응용 프로그램이 없는 경우, 하지만 프로세스를 시도 하 고 **Bean Trader** 싶습니다. [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) 원래 응용 프로그램 (대상 .NET 프레임 워크 4.7.2) NetFx\BeanTraderClient 폴더에서 사용할 수 있습니다. 먼저 일반적으로 앱을 포팅하는 데 필요한 단계를 설명한 다음 **Bean Trader** 샘플에 적용되는 특정 변경 사항을 살펴보겠습니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

.NET Core로 마이그레이션하려면 먼저 다음을 수행해야 합니다.

01. NuGet 종속성을 이해하고 업데이트합니다.

    01. NuGet 종속성을 업그레이드하여 `<PackageReference>` 형식을 사용합니다.
    01. .NET 코어 또는 .NET 표준 호환성에 대한 최상위 NuGet 종속성을 검토합니다.
    01. NuGet 패키지를 최신 버전으로 업그레이드합니다.
    01. [.NET 이식성 분석기를](../../standard/analyzers/portability-analyzer.md) 사용하여 .NET 종속성을 이해합니다.

01. 프로젝트 파일을 새 SDK 스타일 형식으로 마이그레이션합니다.

    01. .NET 코어와 .NET 프레임워크를 모두 대상으로 할지 또는 .NET 코어만 대상으로 할지 선택합니다.
    01. 관련 프로젝트 파일 속성 및 항목을 새 프로젝트 파일에 복사합니다.

01. 빌드 문제 해결:

    01. [Microsoft.Windows.호환성](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) 패키지에 대한 참조를 추가합니다.
    01. API 수준 차이를 찾아 수정합니다.
    01. 또는 이외의 *app.config* `connectionStrings`섹션을 제거합니다. `appSettings`
    01. 필요한 경우 생성된 코드를 다시 생성합니다.

01. 런타임 테스트:

    01. 포팅된 앱이 예상대로 작동하는지 확인합니다.
    01. <xref:System.NotSupportedException> 예외를 주의하십시오.

## <a name="about-the-sample"></a>샘플 정보

이 문서에서는 실제 WPF 앱과 유사한 다양한 종속성을 사용하기 때문에 [Bean Trader 샘플](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) 앱을 참조합니다. 이 앱은 크지는 않지만 복잡성 측면에서 'Hello World'에서 한 단계 더 올라가기 위한 것입니다. 이 앱은 실제 앱을 이식하는 동안 사용자가 발생할 수 있는 몇 가지 문제를 보여 줍니다. 응용 프로그램은 WCF 서비스와 통신, 그래서 제대로 실행하려면, 당신은 또한 BeanTraderServer 프로젝트를 실행해야합니다 (동일한 GitHub 리포지토리에서 사용 가능) BeanTraderClient 구성이 올바른 끝점을 가리키는지 확인합니다. (기본적으로 샘플은 서버가 동일한 컴퓨터에서 *http://localhost:8090*실행되고 있다고 가정합니다.

이 샘플 앱은 .NET Core 포팅 과제및 솔루션을 시연하기 위한 것입니다. WPF 모범 사례를 설명하기 위한 것이 아닙니다. 사실, 그것은 의도적으로 포팅 하는 동안 흥미로운 도전의 적어도 몇 건너 있는지 확인 하는 몇 가지 안티 패턴을 포함.

## <a name="getting-ready"></a>준비

.NET Framework 앱을 .NET Core로 마이그레이션하는 주요 과제는 종속성이 다르게 작동하거나 전혀 작동하지 않을 수 있다는 것입니다. 마이그레이션은 이전보다 훨씬 쉽습니다. 이제 많은 NuGet 패키지가 .NET 표준을 대상으로 합니다. .NET Core 2.0부터 .NET 프레임워크와 .NET 코어 표면 영역이 비슷해졌습니다. 그럼에도 불구하고 NuGet 패키지와 사용 가능한 .NET API모두에서 몇 가지 차이점이 남아 있습니다. 마이그레이션의 첫 번째 단계는 앱의 종속성을 검토하고 참조가 .NET Core로 쉽게 마이그레이션할 수 있는 형식으로 되어 있는지 확인하는 것입니다.

### <a name="upgrade-to-packagereference-nuget-references"></a>NuGet `<PackageReference>` 참조로 업그레이드

이전 .NET Framework 프로젝트는 일반적으로 *Packages.config* 파일에 NuGet 종속성을 나열합니다. 새로운 SDK 스타일 프로젝트 파일 형식은 NuGet 패키지를 별도의 구성 파일이 아닌 csproj 파일 자체의 요소로 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 참조합니다.

마이그레이션할 때 -style 참조를 `<PackageReference>`사용하면 두 가지 장점이 있습니다.

- 새 .NET Core 프로젝트 파일에 필요한 NuGet 참조 스타일입니다. 이미 사용 `<PackageReference>`중인 경우 해당 프로젝트 파일 요소를 복사하여 새 프로젝트에 직접 붙여넣을 수 있습니다.
- packages.config 파일과 `<PackageReference>` 달리 요소는 프로젝트가 직접 종속되는 최상위 종속성만 참조합니다. 다른 모든 전이적 NuGet 패키지는 복원 시점에 결정되며 자동 생성된 obj\project.assets.json 파일에 기록됩니다. 이렇게 하면 프로젝트에 어떤 종속성이 있는지 쉽게 확인할 수 있으므로 .NET Core에서 필요한 종속성이 작동하는지 여부를 결정할 때 유용합니다.

.NET Framework 앱을 .NET Core로 마이그레이션하는 첫 번째 단계는 NuGet 참조를 사용하도록 `<PackageReference>` 업데이트하는 것입니다. 비주얼 스튜디오는 이 것을 간단하게 만듭니다. Visual Studio의 **솔루션 탐색기에서**프로젝트의 *packages.config* 파일을 마우스 오른쪽 단추로 클릭한 다음 **packages.config를 패키지참조로 마이그레이션합니다.**

![패키지참조로 업그레이드](./media/convert-project-from-net-framework/package-reference-migration.png)

계산된 최상위 NuGet 종속성을 표시하고 최상위 수준으로 승격해야 하는 다른 NuGet 패키지를 묻는 대화 상자가 나타납니다. 이러한 다른 패키지 중 어느 것도 콩 상인 샘플에 대한 최상위 가 될 필요가 없습니다, 그래서 당신은 그 상자의 모든 선택을 취소 할 수 있습니다. 그런 다음 **확인을** 클릭하면 *packages.config* `<PackageReference>` 파일이 제거되고 요소가 프로젝트 파일에 추가됩니다.

`<PackageReference>`-스타일 참조는 NuGet 패키지를 패키지 폴더에 로컬로 저장하지 않습니다. 대신 최적화로 전역적으로 저장됩니다. 마이그레이션이 완료되면 csproj 파일을 편집하고 .에서 `<Analyzer>` 이전에 보낸 분석기를 참조하는 요소를 제거합니다. * \패키지* 디렉토리. 걱정하지 마세요. NuGet 패키지 참조가 남아 있으므로 분석기는 프로젝트에 포함됩니다. 이전 패키지를 정리하기만 하면 됩니다.config `<Analyzer>` 스타일 요소입니다.

### <a name="review-nuget-packages"></a>NuGet 패키지 검토

이제 프로젝트에 종속된 최상위 NuGet 패키지를 볼 수 있으므로 .NET Core에서 해당 패키지를 사용할 수 있는지 여부를 검토할 수 있습니다. nuget.org 종속성을 확인하여 패키지가 .NET [Core를](https://www.nuget.org/)지원하는지 여부를 확인할 수 있습니다. 커뮤니티에서 만든 [fuget.org](https://www.fuget.org/) 사이트는 패키지 정보 페이지 상단에 이 정보를 눈에 띄게 표시합니다.

.NET Core 3.0을 대상으로 하는 경우 .NET Core 또는 .NET 표준을 대상으로 하는 모든 패키지가 작동해야 합니다(.NET Core는 .NET 표준 표면 영역을 구현하기 때문에). 경우에 따라 사용 되는 패키지의 특정 버전 .NET 코어 또는 .NET 표준을 대상으로 하지 않습니다 하지만 최신 버전 것입니다. 이 경우 패키지의 최신 버전으로 업그레이드하는 것이 좋습니다.

.NET Framework를 대상으로 하는 패키지도 사용할 수 있지만 몇 가지 위험이 있습니다. .NET Core에서 .NET 프레임워크에 종속되는 것은 .NET Core 및 .NET Framework 영역이 이러한 종속성이 *자주* 작동할 정도로 유사하기 때문에 허용됩니다. 그러나 패키지가 .NET Core에 없는 .NET API를 사용하려고 하면 런타임 예외가 발생합니다. 따라서 다른 옵션을 사용할 수 없는 경우에만 .NET Framework 패키지를 참조해야 하며 이렇게 하면 테스트 부담이 가중된다는 것을 이해해야 합니다.

.NET Core 또는 .NET Standard를 대상으로 하지 않는 참조된 패키지가 있는 경우 다른 대안을 고려해야 합니다.

- 대신 사용할 수있는 다른 유사한 패키지가 있습니까? 때때로 NuGet 저자는 별도의 '를 게시합니다. 특히 .NET 코어를 대상으로 하는 라이브러리의 코어 버전입니다. 엔터프라이즈 라이브러리 패키지는 커뮤니티 게시 "의 예입니다. 넷 코어"대안. 다른 경우에는 .NET Standard에서 특정 서비스에 대한 최신 SDK(때로는 다른 패키지 이름)를 사용할 수 있습니다. 사용할 수 있는 대안이 없는 경우 .NET Core에서 실행한 후 철저히 테스트해야 한다는 점을 염두에 두고 .NET Framework 대상 패키지를 사용하여 진행할 수 있습니다.

빈 트레이더 샘플에는 다음과 같은 최상위 NuGet 종속성이 있습니다.

- [**캐슬.윈저, 버전 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  이 패키지는 .NET 표준 1.6을 대상으로 하므로 .NET Core에서 작동합니다.

- [**마이크로소프트.코드분석.FxCop분석기, 버전 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  이 패키지는 메타 패키지이므로 지원하는 플랫폼을 즉시 알 수는 없지만 [문서에 따르면](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) 최신 버전(2.9.2)이 .NET Framework 및 .NET Core 모두에서 작동합니다.

- [**니토.애싱크, 버전 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  이 패키지는 .NET Core를 대상으로 하지 않지만 최신 5.0 버전은 해당 합니다. 많은 NuGet 패키지가 최근에 .NET 표준 지원을 추가했지만 이전 프로젝트 버전은 .NET Framework만 대상으로 하므로 마이그레이션할 때 일반적입니다. 버전 차이가 사소한 버전 차이인 경우 최신 버전으로 쉽게 업그레이드할 수 있습니다. 이는 주요 버전 변경이므로 패키지에 주요 변경 사항이 있을 수 있으므로 신중하게 업그레이드해야 합니다. 하지만 앞으로 나아갈 길이 있습니다.

- [**MahApps.Metro, 버전 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  이 패키지는 .NET Core를 대상으로 하지 않지만 최신 시험판(2.0-알파)을 사용합니다. 다시 말하지만, 당신은 변화를 깨는 조심해야하지만, 새로운 패키지는 고무적이다.

빈 트레이더 샘플의 NuGet 종속성은 모두 .NET 표준/.NET 코어를 대상으로 하거나 최신 버전을 가지고 있으므로 여기에서 차단 문제가 발생하지 않을 수 있습니다.

### <a name="upgrade-nuget-packages"></a>NuGet 패키지 업그레이드

가능하면 이 시점에서 최신 버전(프로젝트가 여전히 .NET Framework을 대상으로 하는)으로 .NET Core 또는 .NET 표준만을 대상으로 하는 모든 패키지의 버전을 업그레이드하여 주요 변경 사항을 조기에 발견하고 해결하는 것이 좋습니다.

앱의 기존 .NET Framework 버전을 변경하지 않으려면 .NET Core를 대상으로 하는 새 프로젝트 파일이 있을 때까지 기다릴 수 있습니다. 그러나 NuGet 패키지를 미리 .NET Core 호환 버전으로 업그레이드하면 새 프로젝트 파일을 만들면 마이그레이션 프로세스가 더욱 쉬워지고 .NET Framework와 .NET Core 버전 간의 차이점이 줄어듭니다.

Bean Trader 샘플을 사용하면 한 가지 예외를 제외하고 필요한 모든 업그레이드를 쉽게 수행할 수 있습니다(Visual Studio의 NuGet 패키지 관리자 사용) **MahApps.Metro 1.6.5에서** **2.0으로** 업그레이드하면 테마 및 악센트 관리 API와 관련된 주요 변경 사항이 표시됩니다.

이상적으로는 .NET Core에서 작동할 가능성이 높기 때문에 최신 버전의 패키지를 사용하도록 앱이 업데이트되는 것이 좋습니다. 그러나 경우에 따라 실현 가능하지 않을 수 있습니다. 이러한 경우 필요한 변경 사항이 간단하지 않고 이 자습서에서는 **MahApps.Metro 2가** 아닌 .NET Core 3로 마이그레이션하는 데 중점을 두므로 **MahApps.Metro를** 업그레이드하지 마십시오. 또한, 이것은 낮은 위험 .NET 프레임 워크 종속성 때문에 콩 상인 응용 프로그램 **MahApps.Metro의**작은 부분만 실행 . 물론 마이그레이션이 완료되면 모든 것이 작동하는지 확인하기 위한 테스트가 필요합니다. 이것이 실제 시나리오라면 마이그레이션을 수행하지 않기 때문에 **MahApps.Metro** 버전 2.0으로 이동하는 작업을 추적하는 문제를 제기하는 것이 좋습니다.

NuGet 패키지가 최신 버전으로 업데이트되면 Bean Trader 샘플의 프로젝트 파일의 `<PackageReference>` 항목 그룹이 다음과 같아야 합니다.

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

### <a name="net-framework-portability-analysis"></a>.NET 프레임워크 이식성 분석

프로젝트의 NuGet 종속성 상태를 이해한 후 고려해야 할 다음 은 .NET Framework API 종속성입니다. [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) 도구는 프로젝트가 사용하는 .NET API 중 다른 .NET 플랫폼에서 사용할 수 있는 .NET API를 이해하는 데 유용합니다.

이 도구는 [Visual Studio 플러그인,](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) [명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases)또는 [간단한 GUI로](https://github.com/Microsoft/dotnet-apiport-ui)감싸서 옵션을 단순화합니다. 포팅 데스크톱 앱의 GUI를 사용하여 .NET Core 블로그 게시물에 [.NET 이식성](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/) 분석기(API 포트)를 사용하는 것에 대해 자세히 읽을 수 있습니다. 명령줄을 사용하려는 경우 필요한 단계는 다음과 같습니다.

1. [.NET 이식성 분석기를](https://github.com/Microsoft/dotnet-apiport/releases) 아직 가지고 있지 않은 경우 다운로드하십시오.
1. .NET Framework 앱을 성공적으로 포팅할 수 있는지 확인합니다(마이그레이션 전에 는 이 방법을 사용할 수 있습니다).
1. 이와 같은 명령줄로 API 포트를 실행합니다.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    인수는 `-f` 분석할 바이너리를 포함하는 경로를 지정합니다. 인수는 `-r` 원하는 출력 파일 형식을 지정합니다. 인수는 `-t` API 사용량을 분석할 .NET 플랫폼을 지정합니다. 이 경우 .NET 코어를 원합니다.

HTML 보고서를 열면 첫 번째 섹션에서는 분석된 모든 바이너리와 대상 플랫폼에서 사용할 수 있는 .NET API의 백분율을 나열합니다. 백분율 자체는 의미가 없습니다. 더 유용한 것은 누락된 특정 API를 확인하는 것입니다. 이렇게 하려면 어셈블리 이름을 선택하거나 개별 어셈블리에 대한 보고서로 아래로 스크롤합니다.

소스 코드를 소유하는 어셈블리에 초점을 맞춥니다. 예를 들어 Bean Trader ApiPort 보고서에는 나열된 바이너리가 많지만 대부분은 NuGet 패키지에 속합니다. `Castle.Windsor`에서는 .NET Core에 없는 일부 System.Web API에 따라 달라지다는 것을 보여 주며 이 API는 이전에 .NET Core를 지원하는 것으로 `Castle.Windsor` 확인했기 때문에 이 문제는 문제가 되지 않습니다. NuGet 패키지는 다른 .NET 플랫폼에서 사용하기 위해 다른 바이너리를 가지는 것이 일반적이므로.NET Framework 버전의 `Castle.Windsor` System.Web API를 사용하는지 여부는 패키지가 .NET 표준 또는 .NET Core(수행하는 항목)를 대상으로 하는 한 관련이 없습니다.

빈 트레이더 샘플을 사용하면 고려해야 할 유일한 바이너리만 **BeanTraderClient이며** 보고서에는 두 개의 .NET API만 누락된 `System.ServiceModel.ClientBase<T>.Close` 것으로 `System.ServiceModel.ClientBase<T>.Open`표시됩니다.

![빈트레이어클라이언트 이식성 보고서](./media/convert-project-from-net-framework/portability-report.png)

WCF 클라이언트 API는 주로 .NET Core에서 지원되므로 이러한 중앙 API에 사용할 수 있는 대안이 있어야 하므로 이러한 문제가 차단될 가능성은 거의 없습니다. 실제로 `System.ServiceModel`.NET Core 표면 영역(사용)을 <https://apisof.net>살펴보면 .NET Core대신 비동기 대안이 있음을 알 수 있습니다.

이 보고서와 이전 NuGet 종속성 분석을 기반으로 Bean Trader 샘플을 .NET Core로 마이그레이션하는 주요 문제가 없어야 합니다. 실제로 마이그레이션을 시작할 다음 단계에 대한 준비가 되었습니다.

## <a name="migrating-the-project-file"></a>프로젝트 파일 마이그레이션

앱에서 새 [SDK 스타일 프로젝트 파일 형식을](../../core/tools/csproj.md)사용하지 않는 경우 .NET Core를 대상으로 하는 새 프로젝트 파일이 필요합니다. 기존 csproj 파일을 바꾸거나 기존 프로젝트를 현재 상태로 유지하려는 경우 .NET Core를 대상으로 하는 새 csproj 파일을 추가할 수 있습니다. 여러 대상을 지정하는 [다중 대상을](../../standard/library-guidance/cross-platform-targeting.md) 가진 단일 SDK 스타일 프로젝트 파일로 .NET Framework `<TargetFrameworks>` 및 .NET Core용 앱 버전을 빌드할 수 있습니다.

새 프로젝트 파일을 만들려면 Visual Studio에서 새 WPF 프로젝트를 `dotnet new wpf` 만들거나 임시 디렉터리의 명령을 사용하여 프로젝트 파일을 생성한 다음 올바른 위치로 복사/이름을 바꿀 수 있습니다. 프로젝트 파일 마이그레이션의 일부를 자동화할 수 있는 커뮤니티에서 만든 도구인 [CsprojToVs2017도](https://github.com/hvanbakel/CsprojToVs2017)있습니다. 이 도구는 유용하지만 마이그레이션의 모든 세부 사항이 올바른지 확인하기 위해 결과를 검토할 사람이 필요합니다. 도구가 최적으로 처리하지 않는 한 가지 특정 영역은 *packages.config* 파일에서 NuGet 패키지를 마이그레이션하는 것입니다. 도구가 여전히 *Packages.config* 파일을 사용하여 NuGet 패키지를 참조하는 프로젝트 파일에서 실행되는 경우 `<PackageReference>` 자동으로 요소로 마이그레이션되지만 최상위 패키지 대신 `<PackageReference>` *모든* 패키지에 대한 요소를 추가합니다. 이 샘플에서 수행한`<PackageReference>` 것처럼 Visual Studio가 있는 요소로 이미 마이그레이션한 경우 이 도구를 사용하여 변환의 나머지 부분을 사용할 수 있습니다. Scott Hanselman이 [csproj 파일 마이그레이션에 대한 블로그 게시물에서](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx)권장하는 것처럼 손으로 이식하는 것은 교육적이며 포트에 몇 가지 프로젝트만 있는 경우 더 나은 결과를 제공합니다. 그러나 수십 또는 수백 개의 프로젝트 파일을 이식하는 경우 [CsprojToVs2017]과 같은 도구가 도움이 될 수 있습니다.

빈 트레이더 샘플에 대한 새 프로젝트 `dotnet new wpf` 파일을 만들려면 임시 디렉토리에서 실행하고 생성된 *.csproj* 파일을 *BeanTraderClient* 폴더로 이동하고 **BeanTraderClient.Core.csproj의**이름을 바꿉니다.

새 프로젝트 파일 형식에는 C# 파일, *resx* 파일 및 디렉터리 에서 찾은 XAML 파일이 자동으로 포함되어 있으므로 프로젝트 파일은 이미 거의 완료되었습니다! 마이그레이션을 완료하려면 이전 프로젝트 파일과 새 프로젝트 파일을 나란히 열고 이전 프로젝트 파일을 살펴보고 이전 프로젝트 파일을 살펴보고 마이그레이션해야 하는 정보가 있는지 확인합니다. 빈 트레이더 샘플 의 경우 다음 항목을 새 프로젝트에 복사해야 합니다.

- 의 `<RootNamespace>` `<AssemblyName>`에서 `<ApplicationIcon>` 및 속성은 모두 복사해야 합니다.

- 또한 Bean Trader `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` 샘플에 AssemblyInfo.cs 파일에 어셈블리 수준 특성(예: `[AssemblyTitle]`)이 포함되어 있으므로 새 프로젝트 파일에 속성을 추가해야 합니다. 기본적으로 새 SDK 스타일 프로젝트는 csproj 파일의 속성을 기반으로 이러한 특성을 자동으로 생성합니다. 이 경우 이러한 일이 발생하지 않도록 하려면(자동 생성된 특성이 AssemblyInfo.cs 특성과 충돌함) `<GenerateAssemblyInfo>`에서 자동 생성된 특성을 사용하지 않도록 설정합니다.

- *resx* 파일은 포함된 리소스로 자동으로 `<Resource>` 포함되지만 이미지와 같은 다른 항목은 포함되지 않습니다. 따라서 이미지 `<Resource>` 및 아이콘 파일을 포함하기 위한 요소를 복사합니다. 새 프로젝트 파일 형식의 송부 패턴 지원을 사용하여 png 참조를 한 `<Resource Include="**\*.png" />`줄로 단순화할 수 있습니다.

- 마찬가지로 `<None>` 항목은 자동으로 포함되지만 기본적으로 출력 디렉토리에 복사되지 않습니다. Bean Trader *프로젝트에는* 비헤이비어 를 사용하여 `PreserveNewest` 출력 디렉토리에 복사된 `<None>` `<None>` 항목이 포함되어 있으므로 이와 같이 해당 파일에 대해 자동으로 채워진 항목을 업데이트해야 합니다.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- Bean Trader 샘플에는 이 파일에 정의된 테마와 악센트가 앱 `Content` 자체에 포함되지 `Page`않고 런타임에 파일의 XAML에서 로드되기 때문에 XAML 파일(Default.Accent.xaml)이 포함되어 있습니다. 그러나 새 프로젝트 시스템에는 XAML 파일이므로 이 파일을 `<Page>`자동으로 포함합니다. 따라서 XAML 파일을 페이지()로`<Page Remove="**\Default.Accent.xaml" />`제거하고 콘텐츠로 추가해야 합니다.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- 마지막으로 모든 요소를 복사하여 `<ItemGroup>` NuGet 참조를 추가합니다. `<PackageReference>` 이전에 NuGet 패키지를 .NET 코어 호환 버전으로 업그레이드하지 않은 경우 이제 패키지 참조가 .NET Core 관련 프로젝트에 있습니다.

이 시점에서 BeanTrader 솔루션에 새 프로젝트를 추가하고 Visual Studio에서 열 수 있어야 합니다. 이 프로젝트는 솔루션 **탐색기에서** `dotnet restore BeanTraderClient.Core.csproj` 올바르게 보이며 패키지를 성공적으로 복원해야 합니다(.NET Framework를 대상으로 사용하는 MahApps.Metro 버전과 관련된 두 가지 경고가 있음).

두 프로젝트 파일을 나란히 유지할 수 있지만(이전 프로젝트를 그대로 빌드하려는 경우 바람직할 수도 있음) 마이그레이션 프로세스가 복잡해집니다(두 프로젝트는 동일한 bin 및 obj 폴더를 사용하려고 합니다). .NET Core 및 .NET Framework 대상모두에 대해 빌드하려는 `<TargetFramework>netcoreapp3.0</TargetFramework>` 경우 새 프로젝트 파일의 속성을 `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>` 대신 바꿀 수 있습니다. 빈 트레이더 샘플의 경우 더 이상 필요하지 않으므로 이전 프로젝트 파일(BeanTraderClient.csproj)을 삭제합니다. 두 프로젝트 파일을 모두 유지하려는 경우 다른 출력 및 중간 출력 경로로 빌드하도록 해야 합니다.

## <a name="fix-build-issues"></a>빌드 문제 해결

포팅 프로세스의 세 번째 단계는 프로젝트를 빌드하는 것입니다. 일부 앱은 프로젝트 파일이 SDK 스타일 프로젝트로 변환되면 이미 성공적으로 빌드됩니다. 앱의 경우, 축하합니다! 4단계로 진행할 수 있습니다. 다른 앱은 .NET Core를 빌드하기 위해 몇 가지 업데이트가 필요합니다. 예를 들어, `dotnet build` 빈 트레이더 샘플 프로젝트에서 실행하려고 하면(또는 Visual Studio에서 빌드) 많은 오류가 있지만 신속하게 수정됩니다.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>System.ServiceModel 참조 및 Microsoft.Windows.호환성

.NET Core에서 사용할 수 있지만 .NET Core 앱 메타패키지에 자동으로 포함되지 않는 API에 대한 일반적인 오류 소스는 누락되었습니다. 이 문제를 해결하려면 `Microsoft.Windows.Compatibility` 패키지를 참조해야 합니다. 호환성 패키지에는 WCF 클라이언트, 디렉터리 서비스, 레지스트리, 구성, ACL API 등과 같은 Windows 데스크톱 앱에서 공통되는 광범위한 API 집합이 포함되어 있습니다.

Bean Trader 샘플을 사용하면 대부분의 빌드 오류는 누락된 <xref:System.ServiceModel> 유형으로 인한 것입니다. 이러한 문제는 필요한 WCF NuGet 패키지를 참조하여 해결할 수 있습니다. WCF 클라이언트 API는 `Microsoft.Windows.Compatibility` 패키지에 있는 API 중 하나이므로 호환성 패키지를 참조하는 것이 더 나은 솔루션입니다(API와 관련된 모든 문제와 호환성 패키지가 사용할 수 있는 WCF 문제에 대한 해결 방법도 해결하기 때문에). 이 `Microsoft.Windows.Compatibility` 패키지는 대부분의 .NET 코어 3.0 WPF 및 WinForms 포팅 시나리오에서 도움이 됩니다. NuGet 참조를 추가한 `Microsoft.Windows.Compatibility`후 , 하나의 빌드 오류만 남아 있습니다!

### <a name="cleaning-up-unused-files"></a>사용하지 않는 파일 정리

자주 발생하는 마이그레이션 문제의 한 가지 유형은 *모든* 소스를 자동으로 포함하는 새 SDK 스타일 프로젝트에서 빌드에 이전에 포함되지 않았던 C# 및 XAML 파일과 관련이 있습니다.

Bean Trader 샘플에 표시되는 다음 빌드 오류는 *OldUnusedViewModel.cs*에서 잘못된 인터페이스 구현을 나타냅니다. 파일 이름은 힌트이지만 검사 시 이 소스 파일이 올바르지 않다는 것을 알 수 있습니다. 원래 .NET Framework 프로젝트에 포함되지 않았기 때문에 이전에는 문제가 발생하지 않았습니다. 디스크에 있었지만 이전 *csproj에* 포함되지 않은 소스 파일은 이제 자동으로 포함됩니다.

이와 같은 일회성 문제의 경우 이전 *csproj와* 비교하여 파일이 필요하지 않은지 확인한 다음 `<Compile Remove="" />` 소스 파일이 더 이상 필요하지 않은 경우 삭제합니다. 이 경우 *OldUnusedViewModel.cs*삭제하는 것이 안전합니다.

이러한 방식으로 제외해야 하는 원본 파일이 많은 경우 프로젝트 파일에서 `<EnableDefaultCompileItems>` 속성을 false로 설정하여 C# 파일의 자동 포함을 비활성화할 수 있습니다. 그런 다음 포함하려는 소스만 빌드하기 위해 이전 프로젝트 파일에서 새 프로젝트 파일로 항목을 복사할 `<Compile Include>` 수 있습니다. 마찬가지로 `<EnableDefaultPageItems>` XAML 페이지의 자동 포함을 해제하는 데 `<EnableDefaultItems>` 사용할 수 있으며 단일 속성으로 둘 다 제어할 수 있습니다.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>멀티 패스 컴파일러에 대한 간략한 설명

빈 트레이더 샘플에서 잘못된 파일을 제거한 후 다시 빌드할 수 있으며 네 가지 오류가 표시됩니다. 전에 는 없었나요? 오류 수가 증가하는 이유는 무엇입니까? C# 컴파일러는 [다중 패스 컴파일러입니다.](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes) 즉, 각 소스 파일을 두 번 거칩니다. 먼저 컴파일러는 각 소스 파일의 메타데이터와 선언만 살펴보고 선언 수준 문제를 식별합니다. 수정한 오류입니다. 그런 다음 코드를 다시 통과하여 C# 소스를 IL로 빌드합니다. 이는 현재 보고 있는 두 번째 오류 집합입니다.

> [!NOTE]
> C# 컴파일러는 [두 번 이상의 패스를](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)수행하지만, 최종 결과는 이와 같은 큰 코드 변경에 대한 컴파일러 오류가 두 가지 파로 오는 경향이 있다는 것입니다.

### <a name="third-party-dependency-fixes-castlewindsor"></a>타사 종속 성 수정 (성.윈저)

일부 마이그레이션 시나리오에서 제기되는 또 다른 종류의 문제는 .NET Framework와 .NET Core 버전의 종속성 간의 API 차이입니다. NuGet 패키지가 .NET Framework 및 .NET 표준 또는 .NET Core를 모두 대상으로 하는 경우에도 다른 .NET 대상에서 사용할 라이브러리가 다를 수 있습니다. 이렇게 하면 패키지가 다양한 .NET 플랫폼을 지원할 수 있으며, 이 경우 다른 구현이 필요할 수 있습니다. 또한 다른 .NET 플랫폼을 대상으로 할 때 라이브러리에 작은 API 차이가 있을 수 있습니다.

빈 트레이더 샘플에 표시되는 다음 오류 집합은 API와 `Castle.Windsor` 관련이 있습니다. .NET 코어 빈 트레이더 프로젝트는 .NET Framework 대상 프로젝트(4.1.1)와 동일한 버전을 `Castle.Windsor` 사용하지만 이 두 플랫폼에 대한 구현은 약간 다릅니다.

이 경우 해결해야 할 다음과 같은 문제가 표시됩니다.

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly`.NET 코어에서 사용할 수 없습니다. 그러나 비슷한 `Classes.FromAssemblyContaining` API를 사용할 수 있으므로 호출을 하는 `Classes.FromThisAssembly()` 형식이 `Classes.FromAssemblyContaining(t)`있는 `t` 위치에 대한 호출로 두 용도를 모두 바꿀 수 있습니다.
1. 마찬가지로, *Bootstrapper.cs* `Castle.Windsor.Installer.FromAssembly`. .NET Core에서 사용할 수 없습니다. 대신 해당 호출을 로 `FromAssembly.Containing(typeof(Bootstrapper))`대체할 수 있습니다.

### <a name="updating-wcf-client-usage"></a>WCF 클라이언트 사용 업데이트

차이점을 `Castle.Windsor` 수정하면 .NET Core Bean Trader 프로젝트의 마지막 남은 `BeanTraderServiceClient` 빌드 오류는 `DuplexClientBase`메서드가 없다는 `Open` 것입니다. 이 마이그레이션 프로세스의 시작 부분에서 .NET 이식성 분석기에서 강조 표시 한 API이기 때문에 이것은 놀라운 일이 아니다. 하지만 `BeanTraderServiceClient` 더 큰 이슈에 관심을 불러일으킵니다. 이 WCF 클라이언트는 [Svcutil.exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구에 의해 자동 생성되었습니다.

**Svcutil에서 생성된 WCF 클라이언트는 .NET 프레임워크에서 사용하기 위한 것입니다.**

svcutil에서 생성된 WCF 클라이언트를 사용하는 솔루션은 .NET Core와 함께 사용하기 위해 .NET 표준 호환 클라이언트를 다시 생성해야 합니다. 이전 클라이언트가 작동하지 않는 주된 이유 중 하나는 WCF 바인딩 및 끝점을 정의하기 위해 앱 구성에 의존하기 때문에 발생합니다. .NET 표준 WCF API는 플랫폼 간(System.Configuration API를 사용할 수 없는 경우)에서 작동할 수 있으므로 .NET Core 및 .NET 표준 시나리오의 WCF 클라이언트는 구성 대신 프로그래밍 방식으로 바인딩 및 끝점을 정의해야 합니다.

실제로 `<system.serviceModel>` app.config 섹션에 종속된 모든 WCF 클라이언트 사용량(Svcutil으로 만든 지 수동으로 만들든 수동으로)을 변경하여 .NET Core에서 작동하려면 변경해야 합니다.

.NET 표준 호환 WCF 클라이언트를 자동으로 생성하는 방법에는 두 가지가 있습니다.

- 이 `dotnet-svcutil` 도구는 Svcutil이 이전에 작업한 방식과 유사한 방식으로 WCF 클라이언트를 생성하는 .NET 도구입니다.
- Visual Studio는 연결된 서비스 기능의 [WCF 웹 서비스 참조](../../core/additional-tools/wcf-web-service-reference-guide.md) 옵션을 사용하여 WCF 클라이언트를 생성할 수 있습니다.

어느 쪽이든 잘 작동합니다. 물론 WCF 클라이언트 코드를 직접 작성할 수도 있습니다. 이 샘플에서는 Visual Studio 커넥티드 서비스 기능을 사용하기로 결정했습니다. 이렇게 하려면 Visual Studio의 솔루션 탐색기에서 *BeanTraderClient.Core* 프로젝트를 마우스 오른쪽 단추로 클릭하고**연결된 서비스** **추가를** > 선택합니다. 다음으로 WCF 웹 서비스 참조 공급자를 선택합니다. 이렇게 하면 백엔드 Bean Trader 웹 서비스의 주소(로컬로`localhost:8080` 서버를 실행하는 경우)와 생성된 형식이 사용해야 하는 네임스페이스(BeanTrader.Service, 예:)를 지정할 수 있는 대화 상자가 나타납니다.**BeanTrader.Service**

![WCF 웹 서비스 참조 연결된 서비스 대화 상자](./media/convert-project-from-net-framework/connected-service-dialog.png)

**완료** 단추를 선택하면 프로젝트에 새 연결된 서비스 노드가 추가되고 Bean Trader 서비스에 액세스하기 위한 새 .NET 표준 WCF 클라이언트가 포함된 해당 노드 아래에 Reference.cs 파일이 추가됩니다. 해당 파일의 `GetEndpointAddress` 메서드 `GetBindingForEndpoint` 또는 메서드를 보면 이제 바인딩 및 끝점이 앱 구성을 통해서가 아니라 프로그래밍 방식으로 생성되는 것을 볼 수 있습니다. '연결된 서비스 추가' 기능은 프로젝트 파일의 일부 System.ServiceModel 패키지에 대한 참조를 추가할 수 있으며, 필요한 모든 WCF 패키지는 Microsoft.Windows.Compatibility을 통해 포함되어 있기 때문에 필요하지 않습니다. csproj를 확인하여 추가 System.ServiceModel `<PackageReference>` 항목이 추가되었는지 확인하고, 그렇다면 제거합니다.

우리의 프로젝트에는 현재 새로운 WCF 클라이언트 클래스가 있습니다 *(Reference.cs)* 이전 클래스 (BeanTrader.cs)도 있습니다. 이 시점에서 두 가지 옵션이 있습니다.

- 원래 .NET Framework 프로젝트를 빌드할 수 있도록 하려면 (새 .NET Core 대상 프로젝트와 함께) .NET Core 프로젝트의 csproj 파일에 `<Compile Remove="BeanTrader.cs" />` 항목을 사용 하 여 앱의 .NET 프레임 워크 및 .NET Core 버전 이 다른 WCF 클라이언트를 사용 하도록 할 수 있습니다. 이렇게 하면 기존 .NET Framework 프로젝트를 변경하지 않고 두는 이점이 있지만 생성된 WCF 클라이언트를 사용하는 코드가 .NET Framework 프로젝트보다 .NET Core 사례에서 약간 달라야 `#if` 할 수 있으므로 .NET Core를 위해 빌드될 때 일부 WCF 클라이언트 사용량(예: 클라이언트 만들기)을 조건부로 컴파일하기 위해 지시문을 사용해야 합니다.

- 반면에 기존 .NET Framework 프로젝트의 일부 코드 변동이 허용되는 경우 *모두 BeanTrader.cs* 제거할 수 있습니다. 새 WCF 클라이언트는 .NET 표준용으로 빌드되므로 .NET Core 및 .NET Framework 시나리오모두에서 작동합니다. .NET Core 외에 .NET Framework를 빌드하는 경우(다중 타겟팅 또는 두 개의 csproj 파일을 사용하여) 두 대상 모두에 대해 이 새 *Reference.cs* 파일을 사용할 수 있습니다. 이 방법은 두 개의 서로 다른 WCF 클라이언트를 지원하기 위해 코드를 분기할 필요가 없다는 장점이 있습니다. 동일한 코드가 모든 곳에서 사용됩니다. 단점은 (아마도 안정) .NET Framework 프로젝트를 변경해야 한다는 것입니다.

Bean Trader 샘플의 경우 마이그레이션이 더 쉬워지면 원래 프로젝트를 작게 변경할 수 있으므로 다음 단계를 수행하여 WCF 클라이언트 사용량을 조정합니다.

01. 솔루션 탐색기의 '기존 항목 추가' 컨텍스트 메뉴를 사용하여 .NET 프레임워크 *BeanTraderClient.csproj* 프로젝트에 새 Reference.cs 파일을 추가합니다. C# 파일을 복사하는 것이 아니라 두 프로젝트에서 동일한 파일을 사용할 수 있도록 '링크'를 추가해야 합니다. 단일 csproj(다중 타겟팅 사용)를 사용하여 .NET Core 및 .NET Framework를 모두 빌드하는 경우 이 단계가 필요하지 않습니다.

01. *BeanTrader.cs*삭제합니다.

01. 새 WCF 클라이언트는 이전 클라이언트와 비슷하지만 생성된 코드의 여러 네임스페이스는 다릅니다. 따라서 WCF 클라이언트 형식이 BeanTrader.Model 대신 BeanTrader.Model 또는 네임스페이스 없이 BeanTrader.Service(또는 선택한 네임스페이스 이름)에서 사용되도록 프로젝트를 업데이트해야 합니다. *BeanTraderClient.Core.csproj를* 구축하면 이러한 변경이 필요한 위치를 식별하는 데 도움이 됩니다. C# 및 XAML 소스 파일모두에서 수정이 필요합니다.

01. 마지막으로 `BeanTraderServiceClient` 형식에 사용할 수 있는 생성자가 변경되어 *BeanTraderServiceClientFactory.cs* 오류가 있음을 알 수 있습니다. 예전에는 `InstanceContext` `CallbackHandler` `Castle.Windsor` 인수를 제공할 수 있었습니다(IoC 컨테이너에서 를 사용하여 만든). 새 생성자는 새 `CallbackHandler`생성자 입니다. 그러나 기본 형식에는 원하는 `BeanTraderServiceClient`것과 일치하는 생성자가 있습니다. 자동 생성된 WCF 클라이언트 코드는 모두 부분 클래스에 존재하므로 쉽게 확장할 수 있습니다. 이렇게 하려면 *BeanTraderServiceClient.cs라는* 새 파일을 만든 다음 BeanTrader.Service 네임스페이스를 사용하여 같은 이름의 부분 클래스를 만듭니다. 그런 다음 여기에 표시된 대로 부분 형식에 하나의 생성기를 추가합니다.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

이러한 변경 사항을 통해 Bean Trader 샘플은 이제 새로운 .NET 표준 호환 WCF 클라이언트를 사용하고 `Open` *대신* 사용할 `await OpenAsync` TradingService.cs 통화를 변경하는 최종 수정을 할 수 있습니다.

WCF 문제가 해결되면 빈 트레이더 샘플의 .NET 코어 버전이 깔끔하게 구축됩니다!

## <a name="runtime-testing"></a>런타임 테스트

프로젝트가 .NET Core에 대해 깔끔하게 빌드되는 즉시 마이그레이션 작업이 수행되지 않는다는 사실을 잊기 쉽습니다. 이식된 앱을 테스트할 시간도 두는 것이 중요합니다. 빌드가 성공적으로 완료되면 특히 .NET Framework를 대상으로 하는 패키지를 사용하는 경우 앱이 예상대로 실행되고 작동하는지 확인합니다.

의 포팅 콩 상인 응용 프로그램을 시작하고 무슨 일이 일어나는지 보자. 응용 프로그램은 다음과 같은 예외로 실패하기 전에 멀리 얻을하지 않습니다.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

물론 이것은 의미가 있습니다. WCF는 더 이상 앱 구성을 사용하지 않으므로 app.config 파일의 이전 system.serviceModel 섹션을 제거해야 합니다. 업데이트된 WCF 클라이언트에는 코드에 동일한 정보가 모두 포함되어 있으므로 구성 섹션이 더 이상 필요하지 않습니다. app.config에서 WCF 끝점을 구성할 수 있도록 하려면 앱 설정으로 추가하고 WCF 클라이언트 코드를 업데이트하여 구성에서 WCF 서비스 끝점을 검색할 수 있습니다.

*app.config의*system.serviceModel 섹션을 제거한 후 앱이 시작되지만 사용자가 로그인할 때 다른 예외를 제외하고 실패합니다.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

지원되지 않는 `Func<T>.BeginInvoke`API는 . [dotnet/corefx#5940에서](https://github.com/dotnet/corefx/issues/5940)설명한 대로 .NET Core는 `BeginInvoke` `EndInvoke` 기본 원격 종속성으로 인해 대리자 형식에 대한 메서드와 메서드를 지원하지 않습니다. 이 문제와 수정 사항은 [마이그레이션 Delegate.BeginInvoke .NET Core](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) 블로그 게시물에 대한 호출에 대해 자세히 `BeginInvoke` `EndInvoke` 설명하지만 요점은 `Task.Run` 호출을 대체해야 한다는 것입니다(또는 가능한 경우 비동기 대안). 여기에 일반적인 솔루션을 적용하면 `BeginInvoke` 호출을 `Task.Run`에서 `Invoke` 시작된 호출로 대체할 수 있습니다.

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

사용량을 `BeginInvoke` 제거한 후 .NET Core에서 Bean Trader 앱이 성공적으로 실행됩니다!

![.NET 코어에서 실행되는 빈 트레이더](./media/convert-project-from-net-framework/running-on-core.png)

모든 앱은 서로 다르므로 사용자 고유의 앱을 .NET Core로 마이그레이션하는 데 필요한 특정 단계는 다양합니다. 그러나 바라건대 콩 상인 샘플은 일반적인 워크 플로우와 예상 할 수있는 문제의 유형을 보여줍니다. 또한 이 문서의 길이에도 불구하고 .NET Core에서 작동하도록 하기 위해 Bean Trader 샘플에 필요한 실제 변경 사항은 상당히 제한적이었습니다. 많은 앱이 이와 같은 방식으로 .NET Core로 마이그레이션됩니다. 코드 변경이 필요 없거나 제한되지 않습니다.
