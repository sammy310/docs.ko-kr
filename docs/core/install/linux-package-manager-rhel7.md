---
title: Linux RHEL 7에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 7에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: d1f1372b32c7b2471a96492d48aab5533dadb64a
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134211"
---
# <a name="rhel-7-package-manager---install-net-core"></a>RHEL 7 패키지 관리자 - .NET Core 설치

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

이 문서에서는 패키지 관리자를 사용하여 RHEL 7에 .NET Core를 설치하는 방법을 설명합니다.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Red Hat 구독 등록

RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다. 아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.

## <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다. 터미널에서 다음 명령을 실행하여 RHEL 7 dotnet 채널을 사용하도록 설정하고 설치합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a>ASP.NET Core 런타임 설치

구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다. 터미널에서 다음 명령을 실행합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다. 터미널에서 다음 명령을 실행합니다.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a>참고 항목

- [Red Hat Enterprise Linux 7에서 .NET Core 3.1 사용](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
