---
title: Alpine에 .NET Core 설치 - .NET Core
description: Alpine에 .NET Core SDK 및 .NET Core 런타임을 설치하는 다양한 방법을 설명합니다.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 0efe3bbacbe573b77eae8818ea29b5a3867e4570
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619522"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a>Alpine에 .NET Core SDK 또는 .NET Core 런타임 설치

이 문서에서는 Alpine에 .NET Core를 설치하는 방법을 설명합니다. Alpine 버전의 지원이 종료되면 해당 버전에서는 .NET Core가 더 이상 지원되지 않습니다. 그러나, 이 문서의 지침은 지원되지 않더라도 해당 버전에서 .NET Core를 실행하는 데 도움이 될 수 있습니다.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Alpine용 설치 관리자는 없습니다. [설치 스크립트](#scripted-install)를 사용하거나 [수동 설치](#manual-install) 지침을 따라야 합니다.

## <a name="supported-distributions"></a>지원되는 배포

다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Alpine 버전의 목록입니다. 이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 각 버전의 [Alpine이 지원 종료에 도달](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)할 때까지 지원됩니다.

- ✔️는 Alpine 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.
- ❌는 Alpine 또는 .NET Core 버전이 해당 Alpine 릴리스에서 지원되지 않음을 나타냅니다.
- Alpine 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET의 조합이 지원됨을 의미합니다.

| Alpine                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 미리 보기 |
|--------------------------|---------------|---------------|----------------|
| ✔️ 3.12  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ✔️ 3.11  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ✔️ 3.10  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ✔️ 3.9   | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ❌ 3.8   | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |

다음 .NET Core 버전은 더 이상 지원되지 않습니다. 이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>종속성

Alpine Linux에서 .NET Core를 사용하려면 다음 종속성이 설치되어 있어야 합니다.

- icu-libs
- krb5-libs
- libgcc
- libintl
- libssl1.1(Alpine v3.9 이상)
- libssl1.0(Alpine v3.8 이하)
- libstdc++
- zlib

## <a name="scripted-install"></a>스크립팅된 설치

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>수동 설치

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>다음 단계

- [자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기
