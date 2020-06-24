---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602719"
---

[dotnet-install 스크립트](../../tools/dotnet-install-script.md)는 자동화 및 **SDK**의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. <https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. (LTS) 버전이 아닐 수 있는 현재 릴리스를 설치하려면 `-c Current` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current
```

SDK 대신 .NET Core 런타임을 설치하려면 `--runtime` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current --runtime
```

특정 버전을 지정하도록 `-c` 매개 변수를 변경하여 특정 버전을 설치할 수 있습니다. 다음 명령은 .NET Core SDK 3.1을 설치합니다.

```bash
./dotnet-install.sh -c 3.1
```

자세한 내용은 [dotnet-install 스크립트 참조](../../tools/dotnet-install-script.md)를 참조하세요.
