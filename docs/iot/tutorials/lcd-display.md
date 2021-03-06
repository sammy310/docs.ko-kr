---
title: LCD에 텍스트 표시
description: .NET IoT 라이브러리를 사용 하 여 액체 크리스탈 디스플레이에 문자를 표시 하는 방법을 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 005b40a7d9f46b84fcd90541248f5f4fd243e612
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255541"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="display-text-on-an-lcd"></a>LCD에 텍스트 표시

LCD 문자 표시는 외부 모니터가 없어도 정보를 표시 하는 데 유용 합니다. 일반 LCD 문자 표시를 GPIO 핀에 직접 연결할 수 있지만 이러한 방법에는 최대 10 개의 GPIO 핀을 사용 해야 합니다. 여러 장치를 조합 하 여 연결 해야 하는 시나리오의 경우 대부분의 GPIO 헤더를 문자 표시에 devoting 하는 것이 실용적이 지 않습니다.

여러 제조업체에서 20x4 LCD 문자 표시와 통합 GPIO 확장기를 판매 합니다. 문자 표시는 GPIO 확장기에 직접 연결 하 여 I2C (Inter-Integrated 회로) 직렬 프로토콜을 통해 Raspberry Pi에 연결 합니다.

이 항목에서는 .NET을 사용 하 여 I2C GPIO 확장기를 사용 하는 LCD 문자 표시에 텍스트를 표시 합니다.

## <a name="prerequisites"></a>사전 요구 사항

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [20x4는 I2C 인터페이스를 사용 하 여 LCD 문자 표시](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)
- 점퍼 와이어
- 실험용 회로판 (선택 사항/권장)
- Raspberry Pi GPIO 브레이크 보드 보드 (선택 사항/권장)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> LCD 문자 표시의 제조업체에는 여러 가지가 있습니다. 대부분의 디자인은 동일 하며, 제조업체에서 기능에 대해 어떠한 차이도 하지 않아야 합니다. 참조용으로이 자습서는 [SUNFOUNDER LCD2004](https://www.sunfounder.com/lcd2004-module.html)를 사용 하 여 개발 되었습니다.

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>하드웨어 준비

다음과 같이 점퍼 와이어를 사용 하 여 I2C GPIO 확장기에서 4 개의 핀을 Raspberry Pi에 연결 합니다.

- GND
- VCC를 5V로
- SDA에서 SDA로 (GPIO 2)
- SCL에서 SCL (GPIO 3)

필요에 따라 다음 그림을 참조 하세요.

| I2C 인터페이스 (표시 후면) | Raspberry Pi GPIO |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="I2C GPIO 확장기를 표시 하는 문자 표시의 뒤쪽 이미지입니다." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Raspberry Pi GPIO 헤더의 핀아웃를 표시 하는 다이어그램입니다. Image 경칭 Raspberry Pi Foundation입니다." lightbox="../media/gpio-pinout-diagram.png":::<br />[Image 경칭 Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/)입니다.
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>앱 만들기

선호 하는 개발 환경에서 다음 단계를 완료 합니다.

1. [.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다. 이름을 *LcdTutorial* 로 합니다.

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. *Program.cs* 의 내용을 다음 코드로 바꿉니다.

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    위의 코드에서

    - [Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 를 `I2cDevice` 호출 하 `I2cDevice.Create` 고 `I2cConnectionSettings` `busId` 및 매개 변수를 사용 하 여 새를 전달 하 여의 인스턴스를 만듭니다 `deviceAddress` . 이 `I2cDevice` 는 I2C 버스를 나타냅니다. `using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.

        > [!WARNING]
        > GPIO 확장기의 장치 주소는 제조업체에서 사용 하는 칩에 따라 다릅니다. PCF8574를 사용 하는 GPIO 확장 기가는 주소를 사용 하 고 PCF8574A 칩을 사용 하는 경우에는를 사용 `0x27` `0x3F` 합니다. LCD 설명서를 참조 하세요.

    - 다른 `using` 선언은의 인스턴스를 만들고 `Pcf8574` 을 `I2cDevice` 생성자에 전달 합니다. 이 인스턴스는 GPIO 확장기를 나타냅니다.
    - 다른 `using` 선언은의 인스턴스를 만들어 `Lcd2004` 표시를 나타냅니다. 여러 매개 변수는 GPIO 확장기와 통신 하는 데 사용할 설정을 설명 하는 생성자에 전달 됩니다. GPIO 확장기는 매개 변수로 전달 됩니다 `controller` .
    - `while`루프는 무기한 실행 됩니다. 각 반복:
        1. 표시를 지웁니다.
        1. 커서 위치를 현재 줄의 첫 번째 위치로 설정 합니다.
        1. 현재 커서 위치에 표시 되는 현재 시간을 씁니다.
        1. 현재 줄 카운터를 반복 합니다.
        1. 1000 밀리초를 대기 합니다.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. 배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.

    ```bash
    ./LcdTutorial
    ```

    현재 시간이 각 줄에 표시 되 면 LCD 문자 표시를 확인 합니다.

    > [!TIP]
    > 디스플레이가 켜져 있지만 텍스트가 표시 되지 않는 경우 화면 뒷면에서 대비 전화 걸기를 조정 해 보세요.

1. <kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.

축하합니다! I2C 및 GPIO 확장기를 사용 하 여 LCD에 텍스트를 표시 했습니다.

## <a name="get-the-source-code"></a>소스 코드 가져오기

이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial).

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [범용 입/출력을 사용 하 여 LED를 깜박이게 하는 방법을 알아봅니다.](../tutorials/blink-led.md)
