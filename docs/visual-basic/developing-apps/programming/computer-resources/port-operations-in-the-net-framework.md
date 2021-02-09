---
description: '자세한 정보: Visual Basic을 사용한 .NET Framework의 포트 작업'
title: .NET Framework의 포트 작업
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 072baac53589f8a5d6405eb786b4e692cbaf6181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641527"
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="c4151-103">Visual Basic을 사용한 .NET Framework의 포트 작업</span><span class="sxs-lookup"><span data-stu-id="c4151-103">Port Operations in the .NET Framework with Visual Basic</span></span>

<span data-ttu-id="c4151-104"><xref:System.IO.Ports?displayProperty=nameWithType> 네임스페이스의 .NET Framework 클래스를 통해 컴퓨터의 직렬 포트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-104">You can access your computer's serial ports through the .NET Framework classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="c4151-105">가장 중요한 클래스인 <xref:System.IO.Ports.SerialPort>는 동기 및 이벤트 구동 I/O, 핀 및 중단 상태 액세스, 그리고 직렬 드라이버 속성 액세스를 위한 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-105">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="c4151-106">이 클래스는 <xref:System.IO.Ports.SerialPort.BaseStream> 속성을 통해 액세스 가능한 <xref:System.IO.Stream> 개체에 래핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-106">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream> property.</span></span> <span data-ttu-id="c4151-107"><xref:System.IO.Stream> 개체에 <xref:System.IO.Ports.SerialPort>를 래핑하면 스트림을 사용하는 클래스가 직렬 포트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-107">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="c4151-108">네임스페이스에는 직렬 포트의 제어를 간소화하는 열거형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-108">The namespace includes enumerations that simplify the control of serial ports.</span></span>

<span data-ttu-id="c4151-109"><xref:System.IO.Ports.SerialPort> 개체를 만드는 가장 간단한 방법은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-109">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="c4151-110">.NET Framework 클래스를 사용하여 병렬 포트, USB 포트 등 다른 유형의 포트에 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-110">You cannot use .NET Framework classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>

## <a name="enumerations"></a><span data-ttu-id="c4151-111">열거형</span><span class="sxs-lookup"><span data-stu-id="c4151-111">Enumerations</span></span>

<span data-ttu-id="c4151-112">이 표에서는 직렬 포트 액세스에 사용되는 주요 열거형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-112">This table lists and describes the main enumerations used for accessing a serial port:</span></span>

|<span data-ttu-id="c4151-113">열거형</span><span class="sxs-lookup"><span data-stu-id="c4151-113">Enumeration</span></span>|<span data-ttu-id="c4151-114">설명</span><span class="sxs-lookup"><span data-stu-id="c4151-114">Description</span></span>|
|---|---|
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="c4151-115"><xref:System.IO.Ports.SerialPort> 개체에 대한 직렬 포트 통신을 설정할 때 사용되는 제어 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-115">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="c4151-116"><xref:System.IO.Ports.SerialPort> 개체에 대한 패리티 비트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-116">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="c4151-117"><xref:System.IO.Ports.SerialPort> 개체의 직렬 포트에서 수신된 문자 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-117">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="c4151-118"><xref:System.IO.Ports.SerialPort> 개체에서 발생하는 오류를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-118">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="c4151-119"><xref:System.IO.Ports.SerialPort> 개체에서 수행된 변경의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-119">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="c4151-120"><xref:System.IO.Ports.SerialPort> 개체에 사용되는 정지 비트의 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4151-120">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c4151-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4151-121">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="c4151-122">컴퓨터 포트에 액세스</span><span class="sxs-lookup"><span data-stu-id="c4151-122">Accessing the Computer's Ports</span></span>](accessing-the-computer-s-ports.md)
