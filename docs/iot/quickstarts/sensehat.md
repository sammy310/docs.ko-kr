---
title: 빠른 시작-.NET을 사용 하 여 Raspberry Pi Sense HAT 구동
description: Raspberry Pi 용 추가 기능 보드용 Sense HAT를 사용 하 여 5 분 내에 .NET IoT 라이브러리를 시작 하세요.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 28d6650187bbf7b9ce91516f4da4d09b114c904a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259702"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a>빠른 시작-.NET을 사용 하 여 Raspberry Pi Sense HAT 구동

Raspberry Pi [SENSE HAT](https://www.raspberrypi.org/products/sense-hat/) ( **T** Op의 **H** 하려면 **A** ttached)는 Raspberry Pi의 추가 기능 보드입니다. Sense HAT에는 8 × 8의 RGB LED 매트릭스와 5 단추 조이스틱이 장착 되어 있으며 다음과 같은 센서가 포함 되어 있습니다.

- 자이로스코프
- 가속도계
- 지자기 센터
- 온도
- 바 ometric 압력
- 습도

이 빠른 시작에서는 .NET을 사용 하 여 Sense HAT에서 센서 값을 검색 하 고, 조이스틱 입력에 응답 하 고, LED 매트릭스를 구동 합니다.

## <a name="prerequisites"></a>사전 요구 사항

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- Sense HAT

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a>빠른 시작 실행

Raspberry Pi에 Sense HAT를 연결 합니다. Raspberry Pi (로컬 또는 원격)의 Bash 프롬프트에서 다음 명령을 실행 합니다.

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

명령은 스크립트를 다운로드 하 여 실행 합니다. 이 스크립트는

- .NET SDK를 설치 합니다.
- Sense HAT 빠른 시작 프로젝트를 포함 하는 GitHub 리포지토리를 복제 합니다.
- 프로젝트를 빌드합니다.
- 프로젝트를 실행 합니다.

센서 데이터가 표시 되 면 콘솔 출력을 관찰 합니다. LED 매트릭스는 파란색 필드에 노란색 픽셀을 표시 합니다. 모든 방향으로 조이스틱을 유지 하면 노란색 픽셀이 해당 방향으로 이동 합니다. 가운데 조이스틱 단추를 클릭 하면 배경이 파란색에서 빨강으로 전환 됩니다.

## <a name="get-the-source-code"></a>소스 코드 가져오기

이 빠른 시작의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart).

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [범용 입/출력을 사용 하 여 LED를 깜박이게 하는 방법을 알아봅니다.](../tutorials/blink-led.md)
