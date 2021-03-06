---
title: 아날로그에서 디지털로의 변환기에서 값 읽기
description: 아날로그에서 디지털로의 변환기를 사용 하 여 가변 전압 값을 읽는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 509616e3423fbb83b74bfbb8ecec1a7df49f0a20
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259744"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a><span data-ttu-id="950b7-103">아날로그에서 디지털로의 변환기에서 값 읽기</span><span class="sxs-lookup"><span data-stu-id="950b7-103">Read values from an analog-to-digital converter</span></span>

<span data-ttu-id="950b7-104">아날로그-디지털 변환기 (ADC)는 아날로그 입력 전압 값을 읽고 디지털 값으로 변환할 수 있는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-104">An analog-to-digital converter (ADC) is a device that can read an analog input voltage value and convert it into a digital value.</span></span> <span data-ttu-id="950b7-105">ADCs는 특정 조건에 따라 저항을 변경 하는 thermistors, potentiometers 및 기타 장치에서 값을 읽는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-105">ADCs are used for reading values from thermistors, potentiometers, and other devices that change resistance based on certain conditions.</span></span>

<span data-ttu-id="950b7-106">이 항목에서는 potentiometer로 입력 전압을 조절 .NET을 사용 하 여 ADC에서 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-106">In this topic, you will use .NET to read values from an ADC as you modulate the input voltage with a potentiometer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="950b7-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="950b7-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="950b7-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) 아날로그를 디지털로 변환</span><span class="sxs-lookup"><span data-stu-id="950b7-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) analog-to-digital converter</span></span>
- <span data-ttu-id="950b7-109">3 핀 potentiometer</span><span class="sxs-lookup"><span data-stu-id="950b7-109">Three-pin potentiometer</span></span>
- <span data-ttu-id="950b7-110">브레드보드</span><span class="sxs-lookup"><span data-stu-id="950b7-110">Breadboard</span></span>
- <span data-ttu-id="950b7-111">점퍼 와이어</span><span class="sxs-lookup"><span data-stu-id="950b7-111">Jumper wires</span></span>
- <span data-ttu-id="950b7-112">Raspberry Pi GPIO 브레이크 보드 보드 (선택 사항/권장)</span><span class="sxs-lookup"><span data-stu-id="950b7-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="950b7-113">하드웨어 준비</span><span class="sxs-lookup"><span data-stu-id="950b7-113">Prepare the hardware</span></span>

<span data-ttu-id="950b7-114">하드웨어 구성 요소를 사용 하 여 다음 다이어그램에 표시 된 대로 회로를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="MCP3008 ADC 및 potentiometer를 사용 하는 회로를 보여 주는 Fritzing 다이어그램" lightbox="../media/rpi-trimpot_spi.png":::

<span data-ttu-id="950b7-116">MCP3008는 SPI (직렬 주변 장치 인터페이스)를 사용 하 여 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-116">The MCP3008 uses Serial Peripheral Interface (SPI) to communicate.</span></span> <span data-ttu-id="950b7-117">다음은 MCP3008에서 Raspberry Pi 및 potentiometer로의 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-117">The following are the connections from the MCP3008 to the Raspberry Pi and potentiometer:</span></span>

- <span data-ttu-id="950b7-118">V<sub>DD</sub> 에서 3.3 v (빨간색으로 표시)</span><span class="sxs-lookup"><span data-stu-id="950b7-118">V<sub>DD</sub> to 3.3V (shown in red)</span></span>
- <span data-ttu-id="950b7-119">V<sub>REF</sub> -3.3 v (빨강)</span><span class="sxs-lookup"><span data-stu-id="950b7-119">V<sub>REF</sub> to 3.3V (red)</span></span>
- <span data-ttu-id="950b7-120">AGND to 그라운드 (검정)</span><span class="sxs-lookup"><span data-stu-id="950b7-120">AGND to ground (black)</span></span>
- <span data-ttu-id="950b7-121">CLK에서 SCLK (주황색)</span><span class="sxs-lookup"><span data-stu-id="950b7-121">CLK to SCLK (orange)</span></span>
- <span data-ttu-id="950b7-122">차원<sub>확장</sub> (주황색)</span><span class="sxs-lookup"><span data-stu-id="950b7-122">D<sub>OUT</sub> to MISO (orange)</span></span>
- <span data-ttu-id="950b7-123">MOSI<sub>의</sub> D (주황)</span><span class="sxs-lookup"><span data-stu-id="950b7-123">D<sub>IN</sub> to MOSI (orange)</span></span>
- <span data-ttu-id="950b7-124">CS/SHDN to CE0 (녹색)</span><span class="sxs-lookup"><span data-stu-id="950b7-124">CS/SHDN to CE0 (green)</span></span>
- <span data-ttu-id="950b7-125">DGND (검정)</span><span class="sxs-lookup"><span data-stu-id="950b7-125">DGND to ground (black)</span></span>
- <span data-ttu-id="950b7-126">Potentiometer (노랑)의 CH0 to variable (중간) 핀</span><span class="sxs-lookup"><span data-stu-id="950b7-126">CH0 to variable (middle) pin on potentiometer (yellow)</span></span>

<span data-ttu-id="950b7-127">Potentiometer의 외부 핀에 3.3 V 및 접지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-127">Supply 3.3V and ground to the outer pins on the potentiometer.</span></span> <span data-ttu-id="950b7-128">순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-128">Order is unimportant.</span></span>

<span data-ttu-id="950b7-129">필요에 따라 다음 핀아웃 다이어그램을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="950b7-129">Refer to the following pinout diagrams as needed:</span></span>

| <span data-ttu-id="950b7-130">MCP3008</span><span class="sxs-lookup"><span data-stu-id="950b7-130">MCP3008</span></span>  | <span data-ttu-id="950b7-131">Raspberry Pi GPIO</span><span class="sxs-lookup"><span data-stu-id="950b7-131">Raspberry Pi GPIO</span></span> |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="MCP3008의 핀아웃를 보여 주는 다이어그램" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Raspberry Pi GPIO 헤더의 핀아웃를 표시 하는 다이어그램입니다. Image 경칭 Raspberry Pi Foundation입니다." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="950b7-134">[Image 경칭 Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/)입니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-134">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="950b7-135">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="950b7-135">Create the app</span></span>

<span data-ttu-id="950b7-136">선호 하는 개발 환경에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-136">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="950b7-137">[.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-137">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="950b7-138">이름을 *Adctutorial* 로 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-138">Name it *AdcTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="950b7-139">*Program.cs* 의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-139">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    <span data-ttu-id="950b7-140">위의 코드에서</span><span class="sxs-lookup"><span data-stu-id="950b7-140">In the preceding code:</span></span>

    - <span data-ttu-id="950b7-141">`hardwareSpiSettings` 는의 새 인스턴스로 설정 됩니다 `SpiConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="950b7-141">`hardwareSpiSettings` is set to a new instance of `SpiConnectionSettings`.</span></span> <span data-ttu-id="950b7-142">생성자는 `busId` 매개 변수를 0으로 설정 하 고 매개 변수를 0으로 설정 합니다 `chipSelectLine` .</span><span class="sxs-lookup"><span data-stu-id="950b7-142">The constructor sets the `busId` parameter to 0 and the `chipSelectLine` parameter to 0.</span></span>
    - <span data-ttu-id="950b7-143">[Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 를 `SpiDevice` 호출 `SpiDevice.Create` 하 고를 전달 하 여의 인스턴스를 만듭니다 `hardwareSpiSettings` .</span><span class="sxs-lookup"><span data-stu-id="950b7-143">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `SpiDevice` by calling `SpiDevice.Create` and passing in `hardwareSpiSettings`.</span></span> <span data-ttu-id="950b7-144">이 `SpiDevice` 는 SPI 버스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-144">This `SpiDevice` represents the SPI bus.</span></span> <span data-ttu-id="950b7-145">`using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-145">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="950b7-146">다른 `using` 선언은의 인스턴스를 만들고 `Mcp3008` 을 `SpiDevice` 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-146">Another `using` declaration creates an instance of `Mcp3008` and passes the `SpiDevice` into the constructor.</span></span>
    - <span data-ttu-id="950b7-147">`while`루프는 무기한 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="950b7-148">각 반복:</span><span class="sxs-lookup"><span data-stu-id="950b7-148">Each iteration:</span></span>
        1. <span data-ttu-id="950b7-149">을 호출 하 여 ADC에서 CH0의 값을 읽습니다 `mcp.Read(0)` .</span><span class="sxs-lookup"><span data-stu-id="950b7-149">Reads the value of CH0 on the ADC by calling `mcp.Read(0)`.</span></span>
        1. <span data-ttu-id="950b7-150">10.24로 값을 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-150">Divides the value by 10.24.</span></span> <span data-ttu-id="950b7-151">MCP3008는 10 비트 ADC 이며 0-1023 범위의 1024 가능한 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-151">The MCP3008 is a 10-bit ADC, which means it returns 1024 possible values ranging 0-1023.</span></span> <span data-ttu-id="950b7-152">값을 10.24로 나누면 값을 백분율로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-152">Dividing the value by 10.24 represents the value as a percentage.</span></span>
        1. <span data-ttu-id="950b7-153">값을 가장 가까운 정수로 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-153">Rounds the value to the nearest integer.</span></span>
        1. <span data-ttu-id="950b7-154">값을 백분율로 형식이 지정 된 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-154">Writes the value to the console formatted as a percentage.</span></span>
        1. <span data-ttu-id="950b7-155">500 밀리초를 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-155">Sleeps 500 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="950b7-156">배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-156">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./AdcTutorial
    ```

    <span data-ttu-id="950b7-157">Potentiometer 다이얼을 회전할 때 출력을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-157">Observe the output as you rotate the potentiometer dial.</span></span> <span data-ttu-id="950b7-158">이는 potentiometer가 ADC의 CH0에 제공 된 전압을 변경 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-158">This is due to the potentiometer varying the voltage supplied to CH0 on the ADC.</span></span> <span data-ttu-id="950b7-159">ADC는 CH0의 입력 전압을 V<sub>REF</sub> 에 제공 된 참조 전압과 비교 하 여 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-159">The ADC compares the input voltage on CH0 to the reference voltage supplied to V<sub>REF</sub> to generate a value.</span></span>

1. <span data-ttu-id="950b7-160"><kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-160">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="950b7-161">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="950b7-161">Congratulations!</span></span> <span data-ttu-id="950b7-162">SPI를 사용 하 여 아날로그에서 디지털로의 변환기에서 값을 읽었습니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-162">You've used SPI to read values from an analog-to-digital converter.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="950b7-163">소스 코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="950b7-163">Get the source code</span></span>

<span data-ttu-id="950b7-164">이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).</span><span class="sxs-lookup"><span data-stu-id="950b7-164">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).</span></span>

## <a name="next-steps"></a><span data-ttu-id="950b7-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="950b7-165">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="950b7-166">범용 입/출력을 사용 하 여 LED를 깜박이게 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="950b7-166">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
