---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602749"
---

**패키지 {netcore-package}를 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.

다음 명령 집합에는 두 개의 자리 표시자가 있습니다.

- `{dotnet-package}`\
이는 `aspnetcore-runtime-3.1`와 같이 설치 중인 .NET Core 패키지를 나타냅니다. 아래의 `sudo apt-get install` 명령에서 사용됩니다.

- `{os-version}`\
현재 사용 중인 Linux 버전을 나타냅니다. 아래의 `wget` 명령에서 사용됩니다.

다음 패키지 목록을 제거해 보세요.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.
