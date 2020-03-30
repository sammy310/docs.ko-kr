---
title: Ubuntu 19.10에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Ubuntu 19.10에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: aac63ba74a8bfaba63e9d23882c9350a7d3d84f3
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134121"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a>Ubuntu 19.10 패키지 관리자 - .NET Core 설치

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

이 문서에서는 패키지 관리자를 사용하여 Ubuntu 19.10에 .NET Core를 설치하는 방법을 설명합니다.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a>Microsoft 키 및 피드 등록

.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.

- Microsoft 키를 등록합니다.
- 제품 리포지토리를 등록합니다.
- 필수 종속성을 설치합니다.

이 작업은 머신당 한 번만 수행하면 됩니다.

터미널을 열고 다음 명령을 실행합니다.

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> **패키지 dotnet-sdk-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.

## <a name="install-the-aspnet-core-runtime"></a>ASP.NET Core 런타임 설치

설치를 위한 제품을 업데이트하고, ASP.NET Core 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> **패키지 aspnetcore-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.

## <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> **패키지 dotnet-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.

## <a name="how-to-install-other-versions"></a>다른 버전을 설치하는 방법

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>패키지 관리자 문제 해결

이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.

### <a name="unable-to-locate"></a>찾을 수 없음

**패키지 {.NET Core 패키지}를 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.

```bash
sudo apt-get install -y gpg
wget O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a>가져오지 못함

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
