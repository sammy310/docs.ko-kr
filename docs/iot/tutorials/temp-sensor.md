---
title: 센서에서 환경 조건 읽기
description: .NET IoT 라이브러리를 사용 하 여 termperature, 바 ometric 압력 및 습도를 읽는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/14/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 1270e7629e9afc12b1d76d260d4b8b51428f1040
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594153"
---
# <a name="read-environmental-conditions-from-a-sensor"></a>센서에서 환경 조건 읽기

IoT 장치에 대 한 가장 일반적인 시나리오 중 하나는 환경 조건을 검색 하는 것입니다. 온도, 습도, 바 ometric 압력 등을 모니터링 하는 데 다양 한 센서를 사용할 수 있습니다.

이 항목에서는 .NET을 사용 하 여 센서에서 환경 조건을 읽습니다.

## <a name="prerequisites"></a>필수 조건

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) <span class="docon docon-navigate-external x-hidden-focus"></span> 습도/무게 ometric 압력/온도 센서 브레이크 아웃
- 점퍼 와이어
- 실험용 회로판 (선택 사항)
- Raspberry Pi GPIO 브레이크 보드 (선택 사항)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> BME280 사이의 많은 제조업체가 있습니다. 대부분의 디자인은 비슷하며 제조업체에서이 기능에 대해 어떠한 차이를 주지 않아야 합니다. 이 자습서에서는 변형을 고려 하려고 합니다. BME280 브레이크 아웃에 I2C (Inter-Integrated 회로) 인터페이스가 포함 되어 있는지 확인 합니다.

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>하드웨어 준비

하드웨어 구성 요소를 사용 하 여 다음 다이어그램에 표시 된 대로 회로를 빌드합니다.

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Raspberry Pi에서 BME280 브레이크 보드로의 연결을 보여 주는 Fritzing 다이어그램" lightbox="../media/rpi-bmp280_i2c.png":::

다음은 Raspberry Pi에서 BME280로의 연결입니다.

- 3.3 v에서 VIN *또는* 3v3 (빨간색으로 표시)
- 접지 대 GND (검정)
- SDA (GPIO 2)에서 SDI *또는* sda (파란색)로
- SCL (GPIO 3) ~ SCK *또는* SCL (주황색)

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>앱 만들기

선호 하는 개발 환경에서 다음 단계를 완료 합니다.

1. [.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다. 이름을 *SensorTutorial* 로 합니다.

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. *Program.cs* 의 내용을 다음 코드로 바꿉니다.

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    앞의 코드에서 다음을 확인할 수 있습니다.

    - `i2cSettings` 는의 새 인스턴스로 설정 됩니다 `I2cConnectionSettings` . 생성자는 `busId` 매개 변수를 1로 설정 하 고 `deviceAddress` 매개 변수를로 설정 `Bme280.DefaultI2cAddress` 합니다.

        > [!IMPORTANT]
        > 일부 BME280 분리 제조업체는 보조 주소 값을 사용 합니다. 이러한 장치에 대해를 사용 `Bme280.SecondaryI2cAddress` 합니다.

    - [Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 를 `I2cDevice` 호출 `I2cDevice.Create` 하 고를 전달 하 여의 인스턴스를 만듭니다 `i2cSettings` . 이 `I2cDevice` 는 I2C 버스를 나타냅니다. `using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.
    - 다른 `using` 선언은 센서를 나타내는의 인스턴스 `Bme280` 를 만듭니다. 는 `I2cDevice` 생성자에 전달 됩니다.
    - 칩에서 칩의 현재 (기본) 설정에 따라 측정 하는 데 필요한 시간은를 호출 하 여 검색 됩니다 `GetMeasurementDuration` .
    - `while`루프는 무기한 실행 됩니다. 각 반복:
        1. 콘솔을 지웁니다.
        1. 전원 모드를로 설정 `Bmx280PowerMode.Forced` 합니다. 그러면 칩이 하나의 측정을 수행 하 고 결과를 저장 한 다음 절전 모드로 전환 됩니다.
        1. 온도, 압력, 습도 및 고도의 값을 읽습니다.

            > [!NOTE]
            > 고도는 장치 바인딩에서 계산 합니다. 의이 오버 로드는 `TryReadAltitude` 평균 해상 수준 압력을 사용 하 여 추정치를 생성 합니다.

        1. 현재 환경 조건을 콘솔에 기록 합니다.
        1. 1000 밀리초를 대기 합니다.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. 배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.

    ```bash
    ./SensorTutorial
    ```

    콘솔에서 센서 출력을 관찰 합니다.

1. <kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.

축하합니다! I2C를 사용 하 여 온도/습도/바코드 ometric 압력 센서에서 값을 읽었습니다.

## <a name="get-the-source-code"></a>소스 코드 가져오기

이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [LCD에 텍스트를 표시 하는 방법을 알아봅니다.](../tutorials/lcd-display.md)
