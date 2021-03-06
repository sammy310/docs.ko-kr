---
title: .NET IoT 라이브러리를 사용 하 여 IoT 장치용 앱 개발
description: .NET을 사용 하 여 IoT 장치 및 시나리오용 응용 프로그램을 빌드하는 방법을 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: 13460fdafbfd7ef4e047cb7537e832ae4039c614
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255433"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a><span data-ttu-id="954b9-103">.NET IoT 라이브러리를 사용 하 여 IoT 장치용 앱 개발</span><span class="sxs-lookup"><span data-stu-id="954b9-103">Develop apps for IoT devices with the .NET IoT Libraries</span></span>

<span data-ttu-id="954b9-104">.NET은 다양 한 플랫폼과 아키텍처에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-104">.NET runs on a variety of platforms and architectures.</span></span> <span data-ttu-id="954b9-105">Raspberry Pi 및 Hummingboard와 같은 일반적인 IoT (사물 인터넷) 보드가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-105">Common Internet of things (IoT) boards, such as Raspberry Pi and Hummingboard, are supported.</span></span> <span data-ttu-id="954b9-106">IoT 앱은 일반적으로 센서, 아날로그에서 디지털 변환기 및 LCD 장치와 같은 특수 한 하드웨어와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-106">IoT apps typically interact with specialized hardware, such as sensors, analog-to-digital converters, and LCD devices.</span></span> <span data-ttu-id="954b9-107">.NET IoT 라이브러리는 이러한 시나리오를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-107">The .NET IoT Libraries enable these scenarios.</span></span>

## <a name="video-overview"></a><span data-ttu-id="954b9-108">비디오 개요</span><span class="sxs-lookup"><span data-stu-id="954b9-108">Video overview</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a><span data-ttu-id="954b9-109">라이브러리</span><span class="sxs-lookup"><span data-stu-id="954b9-109">Libraries</span></span>

<span data-ttu-id="954b9-110">.NET IoT 라이브러리는 두 개의 NuGet 패키지로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-110">The .NET IoT Libraries are composed of two NuGet packages:</span></span>

- [<span data-ttu-id="954b9-111">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="954b9-111">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/)
- [<span data-ttu-id="954b9-112">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="954b9-112">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/)

### <a name="systemdevicegpio"></a><span data-ttu-id="954b9-113">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="954b9-113">System.Device.Gpio</span></span>

<span data-ttu-id="954b9-114">`System.Device.Gpio` 는 하위 수준 하드웨어 핀과 상호 작용 하 여 장치를 제어 하기 위한 다양 한 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-114">`System.Device.Gpio` supports a variety of protocols for interacting with low-level hardware pins to control devices.</span></span> <span data-ttu-id="954b9-115">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-115">These include:</span></span>

- <span data-ttu-id="954b9-116">범용 i/o (GPIO)</span><span class="sxs-lookup"><span data-stu-id="954b9-116">General-purpose I/O (GPIO)</span></span>
- <span data-ttu-id="954b9-117">Inter-Integrated 회로 (I2C)</span><span class="sxs-lookup"><span data-stu-id="954b9-117">Inter-Integrated Circuit (I2C)</span></span>
- <span data-ttu-id="954b9-118">SPI (직렬 주변 장치 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="954b9-118">Serial Peripheral Interface (SPI)</span></span>
- <span data-ttu-id="954b9-119">펄스 두께 변조 (PWM))</span><span class="sxs-lookup"><span data-stu-id="954b9-119">Pulse Width Modulation (PWM)</span></span>
- <span data-ttu-id="954b9-120">직렬 포트</span><span class="sxs-lookup"><span data-stu-id="954b9-120">Serial port</span></span>

### <a name="iotdevicebindings"></a><span data-ttu-id="954b9-121">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="954b9-121">Iot.Device.Bindings</span></span>

<span data-ttu-id="954b9-122">`Iot.Device.Bindings`패키지:</span><span class="sxs-lookup"><span data-stu-id="954b9-122">The `Iot.Device.Bindings` package:</span></span>

* <span data-ttu-id="954b9-123">시스템. 장치를 래핑하여 앱 개발을 간소화 하는 [장치 바인딩을](https://github.com/dotnet/iot/blob/master/src/devices/README.md) 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-123">Contains [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) to streamline app development by wrapping System.Device.Gpio.</span></span>
* <span data-ttu-id="954b9-124">는 커뮤니티에서 지원 되며 추가 바인딩은 지속적으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-124">Is community-supported, and additional bindings are added continually.</span></span>

<span data-ttu-id="954b9-125">일반적으로 사용 되는 장치 바인딩은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-125">Commonly used device bindings include:</span></span>

- [<span data-ttu-id="954b9-126">CharacterLcd-LCD 문자 표시</span><span class="sxs-lookup"><span data-stu-id="954b9-126">CharacterLcd - LCD character display</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)
- [<span data-ttu-id="954b9-127">SN74HC595-8 비트 시프트 레지스터</span><span class="sxs-lookup"><span data-stu-id="954b9-127">SN74HC595 - 8-bit shift register</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)
- [<span data-ttu-id="954b9-128">BrickPi3</span><span class="sxs-lookup"><span data-stu-id="954b9-128">BrickPi3</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)
- [<span data-ttu-id="954b9-129">Max7219-LED 매트릭스 드라이버</span><span class="sxs-lookup"><span data-stu-id="954b9-129">Max7219 - LED Matrix driver</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)
- [<span data-ttu-id="954b9-130">RGBLedMatrix LED 매트릭스</span><span class="sxs-lookup"><span data-stu-id="954b9-130">RGBLedMatrix - RGB LED Matrix</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)

## <a name="supported-operating-systems"></a><span data-ttu-id="954b9-131">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="954b9-131">Supported operating systems</span></span>

<span data-ttu-id="954b9-132">`System.Device.Gpio` 는 ARM/ARM64 및 Windows 10 IoT Core를 지 원하는 대부분의 Linux 버전에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-132">`System.Device.Gpio` is supported on most versions of Linux that support ARM/ARM64 and Windows 10 IoT Core.</span></span>

> [!TIP]
> <span data-ttu-id="954b9-133">Raspberry Pi의 경우 [Raspberry PI OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  (이전의 Raspbian)를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-133">For Raspberry Pi, [Raspberry Pi OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  (formerly Raspbian) is recommended.</span></span>

## <a name="supported-hardware-platforms"></a><span data-ttu-id="954b9-134">지원 되는 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="954b9-134">Supported hardware platforms</span></span>

<span data-ttu-id="954b9-135">`System.Device.Gpio` 는 대부분의 단일 보드 플랫폼과 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-135">`System.Device.Gpio` is compatible with most single-board platforms.</span></span> <span data-ttu-id="954b9-136">권장 되는 플랫폼은 Raspberry Pi (2 이상) 및 Hummingboard입니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-136">Recommended platforms are Raspberry Pi (2 and greater) and Hummingboard.</span></span> <span data-ttu-id="954b9-137">호환 되는 것으로 알려진 다른 플랫폼은 BeagleBoard 및 ODROID입니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-137">Other platforms known to be compatible are BeagleBoard and ODROID.</span></span>

<span data-ttu-id="954b9-138">PC 플랫폼은 USB-SPI/I2C 브리지를 사용 하 여 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-138">PC platforms are supported via the use of a USB to SPI/I2C bridge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="954b9-139">Raspberry Pi 2 이전의 Raspberry Pi 및 Raspberry Pi 장치를 비롯 한 ARMv6 아키텍처 장치에서는 .NET이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954b9-139">.NET is not supported on ARMv6 architecture devices, including Raspberry Pi Zero and Raspberry Pi devices prior to Raspberry Pi 2.</span></span>

## <a name="resources"></a><span data-ttu-id="954b9-140">리소스</span><span class="sxs-lookup"><span data-stu-id="954b9-140">Resources</span></span>

- [<span data-ttu-id="954b9-141">Github의 .NET IoT 라이브러리</span><span class="sxs-lookup"><span data-stu-id="954b9-141">.NET IoT Libraries on Github</span></span>](https://github.com/dotnet/iot)
