---
title: openSUSE 15에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 openSUSE 15에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 3b5f51161dad4b0d7851421810506d6ed9f676f9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134226"
---
# <a name="opensuse-15-package-manager---install-net-core"></a>openSUSE 15 패키지 관리자 - .NET Core 설치

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

이 문서에서는 패키지 관리자를 사용하여 openSUSE 15에 .NET Core를 설치하는 방법을 설명합니다.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a>Microsoft 키 및 피드 등록

.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.

- Microsoft 키를 등록합니다.
- 제품 리포지토리를 등록합니다.
- 필수 종속성을 설치합니다.

이 작업은 머신당 한 번만 수행하면 됩니다.

터미널을 열고 다음 명령을 실행합니다.

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>ASP.NET Core 런타임 설치

설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>다른 버전을 설치하는 방법

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>패키지 관리자 문제 해결

이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.

### <a name="failed-to-fetch"></a>가져오지 못함

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
