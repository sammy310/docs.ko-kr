---
ms.openlocfilehash: b6f2af7af77398d5e902aae995590b5dde4cf76a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602683"
---

### <a name="install-the-sdk"></a>SDK 설치

.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다. .NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. .NET Core SDK를 설치하려면 다음 명령을 실행합니다.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
```

> [!IMPORTANT]
> **패키지 dotnet-sdk-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.

### <a name="install-the-runtime"></a>런타임 설치

.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다. 아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> **패키지 aspnetcore-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.

ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `aspnetcore-runtime-3.1`을 `dotnet-runtime-3.1`로 바꿉니다.

```bash
sudo apt-get install -y dotnet-runtime-3.1
```
