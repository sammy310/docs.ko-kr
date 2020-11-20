---
ms.openlocfilehash: 87c7abf6a20dd8e9769f3b3b3cbe271d32fd62c3
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507001"
---

### <a name="install-the-sdk"></a>SDK 설치

.NET SDK를 사용하면 .NET으로 앱을 개발할 수 있습니다. .NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. .NET SDK를 설치하려면 다음 명령을 실행합니다.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0
```

> [!IMPORTANT]
> **dotnet-sdk-5.0 패키지를 찾을 수 없음** 과 유사한 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.

### <a name="install-the-runtime"></a>런타임 설치

ASP.NET Core 런타임을 사용하면 런타임을 제공하지 않는 .NET으로 만든 앱을 실행할 수 있습니다. 다음 명령을 실행하면 .NET에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0
```

> [!IMPORTANT]
> **aspnetcore-runtime-5.0 패키지를 찾을 수 없음** 과 같은 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.

ASP.NET Core 런타임 대신 ASP.NET Core 지원이 포함되지 않은 .NET 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-5.0`을 `dotnet-runtime-5.0`으로 바꿉니다.

```bash
sudo apt-get install -y dotnet-runtime-5.0
```
