---
ms.openlocfilehash: 07dd58c314c826c426193b829ea1f64669fb888b
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594574"
---

[dotnet-install 스크립트](../../tools/dotnet-install-script.md)는 자동화와 **SDK** 및 **런타임** 의 관리자 설치가 아닌 일반 설치를 수행하는 데 사용됩니다. <https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 SDK [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET 3.1)을 설치합니다. (LTS) 버전이 아닐 수 있는 현재 릴리스를 설치하려면 `-c Current` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current
```

SDK 대신 .NET 런타임을 설치하려면 `--runtime` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

특정 버전을 지정하도록 `-c` 매개 변수를 변경하여 특정 버전을 설치할 수 있습니다. 다음 명령은 .NET SDK 5.0을 설치합니다.

```bash
./dotnet-install.sh -c 5.0
```

자세한 내용은 [dotnet-install 스크립트 참조](../../tools/dotnet-install-script.md)를 참조하세요.
