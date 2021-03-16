---
title: Fedora에 .NET 설치 - .NET
description: Fedora에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 02/17/2021
ms.openlocfilehash: efaad4788db2200b1a47f9b4ae2414730588c6ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255761"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a>Fedora에 .NET SDK 또는 .NET 런타임 설치

.NET은 Fedora에서 지원되며 이 문서에서는 Fedora에 .NET을 설치하는 방법을 설명합니다. Fedora 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

패키지 관리자 없이 .NET을 설치하는 방법에 대한 자세한 내용은 다음 문서 중 하나를 참조하세요.

- [Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치.](linux-snap.md)
- [스크립트를 사용하여 .NET SDK 또는 .NET 런타임 설치.](linux-scripted-manual.md#scripted-install)
- [수동으로 .NET SDK 또는 .NET 런타임 설치.](linux-scripted-manual.md#manual-install)

## <a name="install-net-50"></a>.NET 5.0 설치

Fedora의 기본 패키지 리포지토리에서 사용할 수 있는 .NET의 최신 버전은 .NET 5.0입니다.

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a>.NET Core 3.1 설치

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a>지원되는 배포

다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Fedora 버전의 목록입니다. 이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Fedora 버전이 지원 종료에 도달](https://fedoraproject.org/wiki/End_of_life)할 때까지 계속 지원됩니다.

- ✔️는 Fedora 또는 .NET 버전이 계속 지원됨을 나타냅니다.
- ❌는 Fedora 또는 .NET 버전이 해당 Fedora 릴리스에서 지원되지 않음을 나타냅니다.
- Fedora 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.

| .NET 버전  | Fedora 33 ✔️ | 32 ✔️ | 31 ❌ | 30 ❌ | 29 ❌ | 28 ❌ | 27 ❌ |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| .NET 5.0      | ✔️        | ✔️ | ❌|❌ |❌ |❌  |❌ |
| .NET Core 3.1 | ✔️        | ✔️ | ✔️|✔️ |✔️ |❌  |❌ |
| .NET Core 2.1 | ✔️        | ✔️ | ✔️|✔️ |✔️ |✔️  |✔️ |

다음 .NET 버전은 더 이상 지원되지 않습니다. 이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>미리 보기 버전 제거

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a>종속성

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a>이전 배포판에 설치

이전 버전의 Fedora에는 기본 패키지 리포지토리의 .NET Core가 포함되어 있지 않습니다. [Snap](linux-snap.md) 또는 [_dotnet-install.sh_ 스크립트](linux-scripted-manual.md#scripted-install)를 통해 .NET을 설치하거나 Microsoft의 리포지토리를 사용하여 .NET을 설치할 수 있습니다.

01. 먼저 Microsoft 서명 키를 신뢰할 수 있는 키 목록에 추가합니다.

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. 그런 다음 Microsoft 패키지 리포지토리를 추가합니다. 리포지토리의 소스는 Fedora의 버전을 기반으로 합니다.

    | Fedora 버전 | 패키지 리포지토리 |
    | -------------- | ------- |
    | 31             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | 30             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | 29             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | 28             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | 27             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a>다른 버전을 설치하는 방법

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>패키지 관리자 문제 해결

이 섹션에서는 패키지 관리자를 사용하여 .NET 또는 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.

### <a name="unable-to-find-package"></a>패키지를 찾을 수 없음

패키지 관리자 없이 .NET을 설치하는 방법에 대한 자세한 내용은 다음 문서 중 하나를 참조하세요.

- [Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치.](linux-snap.md)
- [스크립트를 사용하여 .NET SDK 또는 .NET 런타임 설치.](linux-scripted-manual.md#scripted-install)
- [수동으로 .NET SDK 또는 .NET 런타임 설치.](linux-scripted-manual.md#manual-install)

### <a name="failed-to-fetch"></a>가져오지 못함

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a>다음 단계

- [.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법](../tools/enable-tab-autocomplete.md)
- [자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기](../tutorials/with-visual-studio-code.md)
