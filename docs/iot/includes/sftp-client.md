---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594021"
---
<span data-ttu-id="bf5f0-101">[SFTP 클라이언트를 사용 하 여](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md)개발 컴퓨터의 게시 위치에서 Raspberry Pi의 새 폴더로 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-101">[Using an SFTP client](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copy the files from the publish location on the development computer to a new folder on the Raspberry Pi.</span></span>

<span data-ttu-id="bf5f0-102">예를 들어 명령을 사용 하 여 `scp` 개발 컴퓨터에서 Raspberry Pi로 파일을 복사 하려면 명령 프롬프트를 열고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-102">For example, to use the `scp` command to copy files from the development computer to your Raspberry Pi, open a command prompt and execute the following:</span></span>

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

<span data-ttu-id="bf5f0-103">여기서</span><span class="sxs-lookup"><span data-stu-id="bf5f0-103">Where:</span></span>

- <span data-ttu-id="bf5f0-104">`-r`옵션은 `scp` 파일을 재귀적으로 복사 하도록에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-104">The `-r` option instructs `scp` to copy files recursively.</span></span>
- <span data-ttu-id="bf5f0-105">*/c-loclocs/* 는 이전 단계에서 게시 한 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-105">*/publish-location/* is the folder you published to in the previous step.</span></span>
- <span data-ttu-id="bf5f0-106">`pi@raspberypi` 는 형식의 사용자 및 호스트 이름입니다 `<username>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="bf5f0-106">`pi@raspberypi` is the user and host names in the format `<username>@<hostname>`.</span></span>
- <span data-ttu-id="bf5f0-107">*/home/pi/deployment-location/* 는 Raspberry pi의 새 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-107">*/home/pi/deployment-location/* is the new folder on the Raspberry Pi.</span></span>

> [!TIP]
> <span data-ttu-id="bf5f0-108">최신 버전의 Windows에는 미리 설치 된를 포함 하는 OpenSSH이 있습니다 `scp` .</span><span class="sxs-lookup"><span data-stu-id="bf5f0-108">Recent versions of Windows have OpenSSH, which includes `scp`, pre-installed.</span></span>
