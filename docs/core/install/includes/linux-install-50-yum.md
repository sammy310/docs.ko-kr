---
ms.openlocfilehash: cc394741e399f4fc54dd67f1736f7027badf4c7d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507108"
---

### <a name="install-the-sdk"></a>SDK 설치

.NET SDK를 사용하면 .NET으로 앱을 개발할 수 있습니다. .NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. .NET SDK를 설치하려면 다음 명령을 실행합니다.

```bash
sudo yum install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>런타임 설치

ASP.NET Core 런타임을 사용하면 런타임을 제공하지 않는 .NET으로 만든 앱을 실행할 수 있습니다. 다음 명령을 실행하면 .NET에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다. 터미널에서 다음 명령을 실행합니다.

```bash
sudo yum install aspnetcore-runtime-5.0
```

ASP.NET Core 런타임 대신 ASP.NET Core 지원이 포함되지 않은 .NET 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-5.0`을 `dotnet-runtime-5.0`으로 바꿉니다.

```bash
sudo yum install dotnet-runtime-5.0
```
