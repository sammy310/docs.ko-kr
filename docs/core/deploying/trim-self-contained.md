---
title: 자체 포함 애플리케이션 트리밍
description: 자체 포함 앱을 트리밍하여 크기를 줄이는 방법을 알아봅니다. .NET Core는 게시된 자체 포함 앱과 런타임을 묶고, 일반적으로 필요한 수준보다 더 많은 런타임을 포함합니다.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 9c2994c98a2ebe6f45b056256c2bda28db017fbf
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465483"
---
# <a name="trim-self-contained-deployments-and-executables"></a>자체 포함 배포 및 실행 파일 트리밍

[프레임워크 종속 배포 모델](index.md#publish-framework-dependent)은 .NET 도입 이후 가장 성공적인 배포 모델입니다. 이 시나리오에서 애플리케이션 개발자는 애플리케이션과 타사 어셈블리만 번들하고 .NET 런타임 및 프레임워크 라이브러리는 클라이언트 머신에서 사용할 수 있을 것으로 예상합니다. 이 배포 모델은 .NET Core에서도 주요 모델로 계속 사용되지만 프레임워크 종속 모델이 최적이 아닌 몇 가지 시나리오가 있습니다. 다른 방법은 .NET Core 런타임과 프레임워크가 애플리케이션 및 타사 어셈블리와 함께 번들되는 [자체 포함 애플리케이션](index.md#publish-self-contained)을 게시하는 것입니다.

트리밍된 자체 포함 배포 모델은 배포 크기를 줄이도록 최적화된 특수 버전의 자체 포함 배포 모델입니다. 배포 크기 최소화는 Blazor 애플리케이션과 같은 일부 클라이언트 쪽 시나리오의 중요한 요구 사항입니다. 애플리케이션 복잡성에 따라 프레임워크 어셈블리의 하위 집합만 참조되며 각 어셈블리 내 코드의 하위 집합은 애플리케이션 실행에 필요합니다. 사용되지 않는 라이브러리 부분은 필요가 없으며 패키지된 애플리케이션에서 트리밍할 수 있습니다.

그러나 다양한 문제 코드 패턴을 안정적으로 분석할 수 없다는 점에서(주로 리플렉션 사용을 중심으로 함) 애플리케이션의 빌드 시간 분석으로 인해 런타임에 오류가 발생할 위험이 있습니다. 안정성을 보장할 수 없으므로 이 배포 모델은 미리 보기 기능으로 제공됩니다.

빌드 시간 분석 엔진은 문제가 있는 코드 패턴의 개발자에게 필요한 다른 코드를 검색하도록 경고합니다. 포함할 다른 항목을 트리머에 알리도록 특성을 사용하여 코드에 주석을 달 수 있습니다. [소스 생성기](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md)를 사용하여 많은 리플렉션 패턴을 빌드 시간 코드 생성으로 바꿀 수 있습니다.

애플리케이션의 트리밍 모드는 `TrimMode` 설정으로 구성됩니다. 기본값은 `copyused`이며 참조된 어셈블리를 애플리케이션에서 번들로 묶습니다. `link` 값은 Blazor WebAssembly 애플리케이션에서 사용되며 어셈블리 내에서 사용되지 않는 코드를 트리밍합니다. 트리밍 분석 경고는 전체 종속성 분석이 불가능한 코드 패턴에 대한 정보를 제공합니다. 해당 경고는 기본적으로 표시되지 않으며, `SuppressTrimAnalysisWarnings` 플래그를 `false`로 지정하여 켤 수 있습니다. 사용 가능한 트리밍 옵션에 관한 자세한 내용은 [트리밍 옵션](trimming-options.md)을 참조하세요.

> [!NOTE]
> 트리밍은 .NET Core 3.1, 5.0의 실험적 기능이며 ‘게시된 자체 포함 애플리케이션에만’ 사용할 수 있습니다.

## <a name="prevent-assemblies-from-being-trimmed"></a>어셈블리가 트리밍되지 않도록 방지

트리밍 기능에서 참조를 검색하지 못하는 시나리오가 있습니다. 예를 들어 애플리케이션 또는 애플리케이션에서 참조하는 라이브러리가 런타임 어셈블리에서 리플렉션을 사용하는 경우 어셈블리는 직접 참조되지 않습니다. 트리밍은 이 간접 참조를 인식할 수 없으며 게시된 폴더에서 라이브러리를 제외합니다.

코드에서 리플렉션을 통해 어셈블리를 간접적으로 참조하는 경우 `<TrimmerRootAssembly>` 설정으로 어셈블리가 트리밍되지 않도록 할 수 있습니다. 다음 예제에서는 `System.Security` 어셈블리라는 어셈블리가 트리밍되지 않게 하는 방법을 보여 줍니다.

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>앱 트리밍 - CLI

[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 애플리케이션을 트리밍합니다. 앱을 게시할 때 다음 속성을 설정합니다.

- 특정 런타임을 위해 자체 포함 앱으로 게시: `-r win-x64`
- 트리밍 사용: `/p:PublishTrimmed=true`

다음 예제에서는 Windows용 앱을 자체 포함으로 게시하고 출력을 트리밍합니다.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

다음 예제에서는 어셈블리 내의 사용되지 않는 코드가 트리밍되고 트리머 경고가 사용되는 적극적인 트리밍 모드로 앱을 게시합니다.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.

## <a name="trim-your-app---visual-studio"></a>앱 트리밍 - Visual Studio

Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.

01. **솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다. **게시...** 를 선택합니다.

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.

01. **편집**을 선택합니다.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. **프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.

    - **배포 모드**를 **자체 포함**으로 설정합니다.
    - **대상 런타임**을 게시할 플랫폼으로 설정합니다.
    - **사용하지 않는 어셈블리 트리밍(미리 보기)** 을 선택합니다.

    **저장**을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="배포 모드, 대상 런타임 및 사용하지 않는 어셈블리 트리밍 옵션이 강조 표시된 프로필 설정 대화 상자.":::

01. **게시**를 선택하여 트리밍된 앱을 게시합니다.

자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.

## <a name="trim-your-app---visual-studio-for-mac"></a>앱 트리밍 - Mac용 Visual Studio

Mac용 Visual Studio는 게시하는 동안 앱을 트리밍하는 옵션을 제공하지 않습니다. [앱 트리밍 - CLI](#trim-your-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다. 자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.

## <a name="see-also"></a>참조

- [.NET Core 애플리케이션 배포](index.md).
- [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).
- [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).
- [dotnet publish 명령](../tools/dotnet-publish.md).
