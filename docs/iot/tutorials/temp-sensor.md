---
title: 센서에서 환경 조건 읽기
description: .NET IoT 라이브러리를 사용 하 여 termperature, 바 ometric 압력 및 습도를 읽는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/14/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: bc5c2b9f0876603c152da859547c58b83826969c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259839"
---
# <a name="read-environmental-conditions-from-a-sensor"></a><span data-ttu-id="283c4-103">센서에서 환경 조건 읽기</span><span class="sxs-lookup"><span data-stu-id="283c4-103">Read environmental conditions from a sensor</span></span>

<span data-ttu-id="283c4-104">IoT 장치에 대 한 가장 일반적인 시나리오 중 하나는 환경 조건을 검색 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-104">One of the most common scenarios for IoT devices is detection of environmental conditions.</span></span> <span data-ttu-id="283c4-105">온도, 습도, 바 ometric 압력 등을 모니터링 하는 데 다양 한 센서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-105">A variety of sensors are available to monitor temperature, humidity, barometric pressure, and more.</span></span>

<span data-ttu-id="283c4-106">이 항목에서는 .NET을 사용 하 여 센서에서 환경 조건을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-106">In this topic, you will use .NET to read environmental conditions from a sensor.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="283c4-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="283c4-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="283c4-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) 습도/바 ometric 압력/온도 센서 브레이크 아웃</span><span class="sxs-lookup"><span data-stu-id="283c4-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) humidity/barometric pressure/temperature sensor breakout</span></span>
- <span data-ttu-id="283c4-109">점퍼 와이어</span><span class="sxs-lookup"><span data-stu-id="283c4-109">Jumper wires</span></span>
- <span data-ttu-id="283c4-110">실험용 회로판 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="283c4-110">Breadboard (optional)</span></span>
- <span data-ttu-id="283c4-111">Raspberry Pi GPIO 브레이크 보드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="283c4-111">Raspberry Pi GPIO breakout board (optional)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> <span data-ttu-id="283c4-112">BME280 사이의 많은 제조업체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-112">There are many manufacturers of BME280 breakouts.</span></span> <span data-ttu-id="283c4-113">대부분의 디자인은 비슷하며 제조업체에서이 기능에 대해 어떠한 차이를 주지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-113">Most designs are similar, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="283c4-114">이 자습서에서는 변형을 고려 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-114">This tutorial attempts to account for variations.</span></span> <span data-ttu-id="283c4-115">BME280 브레이크 아웃에 I2C (Inter-Integrated 회로) 인터페이스가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-115">Ensure your BME280 breakout includes an Inter-Integrated Circuit (I2C) interface.</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="283c4-116">하드웨어 준비</span><span class="sxs-lookup"><span data-stu-id="283c4-116">Prepare the hardware</span></span>

<span data-ttu-id="283c4-117">하드웨어 구성 요소를 사용 하 여 다음 다이어그램에 표시 된 대로 회로를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-117">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Raspberry Pi에서 BME280 브레이크 보드로의 연결을 보여 주는 Fritzing 다이어그램" lightbox="../media/rpi-bmp280_i2c.png":::

<span data-ttu-id="283c4-119">다음은 Raspberry Pi에서 BME280로의 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-119">The following are the connections from the Raspberry Pi to the BME280 breakout:</span></span>

- <span data-ttu-id="283c4-120">3.3 v에서 VIN *또는* 3v3 (빨간색으로 표시)</span><span class="sxs-lookup"><span data-stu-id="283c4-120">3.3V to VIN *OR* 3V3 (shown in red)</span></span>
- <span data-ttu-id="283c4-121">접지 대 GND (검정)</span><span class="sxs-lookup"><span data-stu-id="283c4-121">Ground to GND (black)</span></span>
- <span data-ttu-id="283c4-122">SDA (GPIO 2)에서 SDI *또는* sda (파란색)로</span><span class="sxs-lookup"><span data-stu-id="283c4-122">SDA (GPIO 2) to SDI *OR* SDA (blue)</span></span>
- <span data-ttu-id="283c4-123">SCL (GPIO 3) ~ SCK *또는* SCL (주황색)</span><span class="sxs-lookup"><span data-stu-id="283c4-123">SCL (GPIO 3) to SCK *OR* SCL (orange)</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="283c4-124">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="283c4-124">Create the app</span></span>

<span data-ttu-id="283c4-125">선호 하는 개발 환경에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-125">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="283c4-126">[.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-126">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="283c4-127">이름을 *SensorTutorial* 로 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-127">Name it *SensorTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="283c4-128">*Program.cs* 의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-128">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    <span data-ttu-id="283c4-129">위의 코드에서</span><span class="sxs-lookup"><span data-stu-id="283c4-129">In the preceding code:</span></span>

    - <span data-ttu-id="283c4-130">`i2cSettings` 는의 새 인스턴스로 설정 됩니다 `I2cConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="283c4-130">`i2cSettings` is set to a new instance of `I2cConnectionSettings`.</span></span> <span data-ttu-id="283c4-131">생성자는 `busId` 매개 변수를 1로 설정 하 고 `deviceAddress` 매개 변수를로 설정 `Bme280.DefaultI2cAddress` 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-131">The constructor sets the `busId` parameter to 1 and the `deviceAddress` parameter to `Bme280.DefaultI2cAddress`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="283c4-132">일부 BME280 분리 제조업체는 보조 주소 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-132">Some BME280 breakout manufacturers use the secondary address value.</span></span> <span data-ttu-id="283c4-133">이러한 장치에 대해를 사용 `Bme280.SecondaryI2cAddress` 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-133">For those devices, use `Bme280.SecondaryI2cAddress`.</span></span>

    - <span data-ttu-id="283c4-134">[Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 를 `I2cDevice` 호출 `I2cDevice.Create` 하 고를 전달 하 여의 인스턴스를 만듭니다 `i2cSettings` .</span><span class="sxs-lookup"><span data-stu-id="283c4-134">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in `i2cSettings`.</span></span> <span data-ttu-id="283c4-135">이 `I2cDevice` 는 I2C 버스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-135">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="283c4-136">`using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-136">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="283c4-137">다른 `using` 선언은 센서를 나타내는의 인스턴스 `Bme280` 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-137">Another `using` declaration creates an instance of `Bme280` to represent the sensor.</span></span> <span data-ttu-id="283c4-138">는 `I2cDevice` 생성자에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-138">The `I2cDevice` is passed in the constructor.</span></span>
    - <span data-ttu-id="283c4-139">칩에서 칩의 현재 (기본) 설정에 따라 측정 하는 데 필요한 시간은를 호출 하 여 검색 됩니다 `GetMeasurementDuration` .</span><span class="sxs-lookup"><span data-stu-id="283c4-139">The time required for the chip to take measurements with the chip's current (default) settings is retrieved by calling `GetMeasurementDuration`.</span></span>
    - <span data-ttu-id="283c4-140">`while`루프는 무기한 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-140">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="283c4-141">각 반복:</span><span class="sxs-lookup"><span data-stu-id="283c4-141">Each iteration:</span></span>
        1. <span data-ttu-id="283c4-142">콘솔을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-142">Clears the console.</span></span>
        1. <span data-ttu-id="283c4-143">전원 모드를로 설정 `Bmx280PowerMode.Forced` 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-143">Sets the power mode to `Bmx280PowerMode.Forced`.</span></span> <span data-ttu-id="283c4-144">그러면 칩이 하나의 측정을 수행 하 고 결과를 저장 한 다음 절전 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-144">This forces the chip to perform one measurement, store the results, and then sleep.</span></span>
        1. <span data-ttu-id="283c4-145">온도, 압력, 습도 및 고도의 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-145">Reads the values for temperature, pressure, humidity, and altitude.</span></span>

            > [!NOTE]
            > <span data-ttu-id="283c4-146">고도는 장치 바인딩에서 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-146">Altitude is calculated by the device binding.</span></span> <span data-ttu-id="283c4-147">의이 오버 로드는 `TryReadAltitude` 평균 해상 수준 압력을 사용 하 여 추정치를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-147">This overload of `TryReadAltitude` uses mean sea level pressure to generate an estimate.</span></span>

        1. <span data-ttu-id="283c4-148">현재 환경 조건을 콘솔에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-148">Writes the current environmental conditions to the console.</span></span>
        1. <span data-ttu-id="283c4-149">1000 밀리초를 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-149">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="283c4-150">배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-150">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./SensorTutorial
    ```

    <span data-ttu-id="283c4-151">콘솔에서 센서 출력을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-151">Observe the sensor output in the console.</span></span>

1. <span data-ttu-id="283c4-152"><kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-152">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="283c4-153">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="283c4-153">Congratulations!</span></span> <span data-ttu-id="283c4-154">I2C를 사용 하 여 온도/습도/바코드 ometric 압력 센서에서 값을 읽었습니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-154">You've used I2C to read values from a temperature/humidity/barometric pressure sensor!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="283c4-155">소스 코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="283c4-155">Get the source code</span></span>

<span data-ttu-id="283c4-156">이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial).</span><span class="sxs-lookup"><span data-stu-id="283c4-156">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial).</span></span>

## <a name="next-steps"></a><span data-ttu-id="283c4-157">다음 단계</span><span class="sxs-lookup"><span data-stu-id="283c4-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="283c4-158">LCD에 텍스트를 표시 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="283c4-158">Learn how to display text on an LCD</span></span>](../tutorials/lcd-display.md)
