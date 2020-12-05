---
title: 아날로그에서 디지털로의 변환기에서 값 읽기
description: 아날로그에서 디지털로의 변환기를 사용 하 여 가변 전압 값을 읽는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 7cf25f181997ed66639842727be57e7824ef5466
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739989"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a>아날로그에서 디지털로의 변환기에서 값 읽기

아날로그-디지털 변환기 (ADC)는 아날로그 입력 전압 값을 읽고 디지털 값으로 변환할 수 있는 장치입니다. ADCs는 특정 조건에 따라 저항을 변경 하는 thermistors, potentiometers 및 기타 장치에서 값을 읽는 데 사용 됩니다.

이 항목에서는 potentiometer로 입력 전압을 조절 .NET을 사용 하 여 ADC에서 값을 읽습니다.

## <a name="prerequisites"></a>필수 구성 요소

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> 아날로그에서 디지털 컨버터
- 3 핀 potentiometer
- 브레드보드
- 점퍼 와이어
- Raspberry Pi GPIO 브레이크 보드 보드 (선택 사항/권장)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a>하드웨어 준비

하드웨어 구성 요소를 사용 하 여 다음 다이어그램에 표시 된 대로 회로를 빌드합니다.

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="MCP3008 ADC 및 potentiometer를 사용 하는 회로를 보여 주는 Fritzing 다이어그램" lightbox="../media/rpi-trimpot_spi.png":::

MCP3008는 SPI (직렬 주변 장치 인터페이스)를 사용 하 여 통신 합니다. 다음은 MCP3008에서 Raspberry Pi 및 potentiometer로의 연결입니다.

- V<sub>DD</sub> 에서 3.3 v (빨간색으로 표시)
- V<sub>REF</sub> -3.3 v (빨강)
- AGND to 그라운드 (검정)
- CLK에서 SCLK (주황색)
- 차원<sub>확장</sub> (주황색)
- MOSI<sub>의</sub> D (주황)
- CS/SHDN to CE0 (녹색)
- DGND (검정)
- Potentiometer (노랑)의 CH0 to variable (중간) 핀

Potentiometer의 외부 핀에 3.3 V 및 접지를 제공 합니다. 순서는 중요 하지 않습니다.

필요에 따라 다음 핀아웃 다이어그램을 참조 하세요.

| MCP3008  | Raspberry Pi GPIO |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="MCP3008의 핀아웃를 보여 주는 다이어그램" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Raspberry Pi GPIO 헤더의 핀아웃를 표시 하는 다이어그램입니다. Image 경칭 Raspberry Pi Foundation입니다." lightbox="../media/gpio-pinout-diagram.png":::<br />[Image 경칭 Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/)입니다.
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>앱 만들기

선호 하는 개발 환경에서 다음 단계를 완료 합니다.

1. [.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다. 이름을 *Adctutorial* 로 합니다.

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. *Program.cs* 의 내용을 다음 코드로 바꿉니다.

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    위의 코드에서

    - `hardwareSpiSettings` 는의 새 인스턴스로 설정 됩니다 `SpiConnectionSettings` . 생성자는 `busId` 매개 변수를 0으로 설정 하 고 매개 변수를 0으로 설정 합니다 `chipSelectLine` .
    - [Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 를 `SpiDevice` 호출 `SpiDevice.Create` 하 고를 전달 하 여의 인스턴스를 만듭니다 `hardwareSpiSettings` . 이 `SpiDevice` 는 SPI 버스를 나타냅니다. `using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.
    - 다른 `using` 선언은의 인스턴스를 만들고 `Mcp3008` 을 `SpiDevice` 생성자에 전달 합니다.
    - `while`루프는 무기한 실행 됩니다. 각 반복:
        1. 을 호출 하 여 ADC에서 CH0의 값을 읽습니다 `mcp.Read(0)` .
        1. 10.24로 값을 나눕니다. MCP3008는 10 비트 ADC 이며 0-1023 범위의 1024 가능한 값을 반환 합니다. 값을 10.24로 나누면 값을 백분율로 나타냅니다.
        1. 값을 가장 가까운 정수로 반올림 합니다.
        1. 값을 백분율로 형식이 지정 된 콘솔에 씁니다.
        1. 500 밀리초를 대기 합니다.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. 배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.

    ```bash
    ./AdcTutorial
    ```

    Potentiometer 다이얼을 회전할 때 출력을 관찰 합니다. 이는 potentiometer가 ADC의 CH0에 제공 된 전압을 변경 하기 때문입니다. ADC는 CH0의 입력 전압을 V<sub>REF</sub> 에 제공 된 참조 전압과 비교 하 여 값을 생성 합니다.

1. <kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.

축하합니다! SPI를 사용 하 여 아날로그에서 디지털로의 변환기에서 값을 읽었습니다.

## <a name="get-the-source-code"></a>소스 코드 가져오기

이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [범용 입/출력을 사용 하 여 LED를 깜박이게 하는 방법을 알아봅니다.](../tutorials/blink-led.md)
