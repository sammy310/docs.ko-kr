---
title: RHEL에 .NET 설치 - .NET
description: RHEL에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 0b6138185bfd3e2f50c1b31e82779165715a5b6e
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851642"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a>RHEL에 .NET SDK 또는 .NET 런타임 설치

.NET은 RHEL에서 지원됩니다. 이 문서에서는 RHEL에 .NET을 설치하는 방법을 설명합니다.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Red Hat 구독 등록

RHEL의 Red Hat에서 .NET을 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다. 아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net/5.0/)를 참조하세요.

## <a name="supported-distributions"></a>지원되는 배포

다음 표는 RHEL 7과 RHEL 8에서 현재 지원되는 .NET 릴리스의 목록입니다. 이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 RHEL 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.

- ✔️는 RHEL 또는 .NET 버전이 계속 지원됨을 나타냅니다.
- ❌는 RHEL 또는 .NET 버전이 해당 RHEL 릴리스에서 지원되지 않음을 나타냅니다.
- RHEL 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.

| RHEL                     | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-)        | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](#rhel-7--net-50) | ✔️ 2.1        | ✔️ [3.1](#rhel-7--net-core-31)        | ✔️ [5.0](#rhel-7--net-50) |

다음 .NET 버전은 더 이상 지원되지 않습니다. 이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>미리 보기 버전 제거

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a>다른 버전을 설치하는 방법

.NET의 다른 릴리스를 설치하는 데 필요한 단계에 대해서는 [.NET용 Red Hat 설명서](https://access.redhat.com/documentation/net/5.0/)를 참조하세요.

## <a name="rhel-8-"></a>RHEL 8 ✔️

.NET은 RHEL 8의 AppStream 리포지토리에 포함되어 있습니다.

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a>RHEL 7 ✔️ .NET 5.0

다음 명령은 `scl-utils` 패키지를 설치합니다.

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>SDK 설치

.NET SDK를 사용하면 .NET으로 앱을 개발할 수 있습니다. .NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. .NET SDK를 설치하려면 다음 명령을 실행합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet50`을 영구적으로 사용 설정하는 것을 권장하지 않습니다. `rh-dotnet`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a>런타임 설치

.NET 런타임을 사용하면 런타임을 포함하지 않았던 .NET으로 만든 앱을 실행할 수 있습니다. 아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다. 터미널에서 다음 명령을 실행합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet50`을 영구적으로 사용 설정하는 것을 권장하지 않습니다. `rh-dotnet50`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.

```bash
source scl_source enable rh-dotnet50
```

ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET 런타임을 설치할 수 있습니다. 위 명령에서 `rh-dotnet50-aspnetcore-runtime-5.0`을 `rh-dotnet50-dotnet-runtime-5.0`으로 바꿉니다.

## <a name="rhel-7--net-core-31"></a>RHEL 7 ✔️ .NET Core 3.1

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

다음 명령은 `scl-utils` 패키지를 설치합니다.

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>SDK 설치

.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다. .NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. .NET Core SDK를 설치하려면 다음 명령을 실행합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31`을 영구적으로 사용 설정하는 것을 권장하지 않습니다. 예를 들어 `rh-dotnet31`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다. 이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다. `rh-dotnet`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a>런타임 설치

.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다. 아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다. 터미널에서 다음 명령을 실행합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31`을 영구적으로 사용 설정하는 것을 권장하지 않습니다. 예를 들어 `rh-dotnet31`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다. 이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다. `rh-dotnet31`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.

```bash
source scl_source enable rh-dotnet31
```

ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `rh-dotnet31-aspnetcore-runtime-3.1`을 `rh-dotnet31-dotnet-runtime-3.1`로 바꿉니다.

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>종속성

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a>스크립팅된 설치

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>수동 설치

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>다음 단계

- [자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기](../tutorials/with-visual-studio-code.md)
