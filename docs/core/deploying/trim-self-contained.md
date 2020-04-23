---
title: 자체 포함 애플리케이션 트리밍
description: 자체 포함 앱을 트리밍하여 크기를 줄이는 방법을 알아봅니다. .NET Core는 게시된 자체 포함 앱과 런타임을 묶고, 일반적으로 필요한 수준보다 더 많은 런타임을 포함합니다.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242920"
---
# <a name="trim-self-contained-deployments-and-executables"></a>자체 포함 배포 및 실행 파일 트리밍

자체 포함 애플리케이션을 게시하면 .NET Core 런타임이 애플리케이션과 함께 제공됩니다. 이렇게 묶음으로써 패키지된 애플리케이션에 상당한 양의 콘텐츠가 추가됩니다. 애플리케이션 배포와 관련하여 크기는 종종 중요한 요소입니다. 패키지 애플리케이션의 크기를 가능한 한 작게 유지하는 것은 일반적으로 애플리케이션 개발자의 목표입니다.

애플리케이션의 복잡성에 따라 런타임의 하위 집합만 애플리케이션 실행에 필요합니다. 사용되지 않는 이러한 런타임 부분은 필요 없으며 패키지된 애플리케이션에서 트리밍해도 됩니다.

트리밍 기능은 애플리케이션 이진 파일을 검사하여 필요한 런타임 어셈블리의 그래프를 발견하고 작성하는 방식으로 작동합니다. 참조되지 않는 나머지 런타임 어셈블리는 제외됩니다.

> [!NOTE]
> 트리밍은 .NET Core 3.1의 실험적 기능이며 ‘게시된 자체 포함 애플리케이션에만’ 사용할 수 있습니다. 

## <a name="prevent-assemblies-from-being-trimmed"></a>어셈블리가 트리밍되지 않도록 방지

트리밍 기능에서 참조를 검색하지 못하는 시나리오가 있습니다. 예를 들어 애플리케이션 또는 애플리케이션에서 참조하는 라이브러리가 런타임 어셈블리에서 리플렉션을 사용하는 경우 어셈블리는 직접 참조되지 않습니다. 트리밍은 이 간접 참조를 인식할 수 없으며 게시된 폴더에서 라이브러리를 제외합니다.

코드에서 리플렉션을 통해 어셈블리를 간접적으로 참조하는 경우 `<TrimmerRootAssembly>` 설정으로 어셈블리가 트리밍되지 않도록 할 수 있습니다. 다음 예제에서는 `System.Security` 어셈블리라는 어셈블리가 트리밍되지 않게 하는 방법을 보여 줍니다.

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>앱 트리밍 - CLI

[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 애플리케이션을 트리밍합니다. 앱을 게시하는 경우 다음 세 가지 설정을 지정합니다.

- 자체 포함으로 게시: `--self-contained true`
- 단일 파일 게시 사용 안 함: `-p:PublishSingleFile=false`
- 트리밍 사용: `p:PublishTrimmed=true`

다음 예제에서는 Windows 10용 앱을 자체 포함으로 게시하고 출력을 트리밍합니다.

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
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
