---
title: LED 깜박이기
description: .NET IoT 라이브러리를 사용 하 여 LED를 깜박이는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 0d5db19faac0293b9982731f26dfd85d6ce07b3a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259028"
---
# <a name="blink-an-led"></a>LED 깜박이기

범용 i/o (GPIO) 핀은 개별적으로 제어할 수 있습니다. 이는 Led, 릴레이 및 기타 상태 저장 장치를 제어 하는 데 유용 합니다. 이 항목에서는 .NET 및 Raspberry Pi의 GPIO 핀을 사용 하 여 LED를 켜고 반복적으로 깜박임 합니다.

## <a name="prerequisites"></a>사전 요구 사항

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- 5mm LED
- 330 Ω 저항기
- 브레드보드
- 점퍼 와이어
- Raspberry Pi GPIO 브레이크 보드 보드 (선택 사항/권장)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a>하드웨어 준비

하드웨어 구성 요소를 사용 하 여 다음 다이어그램에 표시 된 대로 회로를 빌드합니다.

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="LED와 저항기를 사용 하는 회로를 보여 주는 Fritzing 다이어그램" lightbox="../media/rpi-led_bb.png":::

위의 이미지는 다음 연결을 보여 줍니다.

- GPIO 18 to LED 양극 (길수록 긍정적인 리드)
- LED 음극 (짧은 리드, 부정 리드) ~ 330 Ω 저항기 (끝)
- 330 Ω 저항기 (기타 끝)를 접지 합니다.

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>앱 만들기

선호 하는 개발 환경에서 다음 단계를 완료 합니다.

1. [.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다. 이름을 *Blinktutorial* 으로 이름 합니다.

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. *Program.cs* 의 내용을 다음 코드로 바꿉니다.

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    위의 코드에서

    - [Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 의 인스턴스를 만듭니다 `GpioController` . `using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.
    - 출력에 대 한 GPIO 핀 18이 열립니다.
    - `while`루프는 무기한 실행 됩니다. 각 반복:
        1. GPIO 핀 18에 값을 씁니다. `ledOn`가 true 이면는 `PinValue.High` (on)를 작성 합니다. 그렇지 않으면를 씁니다 `PinValue.Low` .
        1. 1000 밀리초를 대기 합니다.
        1. 의 값을 설정/해제 `ledOn` 합니다.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. 배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.

    ```bash
    ./BlinkTutorial
    ```

    LED는 매 초 마다 깜박입니다.

1. <kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.

축하합니다! GPIO를 사용 하 여 LED를 깜박임 했습니다.

## <a name="get-the-source-code"></a>소스 코드 가져오기

이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial).

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [센서에서 환경 조건을 읽는 방법 알아보기](../tutorials/temp-sensor.md)
