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
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a>.NET IoT 라이브러리를 사용 하 여 IoT 장치용 앱 개발

.NET은 다양 한 플랫폼과 아키텍처에서 실행 됩니다. Raspberry Pi 및 Hummingboard와 같은 일반적인 IoT (사물 인터넷) 보드가 지원 됩니다. IoT 앱은 일반적으로 센서, 아날로그에서 디지털 변환기 및 LCD 장치와 같은 특수 한 하드웨어와 상호 작용 합니다. .NET IoT 라이브러리는 이러한 시나리오를 가능 하 게 합니다.

## <a name="video-overview"></a>비디오 개요

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a>라이브러리

.NET IoT 라이브러리는 두 개의 NuGet 패키지로 구성 됩니다.

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span>
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span>

### <a name="systemdevicegpio"></a>System.Device.Gpio

`System.Device.Gpio` 는 하위 수준 하드웨어 핀과 상호 작용 하 여 장치를 제어 하기 위한 다양 한 프로토콜을 지원 합니다. 이러한 위협은 다음과 같습니다.

- 범용 i/o (GPIO)
- Inter-Integrated 회로 (I2C)
- SPI (직렬 주변 장치 인터페이스)
- 펄스 두께 변조 (PWM))
- 직렬 포트

### <a name="iotdevicebindings"></a>Iot.Device.Bindings

`Iot.Device.Bindings`패키지:

* [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> 시스템. 장치를 래핑하여 앱 개발을 간소화 하는 장치 바인딩을 포함 합니다.
* 는 커뮤니티에서 지원 되며 추가 바인딩은 지속적으로 추가 됩니다.

일반적으로 사용 되는 장치 바인딩은 다음과 같습니다.

- [CharacterLcd-LCD 문자 표시](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [SN74HC595-8 비트 시프트 레지스터](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [Max7219-LED 매트릭스 드라이버](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [RGBLEDMATRIX LED 매트릭스](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="supported-operating-systems"></a>지원되는 운영 체제

`System.Device.Gpio` 는 ARM/ARM64 및 Windows 10 IoT Core를 지 원하는 대부분의 Linux 버전에서 지원 됩니다.

> [!TIP]
> Raspberry Pi의 경우 [Raspberry PI OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (이전의 Raspbian)를 권장 합니다.  

## <a name="supported-hardware-platforms"></a>지원 되는 하드웨어 플랫폼

`System.Device.Gpio` 는 대부분의 단일 보드 플랫폼과 호환 됩니다. 권장 되는 플랫폼은 Raspberry Pi (2 이상) 및 Hummingboard입니다. 호환 되는 것으로 알려진 다른 플랫폼은 BeagleBoard 및 ODROID입니다.

PC 플랫폼은 USB-SPI/I2C 브리지를 사용 하 여 지원 됩니다.

> [!IMPORTANT]
> Raspberry Pi 2 이전의 Raspberry Pi 및 Raspberry Pi 장치를 비롯 한 ARMv6 아키텍처 장치에서는 .NET이 지원 되지 않습니다.

## <a name="resources"></a>리소스

- [Github의 .Net IoT 라이브러리](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span>
