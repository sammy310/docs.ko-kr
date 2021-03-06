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
# <a name="display-text-on-an-lcd"></a><span data-ttu-id="8531c-103">LCD에 텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="8531c-103">Display text on an LCD</span></span>

<span data-ttu-id="8531c-104">LCD 문자 표시는 외부 모니터가 없어도 정보를 표시 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-104">LCD character displays are useful for displaying information without the need for an external monitor.</span></span> <span data-ttu-id="8531c-105">일반 LCD 문자 표시를 GPIO 핀에 직접 연결할 수 있지만 이러한 방법에는 최대 10 개의 GPIO 핀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-105">Common LCD character displays can be connected directly to the GPIO pins, but such an approach requires the use of up to 10 GPIO pins.</span></span> <span data-ttu-id="8531c-106">여러 장치를 조합 하 여 연결 해야 하는 시나리오의 경우 대부분의 GPIO 헤더를 문자 표시에 devoting 하는 것이 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-106">For scenarios that require connecting to a combination of devices, devoting so much of the GPIO header to a character display is often impractical.</span></span>

<span data-ttu-id="8531c-107">여러 제조업체에서 20x4 LCD 문자 표시와 통합 GPIO 확장기를 판매 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-107">Many manufacturers sell 20x4 LCD character displays with an integrated GPIO expander.</span></span> <span data-ttu-id="8531c-108">문자 표시는 GPIO 확장기에 직접 연결 하 여 I2C (Inter-Integrated 회로) 직렬 프로토콜을 통해 Raspberry Pi에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-108">The character display connects directly to the GPIO expander, which then connects to the Raspberry Pi via the Inter-Integrated Circuit (I2C) serial protocol.</span></span>

<span data-ttu-id="8531c-109">이 항목에서는 .NET을 사용 하 여 I2C GPIO 확장기를 사용 하는 LCD 문자 표시에 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-109">In this topic, you will use .NET to display text on an LCD character display using an I2C GPIO expander.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8531c-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8531c-110">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [<span data-ttu-id="8531c-111">20x4는 I2C 인터페이스를 사용 하 여 LCD 문자 표시</span><span class="sxs-lookup"><span data-stu-id="8531c-111">20x4 LCD Character Display with I2C interface</span></span>](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)
- <span data-ttu-id="8531c-112">점퍼 와이어</span><span class="sxs-lookup"><span data-stu-id="8531c-112">Jumper wires</span></span>
- <span data-ttu-id="8531c-113">실험용 회로판 (선택 사항/권장)</span><span class="sxs-lookup"><span data-stu-id="8531c-113">Breadboard (optional/recommended)</span></span>
- <span data-ttu-id="8531c-114">Raspberry Pi GPIO 브레이크 보드 보드 (선택 사항/권장)</span><span class="sxs-lookup"><span data-stu-id="8531c-114">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> <span data-ttu-id="8531c-115">LCD 문자 표시의 제조업체에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-115">There are many manufacturers of LCD character displays.</span></span> <span data-ttu-id="8531c-116">대부분의 디자인은 동일 하며, 제조업체에서 기능에 대해 어떠한 차이도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-116">Most designs are identical, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="8531c-117">참조용으로이 자습서는 [SUNFOUNDER LCD2004](https://www.sunfounder.com/lcd2004-module.html)를 사용 하 여 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-117">For reference, this tutorial was developed with the [SunFounder LCD2004](https://www.sunfounder.com/lcd2004-module.html).</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="8531c-118">하드웨어 준비</span><span class="sxs-lookup"><span data-stu-id="8531c-118">Prepare the hardware</span></span>

<span data-ttu-id="8531c-119">다음과 같이 점퍼 와이어를 사용 하 여 I2C GPIO 확장기에서 4 개의 핀을 Raspberry Pi에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-119">Use jumper wires to connect the four pins on the I2C GPIO expander to the Raspberry Pi as follows:</span></span>

- <span data-ttu-id="8531c-120">GND</span><span class="sxs-lookup"><span data-stu-id="8531c-120">GND to ground</span></span>
- <span data-ttu-id="8531c-121">VCC를 5V로</span><span class="sxs-lookup"><span data-stu-id="8531c-121">VCC to 5V</span></span>
- <span data-ttu-id="8531c-122">SDA에서 SDA로 (GPIO 2)</span><span class="sxs-lookup"><span data-stu-id="8531c-122">SDA to SDA (GPIO 2)</span></span>
- <span data-ttu-id="8531c-123">SCL에서 SCL (GPIO 3)</span><span class="sxs-lookup"><span data-stu-id="8531c-123">SCL to SCL (GPIO 3)</span></span>

<span data-ttu-id="8531c-124">필요에 따라 다음 그림을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8531c-124">Refer to the following figures as needed:</span></span>

| <span data-ttu-id="8531c-125">I2C 인터페이스 (표시 후면)</span><span class="sxs-lookup"><span data-stu-id="8531c-125">I2C interface (back of display)</span></span> | <span data-ttu-id="8531c-126">Raspberry Pi GPIO</span><span class="sxs-lookup"><span data-stu-id="8531c-126">Raspberry Pi GPIO</span></span> |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="I2C GPIO 확장기를 표시 하는 문자 표시의 뒤쪽 이미지입니다." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Raspberry Pi GPIO 헤더의 핀아웃를 표시 하는 다이어그램입니다. Image 경칭 Raspberry Pi Foundation입니다." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="8531c-129">[Image 경칭 Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/)입니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-129">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="8531c-130">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="8531c-130">Create the app</span></span>

<span data-ttu-id="8531c-131">선호 하는 개발 환경에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-131">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="8531c-132">[.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-132">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="8531c-133">이름을 *LcdTutorial* 로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-133">Name it *LcdTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="8531c-134">*Program.cs* 의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-134">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    <span data-ttu-id="8531c-135">위의 코드에서</span><span class="sxs-lookup"><span data-stu-id="8531c-135">In the preceding code:</span></span>

    - <span data-ttu-id="8531c-136">[Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 를 `I2cDevice` 호출 하 `I2cDevice.Create` 고 `I2cConnectionSettings` `busId` 및 매개 변수를 사용 하 여 새를 전달 하 여의 인스턴스를 만듭니다 `deviceAddress` .</span><span class="sxs-lookup"><span data-stu-id="8531c-136">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in a new `I2cConnectionSettings` with the `busId` and `deviceAddress` parameters.</span></span> <span data-ttu-id="8531c-137">이 `I2cDevice` 는 I2C 버스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-137">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="8531c-138">`using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-138">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>

        > [!WARNING]
        > <span data-ttu-id="8531c-139">GPIO 확장기의 장치 주소는 제조업체에서 사용 하는 칩에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-139">The device address for the GPIO expander depends on the chip used by the manufacturer.</span></span> <span data-ttu-id="8531c-140">PCF8574를 사용 하는 GPIO 확장 기가는 주소를 사용 하 고 PCF8574A 칩을 사용 하는 경우에는를 사용 `0x27` `0x3F` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-140">GPIO expanders equipped with a PCF8574 use the address `0x27`, while those using PCF8574A chips use `0x3F`.</span></span> <span data-ttu-id="8531c-141">LCD 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8531c-141">Consult your LCD's documentation.</span></span>

    - <span data-ttu-id="8531c-142">다른 `using` 선언은의 인스턴스를 만들고 `Pcf8574` 을 `I2cDevice` 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-142">Another `using` declaration creates an instance of `Pcf8574` and passes the `I2cDevice` into the constructor.</span></span> <span data-ttu-id="8531c-143">이 인스턴스는 GPIO 확장기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-143">This instance represents the GPIO expander.</span></span>
    - <span data-ttu-id="8531c-144">다른 `using` 선언은의 인스턴스를 만들어 `Lcd2004` 표시를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-144">Another `using` declaration creates an instance of `Lcd2004` to represent the display.</span></span> <span data-ttu-id="8531c-145">여러 매개 변수는 GPIO 확장기와 통신 하는 데 사용할 설정을 설명 하는 생성자에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-145">Several parameters are passed to the constructor describing the settings to use to communicate with the GPIO expander.</span></span> <span data-ttu-id="8531c-146">GPIO 확장기는 매개 변수로 전달 됩니다 `controller` .</span><span class="sxs-lookup"><span data-stu-id="8531c-146">The GPIO expander is passed as the `controller` parameter.</span></span>
    - <span data-ttu-id="8531c-147">`while`루프는 무기한 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="8531c-148">각 반복:</span><span class="sxs-lookup"><span data-stu-id="8531c-148">Each iteration:</span></span>
        1. <span data-ttu-id="8531c-149">표시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-149">Clears the display.</span></span>
        1. <span data-ttu-id="8531c-150">커서 위치를 현재 줄의 첫 번째 위치로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-150">Sets the cursor position to the first position on the current line.</span></span>
        1. <span data-ttu-id="8531c-151">현재 커서 위치에 표시 되는 현재 시간을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-151">Writes the current time to the display at the current cursor position.</span></span>
        1. <span data-ttu-id="8531c-152">현재 줄 카운터를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-152">Iterates the current line counter.</span></span>
        1. <span data-ttu-id="8531c-153">1000 밀리초를 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-153">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="8531c-154">배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-154">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./LcdTutorial
    ```

    <span data-ttu-id="8531c-155">현재 시간이 각 줄에 표시 되 면 LCD 문자 표시를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-155">Observe the LCD character display as the current time displays on each line.</span></span>

    > [!TIP]
    > <span data-ttu-id="8531c-156">디스플레이가 켜져 있지만 텍스트가 표시 되지 않는 경우 화면 뒷면에서 대비 전화 걸기를 조정 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="8531c-156">If the display is lit but you don't see any text, try adjusting the contrast dial on the back of the display.</span></span>

1. <span data-ttu-id="8531c-157"><kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-157">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="8531c-158">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="8531c-158">Congratulations!</span></span> <span data-ttu-id="8531c-159">I2C 및 GPIO 확장기를 사용 하 여 LCD에 텍스트를 표시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-159">You've displayed text on an LCD using a I2C and a GPIO expander!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="8531c-160">소스 코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="8531c-160">Get the source code</span></span>

<span data-ttu-id="8531c-161">이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial).</span><span class="sxs-lookup"><span data-stu-id="8531c-161">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8531c-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8531c-162">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8531c-163">범용 입/출력을 사용 하 여 LED를 깜박이게 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8531c-163">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
