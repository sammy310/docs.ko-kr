---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506985"
---

**{netcore-package} 패키지를 찾을 수 없음** 또는 **일부 패키지를 설치할 수 없음** 과 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.

다음 명령 집합에는 두 개의 자리 표시자가 있습니다.

- `{dotnet-package}`\
`aspnetcore-runtime-3.1`과 같이 설치 중인 .NET 패키지를 나타냅니다. 다음 `sudo apt-get install` 명령에 사용됩니다.

- `{os-version}`\
현재 사용 중인 Linux 버전을 나타냅니다. 아래의 `wget` 명령에서 사용됩니다.

먼저, 다음 패키지 목록을 제거해 봅니다.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

그런 다음, .NET을 다시 설치해 봅니다. 이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.
