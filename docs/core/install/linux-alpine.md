---
title: Alpine에 .NET 설치 - .NET
description: Alpine에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506837"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Alpine에 .NET SDK 또는 .NET 런타임 설치

이 문서에서는 Alpine에 .NET을 설치하는 방법을 설명합니다. Alpine 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다. 그러나 이러한 지침은 지원되지 않더라도 해당 버전에서 .NET을 실행하는 데 도움이 될 수 있습니다.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Alpine용 설치 관리자는 없습니다. [설치 스크립트](#scripted-install)를 사용하거나 [수동 설치](#manual-install) 지침을 따라야 합니다.

## <a name="supported-distributions"></a>지원되는 배포

다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Alpine 버전의 목록입니다. 이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Alpine 버전이 지원 종료에 도달](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)할 때까지 계속 지원됩니다.

- ✔️는 Alpine 또는 .NET 버전이 계속 지원됨을 나타냅니다.
- ❌는 Alpine 또는 .NET 버전이 해당 Alpine 릴리스에서 지원되지 않음을 나타냅니다.
- Alpine 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.

| Alpine  | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|-------- |---------------|---------------|----------------|
| ✔️ 3.12 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.11 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.10 | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.9  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.8  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |

다음 .NET 버전은 더 이상 지원되지 않습니다. 이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>종속성

Alpine Linux에서 .NET을 사용하려면 다음 종속성이 설치되어 있어야 합니다.

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

- [자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기](../tutorials/with-visual-studio-code.md)
