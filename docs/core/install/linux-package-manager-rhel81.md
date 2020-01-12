---
title: Linux RHEL 8.1에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 8.1에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714385"
---
# <a name="rhel-81-package-manager---install-net-core"></a>RHEL 8.1 패키지 관리자 - .NET Core 설치

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

이 문서에서는 패키지 관리자를 사용하여 RHEL 8.1에 .NET Core를 설치하는 방법을 설명합니다. RHEL 8.1에서는 아직 .NET Core 3.1을 사용할 수 없습니다.

> [!NOTE]
> RHEL 8.0은 .NET Core 3.0을 포함하지 않습니다. 명령 `yum upgrade`를 사용하여 RHEL 8.1로 업그레이드하세요.

## <a name="register-your-red-hat-subscription"></a>Red Hat 구독 등록

RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다. 아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.

## <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다. 터미널에서 다음 명령을 실행합니다.

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a>ASP.NET Core 런타임 설치

구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다. 터미널에서 다음 명령을 실행합니다.

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a>참조

- [Using .NET Core 3.0 on Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)(Red Hat Enterprise Linux 8에서 .NET Core 3.0 사용)
