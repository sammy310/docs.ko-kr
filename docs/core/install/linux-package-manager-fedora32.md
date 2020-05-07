---
title: Fedora 32에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Fedora 32에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624953"
---
# <a name="fedora-32-package-manager---install-net-core"></a>Fedora 32 패키지 관리자 - .NET Core 설치

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

이 문서에서는 패키지 관리자를 사용하여 Fedora 32에 .NET Core를 설치하는 방법을 설명합니다.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

Fedora 32부터는 Fedora의 기본 패키지 리포지토리에서 .NET Core 3.1을 사용할 수 있습니다.

## <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

.NET Core SDK를 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>ASP.NET Core 런타임 설치

ASP.NET 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

.NET Core 런타임을 설치합니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>다른 버전을 설치하는 방법

다른 버전의 .NET Core를 설치하려면 [.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) 또는 [.NET Core 런타임](runtime.md?pivots=os-linux#download-and-manually-install)을 수동으로 설치합니다.
