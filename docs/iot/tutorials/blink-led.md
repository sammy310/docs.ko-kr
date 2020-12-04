---
title: LED 깜박이기
description: .NET IoT 라이브러리를 사용 하 여 LED를 깜박이는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 07a050c0655f9cae3d7f2b924c0dd07ac1c6c0b9
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594148"
---
# <a name="blink-an-led"></a><span data-ttu-id="ec5c1-103">LED 깜박이기</span><span class="sxs-lookup"><span data-stu-id="ec5c1-103">Blink an LED</span></span>

<span data-ttu-id="ec5c1-104">범용 i/o (GPIO) 핀은 개별적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-104">General-purpose I/O (GPIO) pins can be controlled individually.</span></span> <span data-ttu-id="ec5c1-105">이는 Led, 릴레이 및 기타 상태 저장 장치를 제어 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-105">This is useful for controlling LEDs, relays, and other stateful devices.</span></span> <span data-ttu-id="ec5c1-106">이 항목에서는 .NET 및 Raspberry Pi의 GPIO 핀을 사용 하 여 LED를 켜고 반복적으로 깜박임 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-106">In this topic, you will use .NET and your Raspberry Pi's GPIO pins to power an LED and blink it repeatedly.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec5c1-107">필수 조건</span><span class="sxs-lookup"><span data-stu-id="ec5c1-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="ec5c1-108">5mm LED</span><span class="sxs-lookup"><span data-stu-id="ec5c1-108">5 mm LED</span></span>
- <span data-ttu-id="ec5c1-109">330 Ω 저항기</span><span class="sxs-lookup"><span data-stu-id="ec5c1-109">330 Ω resistor</span></span>
- <span data-ttu-id="ec5c1-110">브레드보드</span><span class="sxs-lookup"><span data-stu-id="ec5c1-110">Breadboard</span></span>
- <span data-ttu-id="ec5c1-111">점퍼 와이어</span><span class="sxs-lookup"><span data-stu-id="ec5c1-111">Jumper wires</span></span>
- <span data-ttu-id="ec5c1-112">Raspberry Pi GPIO 브레이크 보드 보드 (선택 사항/권장)</span><span class="sxs-lookup"><span data-stu-id="ec5c1-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="ec5c1-113">하드웨어 준비</span><span class="sxs-lookup"><span data-stu-id="ec5c1-113">Prepare the hardware</span></span>

<span data-ttu-id="ec5c1-114">하드웨어 구성 요소를 사용 하 여 다음 다이어그램에 표시 된 대로 회로를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="LED와 저항기를 사용 하는 회로를 보여 주는 Fritzing 다이어그램" lightbox="../media/rpi-led_bb.png":::

<span data-ttu-id="ec5c1-116">위의 이미지는 다음 연결을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-116">The image above depicts the following connections:</span></span>

- <span data-ttu-id="ec5c1-117">GPIO 18 to LED 양극 (길수록 긍정적인 리드)</span><span class="sxs-lookup"><span data-stu-id="ec5c1-117">GPIO 18 to LED anode (longer, positive lead)</span></span>
- <span data-ttu-id="ec5c1-118">LED 음극 (짧은 리드, 부정 리드) ~ 330 Ω 저항기 (끝)</span><span class="sxs-lookup"><span data-stu-id="ec5c1-118">LED cathode (shorter, negative lead) to 330 Ω resistor (either end)</span></span>
- <span data-ttu-id="ec5c1-119">330 Ω 저항기 (기타 끝)를 접지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-119">330 Ω resistor (other end) to ground</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="ec5c1-120">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ec5c1-120">Create the app</span></span>

<span data-ttu-id="ec5c1-121">선호 하는 개발 환경에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-121">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="ec5c1-122">[.NET CLI](../../core/tools/dotnet-new.md) 또는 [Visual Studio](../../core/tutorials/with-visual-studio.md)중 하나를 사용 하 여 새 .net 콘솔 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-122">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="ec5c1-123">이름을 *Blinktutorial* 으로 이름 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-123">Name it *BlinkTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="ec5c1-124">*Program.cs* 의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-124">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    <span data-ttu-id="ec5c1-125">앞의 코드에서 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-125">In the preceding code:</span></span>

    - <span data-ttu-id="ec5c1-126">[Using 선언은](../../csharp/whats-new/csharp-8.md#using-declarations) 의 인스턴스를 만듭니다 `GpioController` .</span><span class="sxs-lookup"><span data-stu-id="ec5c1-126">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `GpioController`.</span></span> <span data-ttu-id="ec5c1-127">`using`선언은 개체가 삭제 되 고 하드웨어 리소스가 제대로 해제 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-127">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="ec5c1-128">출력에 대 한 GPIO 핀 18이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-128">GPIO pin 18 is opened for output</span></span>
    - <span data-ttu-id="ec5c1-129">`while`루프는 무기한 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-129">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="ec5c1-130">각 반복:</span><span class="sxs-lookup"><span data-stu-id="ec5c1-130">Each iteration:</span></span>
        1. <span data-ttu-id="ec5c1-131">GPIO 핀 18에 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-131">Writes a value to GPIO pin 18.</span></span> <span data-ttu-id="ec5c1-132">`ledOn`가 true 이면는 `PinValue.High` (on)를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-132">If `ledOn` is true, it writes `PinValue.High` (on).</span></span> <span data-ttu-id="ec5c1-133">그렇지 않으면를 씁니다 `PinValue.Low` .</span><span class="sxs-lookup"><span data-stu-id="ec5c1-133">Otherwise, it writes `PinValue.Low`.</span></span>
        1. <span data-ttu-id="ec5c1-134">1000 밀리초를 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-134">Sleeps 1000 ms.</span></span>
        1. <span data-ttu-id="ec5c1-135">의 값을 설정/해제 `ledOn` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-135">Toggles the value of `ledOn`.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="ec5c1-136">배포 디렉터리로 전환 하 고 실행 파일을 실행 하 여 Raspberry Pi에서 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-136">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./BlinkTutorial
    ```

    <span data-ttu-id="ec5c1-137">LED는 매 초 마다 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-137">The LED blinks off and on every second.</span></span>

1. <span data-ttu-id="ec5c1-138"><kbd>Ctrl + C</kbd>를 눌러 프로그램을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-138">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="ec5c1-139">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="ec5c1-139">Congratulations!</span></span> <span data-ttu-id="ec5c1-140">GPIO를 사용 하 여 LED를 깜박임 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5c1-140">You've used GPIO to blink an LED.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="ec5c1-141">소스 코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="ec5c1-141">Get the source code</span></span>

<span data-ttu-id="ec5c1-142">이 자습서의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="ec5c1-142">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec5c1-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ec5c1-143">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ec5c1-144">센서에서 환경 조건을 읽는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="ec5c1-144">Learn how to read environmental conditions from a sensor</span></span>](../tutorials/temp-sensor.md)
