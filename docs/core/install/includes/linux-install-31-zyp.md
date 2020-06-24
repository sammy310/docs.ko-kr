---
ms.openlocfilehash: db89539982c1afe0df374027d54826f3265f0fee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602773"
---

### <a name="install-the-sdk"></a>SDK 설치

.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다. .NET Core SDK를 설치하려면 다음 명령을 실행합니다.

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a>런타임 설치

.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다. 아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `aspnetcore-runtime-2.1`을 `dotnet-runtime-3.1`로 바꿉니다.

```bash
sudo zypper install dotnet-runtime-3.1
```
