---
title: Fedora 30에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Fedora 30에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: bd7a199f551be0c51032510279ee9da74bcf0c7c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740699"
---
# <a name="fedora-30-package-manager---install-net-core"></a>Fedora 30 패키지 관리자 - .NET Core 설치

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

이 문서에서는 패키지 관리자를 사용하여 Fedora 30에 .NET Core를 설치하는 방법을 설명합니다. 런타임을 설치하려면 .NET Core 런타임과 ASP.NET Core 런타임이 모두 포함된 [ASP.NET Core 런타임](#install-the-aspnet-core-runtime)을 설치하는 것이 좋습니다.

## <a name="register-microsoft-key-and-feed"></a>Microsoft 키 및 피드 등록

.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.

- Microsoft 키를 등록합니다.
- 제품 리포지토리를 등록합니다.
- 필수 종속성을 설치합니다.

이 작업은 머신당 한 번만 수행하면 됩니다.

터미널을 열고 다음 명령을 실행합니다.

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

## <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>ASP.NET Core 런타임 설치

설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>다른 버전을 설치하는 방법

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
