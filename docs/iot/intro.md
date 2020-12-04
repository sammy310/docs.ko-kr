---
title: .NET IoT 라이브러리를 사용 하 여 IoT 장치용 앱 개발
description: .NET을 사용 하 여 IoT 장치 및 시나리오용 응용 프로그램을 빌드하는 방법을 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: c3d05ec5b05780f91404c3c27e91bcd602b0faeb
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594028"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a><span data-ttu-id="dc255-103">.NET IoT 라이브러리를 사용 하 여 IoT 장치용 앱 개발</span><span class="sxs-lookup"><span data-stu-id="dc255-103">Develop apps for IoT devices with the .NET IoT Libraries</span></span>

<span data-ttu-id="dc255-104">.NET은 다양 한 플랫폼과 아키텍처에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-104">.NET runs on a variety of platforms and architectures.</span></span> <span data-ttu-id="dc255-105">Raspberry Pi 및 Hummingboard와 같은 일반적인 IoT (사물 인터넷) 보드가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-105">Common Internet of things (IoT) boards, such as Raspberry Pi and Hummingboard, are supported.</span></span> <span data-ttu-id="dc255-106">IoT 앱은 일반적으로 센서, 아날로그에서 디지털 변환기 및 LCD 장치와 같은 특수 한 하드웨어와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-106">IoT apps typically interact with specialized hardware, such as sensors, analog-to-digital converters, and LCD devices.</span></span> <span data-ttu-id="dc255-107">.NET IoT 라이브러리는 이러한 시나리오를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-107">The .NET IoT Libraries enable these scenarios.</span></span>

## <a name="video-overview"></a><span data-ttu-id="dc255-108">비디오 개요</span><span class="sxs-lookup"><span data-stu-id="dc255-108">Video overview</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a><span data-ttu-id="dc255-109">라이브러리</span><span class="sxs-lookup"><span data-stu-id="dc255-109">Libraries</span></span>

<span data-ttu-id="dc255-110">.NET IoT 라이브러리는 두 개의 NuGet 패키지로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-110">The .NET IoT Libraries are composed of two NuGet packages:</span></span>

- <span data-ttu-id="dc255-111">[System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-111">[System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="dc255-112">[Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-112">[Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

### <a name="systemdevicegpio"></a><span data-ttu-id="dc255-113">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="dc255-113">System.Device.Gpio</span></span>

<span data-ttu-id="dc255-114">`System.Device.Gpio` 는 하위 수준 하드웨어 핀과 상호 작용 하 여 장치를 제어 하기 위한 다양 한 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-114">`System.Device.Gpio` supports a variety of protocols for interacting with low-level hardware pins to control devices.</span></span> <span data-ttu-id="dc255-115">이러한 위협은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-115">These include:</span></span>

- <span data-ttu-id="dc255-116">범용 i/o (GPIO)</span><span class="sxs-lookup"><span data-stu-id="dc255-116">General-purpose I/O (GPIO)</span></span>
- <span data-ttu-id="dc255-117">Inter-Integrated 회로 (I2C)</span><span class="sxs-lookup"><span data-stu-id="dc255-117">Inter-Integrated Circuit (I2C)</span></span>
- <span data-ttu-id="dc255-118">SPI (직렬 주변 장치 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="dc255-118">Serial Peripheral Interface (SPI)</span></span>
- <span data-ttu-id="dc255-119">펄스 두께 변조 (PWM))</span><span class="sxs-lookup"><span data-stu-id="dc255-119">Pulse Width Modulation (PWM)</span></span>
- <span data-ttu-id="dc255-120">직렬 포트</span><span class="sxs-lookup"><span data-stu-id="dc255-120">Serial port</span></span>

### <a name="iotdevicebindings"></a><span data-ttu-id="dc255-121">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="dc255-121">Iot.Device.Bindings</span></span>

<span data-ttu-id="dc255-122">`Iot.Device.Bindings`패키지:</span><span class="sxs-lookup"><span data-stu-id="dc255-122">The `Iot.Device.Bindings` package:</span></span>

* <span data-ttu-id="dc255-123">[device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> 시스템. 장치를 래핑하여 앱 개발을 간소화 하는 장치 바인딩을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-123">Contains [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> to streamline app development by wrapping System.Device.Gpio.</span></span>
* <span data-ttu-id="dc255-124">는 커뮤니티에서 지원 되며 추가 바인딩은 지속적으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-124">Is community-supported, and additional bindings are added continually.</span></span>

<span data-ttu-id="dc255-125">일반적으로 사용 되는 장치 바인딩은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-125">Commonly used device bindings include:</span></span>

- <span data-ttu-id="dc255-126">[CharacterLcd-LCD 문자 표시](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-126">[CharacterLcd - LCD character display](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="dc255-127">[SN74HC595-8 비트 시프트 레지스터](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-127">[SN74HC595 - 8-bit shift register](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="dc255-128">[BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-128">[BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="dc255-129">[Max7219-LED 매트릭스 드라이버](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-129">[Max7219 - LED Matrix driver](https://github.com/dotnet/iot/tree/master/src/devices/Max7219) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="dc255-130">[RGBLEDMATRIX LED 매트릭스](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-130">[RGBLedMatrix - RGB LED Matrix](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="dc255-131">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="dc255-131">Supported operating systems</span></span>

<span data-ttu-id="dc255-132">`System.Device.Gpio` 는 ARM/ARM64 및 Windows 10 IoT Core를 지 원하는 대부분의 Linux 버전에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-132">`System.Device.Gpio` is supported on most versions of Linux that support ARM/ARM64 and Windows 10 IoT Core.</span></span>

> [!TIP]
> <span data-ttu-id="dc255-133">Raspberry Pi의 경우 [Raspberry PI OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (이전의 Raspbian)를 권장 합니다.  </span><span class="sxs-lookup"><span data-stu-id="dc255-133">For Raspberry Pi, [Raspberry Pi OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  <span class="docon docon-navigate-external x-hidden-focus"></span> (formerly Raspbian) is recommended.</span></span>

## <a name="supported-hardware-platforms"></a><span data-ttu-id="dc255-134">지원 되는 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="dc255-134">Supported hardware platforms</span></span>

<span data-ttu-id="dc255-135">`System.Device.Gpio` 는 대부분의 단일 보드 플랫폼과 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-135">`System.Device.Gpio` is compatible with most single-board platforms.</span></span> <span data-ttu-id="dc255-136">권장 되는 플랫폼은 Raspberry Pi (2 이상) 및 Hummingboard입니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-136">Recommended platforms are Raspberry Pi (2 and greater) and Hummingboard.</span></span> <span data-ttu-id="dc255-137">호환 되는 것으로 알려진 다른 플랫폼은 BeagleBoard 및 ODROID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-137">Other platforms known to be compatible are BeagleBoard and ODROID.</span></span>

<span data-ttu-id="dc255-138">PC 플랫폼은 USB-SPI/I2C 브리지를 사용 하 여 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-138">PC platforms are supported via the use of a USB to SPI/I2C bridge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc255-139">Raspberry Pi 2 이전의 Raspberry Pi 및 Raspberry Pi 장치를 비롯 한 ARMv6 아키텍처 장치에서는 .NET이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc255-139">.NET is not supported on ARMv6 architecture devices, including Raspberry Pi Zero and Raspberry Pi devices prior to Raspberry Pi 2.</span></span>

## <a name="resources"></a><span data-ttu-id="dc255-140">리소스</span><span class="sxs-lookup"><span data-stu-id="dc255-140">Resources</span></span>

- <span data-ttu-id="dc255-141">[Github의 .Net IoT 라이브러리](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="dc255-141">[.NET IoT Libraries on Github](https://github.com/dotnet/iot) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
