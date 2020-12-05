---
title: 빠른 시작-.NET을 사용 하 여 Raspberry Pi Sense HAT 구동
description: Raspberry Pi 용 추가 기능 보드용 Sense HAT를 사용 하 여 5 분 내에 .NET IoT 라이브러리를 시작 하세요.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 2919db55304590f5557aa0cbda50cc4bd6640443
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739532"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a><span data-ttu-id="94782-103">빠른 시작-.NET을 사용 하 여 Raspberry Pi Sense HAT 구동</span><span class="sxs-lookup"><span data-stu-id="94782-103">Quickstart - Use .NET to drive a Raspberry Pi Sense HAT</span></span>

<span data-ttu-id="94782-104">Raspberry pi [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> ( **T** op의 **H** 하려면 **A** ttached)는 Raspberry Pi의 추가 기능 보드입니다.</span><span class="sxs-lookup"><span data-stu-id="94782-104">The Raspberry Pi [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** ardware **A** ttached on **T** op) is an add-on board for Raspberry Pi.</span></span> <span data-ttu-id="94782-105">Sense HAT에는 8 × 8의 RGB LED 매트릭스와 5 단추 조이스틱이 장착 되어 있으며 다음과 같은 센서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94782-105">The Sense HAT is equipped with an 8×8 RGB LED matrix, a five-button joystick, and includes the following sensors:</span></span>

- <span data-ttu-id="94782-106">자이로스코프</span><span class="sxs-lookup"><span data-stu-id="94782-106">Gyroscope</span></span>
- <span data-ttu-id="94782-107">가속도계</span><span class="sxs-lookup"><span data-stu-id="94782-107">Accelerometer</span></span>
- <span data-ttu-id="94782-108">지자기 센터</span><span class="sxs-lookup"><span data-stu-id="94782-108">Magnetometer</span></span>
- <span data-ttu-id="94782-109">온도</span><span class="sxs-lookup"><span data-stu-id="94782-109">Temperature</span></span>
- <span data-ttu-id="94782-110">바 ometric 압력</span><span class="sxs-lookup"><span data-stu-id="94782-110">Barometric pressure</span></span>
- <span data-ttu-id="94782-111">습도</span><span class="sxs-lookup"><span data-stu-id="94782-111">Humidity</span></span>

<span data-ttu-id="94782-112">이 빠른 시작에서는 .NET을 사용 하 여 Sense HAT에서 센서 값을 검색 하 고, 조이스틱 입력에 응답 하 고, LED 매트릭스를 구동 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-112">This quickstart uses .NET to retrieve sensor values from the Sense HAT, respond to joystick input, and drive the LED matrix.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94782-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="94782-113">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="94782-114">Sense HAT</span><span class="sxs-lookup"><span data-stu-id="94782-114">Sense HAT</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a><span data-ttu-id="94782-115">빠른 시작 실행</span><span class="sxs-lookup"><span data-stu-id="94782-115">Run the quickstart</span></span>

<span data-ttu-id="94782-116">Raspberry Pi에 Sense HAT를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-116">Attach the Sense HAT to your Raspberry Pi.</span></span> <span data-ttu-id="94782-117">Raspberry Pi (로컬 또는 원격)의 Bash 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-117">From a Bash prompt on the Raspberry Pi (local or remote), run the following command:</span></span>

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

<span data-ttu-id="94782-118">명령은 스크립트를 다운로드 하 여 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-118">The command downloads and runs a script.</span></span> <span data-ttu-id="94782-119">스크립트:</span><span class="sxs-lookup"><span data-stu-id="94782-119">The script:</span></span>

- <span data-ttu-id="94782-120">.NET SDK를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-120">Installs the .NET SDK.</span></span>
- <span data-ttu-id="94782-121">Sense HAT 빠른 시작 프로젝트를 포함 하는 GitHub 리포지토리를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-121">Clones a GitHub repository that includes the Sense HAT quickstart project.</span></span>
- <span data-ttu-id="94782-122">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-122">Builds the project.</span></span>
- <span data-ttu-id="94782-123">프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-123">Runs the project.</span></span>

<span data-ttu-id="94782-124">센서 데이터가 표시 되 면 콘솔 출력을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-124">Observe the console output as sensor data is displayed.</span></span> <span data-ttu-id="94782-125">LED 매트릭스는 파란색 필드에 노란색 픽셀을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-125">The LED matrix displays a yellow pixel on a field of blue.</span></span> <span data-ttu-id="94782-126">모든 방향으로 조이스틱을 유지 하면 노란색 픽셀이 해당 방향으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="94782-126">Holding the joystick in any direction moves the yellow pixel in that direction.</span></span> <span data-ttu-id="94782-127">가운데 조이스틱 단추를 클릭 하면 배경이 파란색에서 빨강으로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94782-127">Clicking the center joystick button causes the background to switch from blue to red.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="94782-128">소스 코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="94782-128">Get the source code</span></span>

<span data-ttu-id="94782-129">이 빠른 시작의 소스는 [GitHub에서 사용할 수 있습니다](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="94782-129">The source for this quickstart is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94782-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="94782-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94782-131">범용 입/출력을 사용 하 여 LED를 깜박이게 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="94782-131">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
