---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594021"
---
[SFTP 클라이언트를 사용 하 여](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md)개발 컴퓨터의 게시 위치에서 Raspberry Pi의 새 폴더로 파일을 복사 합니다.

예를 들어 명령을 사용 하 여 `scp` 개발 컴퓨터에서 Raspberry Pi로 파일을 복사 하려면 명령 프롬프트를 열고 다음을 실행 합니다.

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

여기서

- `-r`옵션은 `scp` 파일을 재귀적으로 복사 하도록에 지시 합니다.
- */c-loclocs/* 는 이전 단계에서 게시 한 폴더입니다.
- `pi@raspberypi` 는 형식의 사용자 및 호스트 이름입니다 `<username>@<hostname>` .
- */home/pi/deployment-location/* 는 Raspberry pi의 새 폴더입니다.

> [!TIP]
> 최신 버전의 Windows에는 미리 설치 된를 포함 하는 OpenSSH이 있습니다 `scp` .
