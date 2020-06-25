---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768401"
---

[dotnet-install 스크립트](../../tools/dotnet-install-script.md)는 자동화와 **SDK** 및 **런타임**의 관리자 설치가 아닌 일반 설치를 수행하는 데 사용됩니다. <https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 SDK [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. (LTS) 버전이 아닐 수 있는 현재 릴리스를 설치하려면 `-c Current` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current
```

SDK 대신 .NET Core 런타임을 설치하려면 `--runtime` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

특정 버전을 지정하도록 `-c` 매개 변수를 변경하여 특정 버전을 설치할 수 있습니다. 다음 명령은 .NET Core SDK 3.1을 설치합니다.

```bash
./dotnet-install.sh -c 3.1
```

자세한 내용은 [dotnet-install 스크립트 참조](../../tools/dotnet-install-script.md)를 참조하세요.
