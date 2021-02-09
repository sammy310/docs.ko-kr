---
description: '자세한 정보: NetworkInformation'
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: 9092fd0593d9046f419018b882c08066a6bc654c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785707"
---
# <a name="networkinformation"></a><span data-ttu-id="7c4bd-103">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="7c4bd-103">NetworkInformation</span></span>

<span data-ttu-id="7c4bd-104"><xref:System.Net.NetworkInformation> 네임스페이스를 사용하면 네트워크 이벤트, 변경 사항, 통계 및 속성에 대한 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-104">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="7c4bd-105"><xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> 클래스를 사용하여 원격 호스트에 연결 가능한지도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-105">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="7c4bd-106">네트워크 가용성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="7c4bd-106">Network Availability and Events</span></span>  

 <span data-ttu-id="7c4bd-107"><xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> 클래스를 사용하면 네트워크 주소 또는 가용성이 변경되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-107">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="7c4bd-108">이 클래스를 사용하려면 이벤트 처리기를 만들어 변경 사항을 처리한 다음 <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> 또는 <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-108">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="7c4bd-109">자세한 내용은 [방법: 네트워크 가용성 및 주소 변경 검색](how-to-detect-network-availability-and-address-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-109">For more information, see [How to: Detect Network Availability and Address Changes](how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="7c4bd-110">네트워크 통계 및 속성</span><span class="sxs-lookup"><span data-stu-id="7c4bd-110">Network Statistics and Properties</span></span>  

 <span data-ttu-id="7c4bd-111">인터페이스 또는 프로토콜을 기반으로 네트워크 통계 및 속성을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-111">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="7c4bd-112"><xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> 및 <xref:System.Net.NetworkInformation.PhysicalAddress> 클래스는 특정 네트워크 인터페이스에 대한 정보를 제공하는 반면 <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> 및 <xref:System.Net.NetworkInformation.UdpStatistics> 클래스는 계층 3 및 계층 4 패킷에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-112">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="7c4bd-113">자세한 내용은 [방법: 인터페이스 및 프로토콜 정보 가져오기](how-to-get-interface-and-protocol-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-113">For more information, see [How to: Get Interface and Protocol Information](how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="7c4bd-114">원격 호스트에 연결 가능한지 확인</span><span class="sxs-lookup"><span data-stu-id="7c4bd-114">Determine if a Remote Host is Reachable</span></span>  

 <span data-ttu-id="7c4bd-115"><xref:System.Net.NetworkInformation.Ping> 클래스를 사용하여 원격 호스트가 가동되어 네트워크에 있으며 연결 가능한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-115">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="7c4bd-116">자세한 내용은 [방법: 호스트에 대해 ping 실행](how-to-ping-a-host.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c4bd-116">For more information, see [How to: Ping a Host](how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4bd-117">참조</span><span class="sxs-lookup"><span data-stu-id="7c4bd-117">See also</span></span>

- [<span data-ttu-id="7c4bd-118">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="7c4bd-118">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
