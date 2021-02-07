---
description: '자세히 알아보기: ConnectionOrientedTransportBindingElement'
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: bd0c05fc86ad7bc95837cee7e22ea83975369b62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757581"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="9dc3b-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9dc3b-103">ConnectionOrientedTransportBindingElement</span></span>

<span data-ttu-id="9dc3b-104">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9dc3b-104">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc3b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dc3b-105">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9dc3b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9dc3b-106">Methods</span></span>  

 <span data-ttu-id="9dc3b-107">ConnectionOrientedTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-107">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9dc3b-108">속성</span><span class="sxs-lookup"><span data-stu-id="9dc3b-108">Properties</span></span>  

 <span data-ttu-id="9dc3b-109">ConnectionOrientedTransportBindingElement 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-109">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="9dc3b-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="9dc3b-110">ChannelInitializationTimeout</span></span>  

 <span data-ttu-id="9dc3b-111">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="9dc3b-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="9dc3b-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-113">제한 시간이 초과되기 전에 채널 초기화가 완료되어야 하는 기간을 지정하는 timespan입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-113">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="9dc3b-114">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="9dc3b-114">ConnectionBufferSize</span></span>  

 <span data-ttu-id="9dc3b-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9dc3b-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="9dc3b-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-117">통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-117">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="9dc3b-118">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="9dc3b-118">HostNameComparisonMode</span></span>  

 <span data-ttu-id="9dc3b-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9dc3b-119">Data type: string</span></span>  
  
 <span data-ttu-id="9dc3b-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-121">URI를 일치시킬 때 서비스에 연결하기 위해 호스트 이름이 사용되는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-121">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="9dc3b-122">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="9dc3b-122">MaxBufferSize</span></span>  

 <span data-ttu-id="9dc3b-123">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9dc3b-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="9dc3b-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-125">사용할 버퍼의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-125">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="9dc3b-126">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="9dc3b-126">MaxOutputDelay</span></span>  

 <span data-ttu-id="9dc3b-127">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="9dc3b-127">Data type: datetime</span></span>  
  
 <span data-ttu-id="9dc3b-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-129">메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-129">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="9dc3b-130">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="9dc3b-130">MaxPendingAccepts</span></span>  

 <span data-ttu-id="9dc3b-131">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9dc3b-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="9dc3b-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-133">서비스에서 들어오는 연결을 처리하는 데 사용할 수 있는 보류 중인 최대 비동기 수락 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-133">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="9dc3b-134">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="9dc3b-134">MaxPendingConnections</span></span>  

 <span data-ttu-id="9dc3b-135">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9dc3b-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="9dc3b-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-137">보류 중 연결의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-137">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="9dc3b-138">TransferMode</span><span class="sxs-lookup"><span data-stu-id="9dc3b-138">TransferMode</span></span>  

 <span data-ttu-id="9dc3b-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9dc3b-139">Data type: string</span></span>  
  
 <span data-ttu-id="9dc3b-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9dc3b-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc3b-141">메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-141">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc3b-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9dc3b-142">Requirements</span></span>  
  
|<span data-ttu-id="9dc3b-143">MOF</span><span class="sxs-lookup"><span data-stu-id="9dc3b-143">MOF</span></span>|<span data-ttu-id="9dc3b-144">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9dc3b-145">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9dc3b-145">Namespace</span></span>|<span data-ttu-id="9dc3b-146">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9dc3b-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dc3b-147">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
