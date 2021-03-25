---
title: Alpine에 .NET 설치 - .NET
description: Alpine에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 19cae3c6237dc9f1a23087ec654e8f24ca13cd66
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653441"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Alpine에 .NET SDK 또는 .NET 런타임 설치

이 문서에서는 Alpine에 .NET을 설치하는 방법을 설명합니다. Alpine 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다. 그러나 이러한 지침은 지원되지 않더라도 해당 버전에서 .NET을 실행하는 데 도움이 될 수 있습니다.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a>설치

설치 프로그램은 Alpine Linux에서 사용할 수 없습니다. 다음 방법 중 하나를 사용하여 .NET을 설치해야 합니다.

- [Snap 패키지](linux-snap.md)
- [_install-dotnet.sh_ 스크립트를 통한 설치](linux-scripted-manual.md#scripted-install)
- [수동 이진 추출](linux-scripted-manual.md#manual-install)

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

- bash
- icu-libs
- krb5-libs
- libgcc
- libgdiplus(.NET 앱에 *System.Drawing.Common* 어셈블리가 필요한 경우)
- libintl
- libssl1.1(Alpine v3.9 이상)
- libssl1.0(Alpine v3.8 이하)
- libstdc++
- zlib

필요한 요구 사항을 설치하려면 다음 명령을 실행합니다.

```bash
apk add bash icu-libs krb5-libs libgcc libintl libssl1.1 libstdc++ zlib
```

**libgdiplus** 를 설치하려면 리포지토리를 지정해야 할 수 있습니다.

```bash
apk add libgdiplus --repository https://dl-3.alpinelinux.org/alpine/edge/testing/
```

## <a name="next-steps"></a>다음 단계

- [.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법](../tools/enable-tab-autocomplete.md)
- [자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기](../tutorials/with-visual-studio-code.md)
