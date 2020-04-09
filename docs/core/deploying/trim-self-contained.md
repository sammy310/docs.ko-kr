---
title: 자체 포함 애플리케이션 트리밍
description: 자체 포함 앱을 트리밍하여 크기를 줄이는 방법을 알아봅니다. .NET Core는 게시된 자체 포함 앱과 런타임을 묶고, 일반적으로 필요한 수준보다 더 많은 런타임을 포함합니다.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665622"
---
# <a name="trim-self-contained-deployments-and-executables"></a>자체 포함 배포 및 실행 파일 트리밍

자체 포함 애플리케이션을 게시하면 .NET Core 런타임이 애플리케이션과 함께 제공됩니다. 이렇게 묶음으로써 패키지된 애플리케이션에 상당한 양의 콘텐츠가 추가됩니다.

애플리케이션 배포와 관련하여 크기는 종종 중요한 요소입니다. 패키지 애플리케이션의 크기를 가능한 한 작게 유지하는 것은 일반적으로 애플리케이션 개발자의 목표입니다.

애플리케이션의 복잡성에 따라 런타임의 하위 집합만 애플리케이션 실행에 필요합니다. 사용되지 않는 이러한 런타임 부분은 필요 없으며 패키지된 애플리케이션에서 트리밍해도 됩니다.

> [!NOTE]
> 트리밍은 .NET Core 3.1의 실험적 기능이며 ‘게시된 자체 포함 애플리케이션에만’ 사용할 수 있습니다. 

## <a name="trim-your-application"></a>애플리케이션 트리밍

다음 예제에서는 [dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 애플리케이션을 트리밍하는 방법을 보여 줍니다.

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

트리밍 기능은 애플리케이션 이진 파일을 검사하여 필요한 런타임 어셈블리의 그래프를 발견하고 작성하는 방식으로 작동합니다. 참조되지 않는 나머지 런타임 어셈블리는 트리밍됩니다.

## <a name="trimming-issues-when-using-reflection"></a>리플렉션을 사용할 때의 트리밍 문제

트리밍 기능에서 참조를 검색하지 못하는 시나리오가 있습니다. 예를 들어 리플렉션을 사용하는 애플리케이션에서 어셈블리에 대한 종속성이 런타임에만 알려지므로 이 문제가 발생할 수 있습니다.

리플렉션 사용이 직접 참조되지 않는 런타임 어셈블리에 의존하는 경우에만 트리밍이 문제가 됩니다. 애플리케이션 코드가 리플렉션을 직접 사용하지 않을 수도 있지만 참조하는 타사 어셈블리는 사용하고 있을 수 있다는 점을 기억하세요.

코드가 리플렉션을 통해 API를 참조하고 있고 링커가 이 API가 포함된 어셈블리를 트리밍하는 것을 원하지 않는 경우 트리밍 프로세스에서 어셈블리를 제외하도록 프로젝트 파일을 수정할 수 있습니다. 다음 예제에서는 `System.Security`라는 어셈블리가 트리밍되지 않게 하는 방법을 보여 줍니다.

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a>참조

- [.NET Core 애플리케이션 배포](index.md)
