---
description: '자세히 알아보기: ReliableSessionBindingElement'
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 582fd62a8751a31c2834b7d81219a237c9887236
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743865"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="cdca2-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="cdca2-103">ReliableSessionBindingElement</span></span>

<span data-ttu-id="cdca2-104">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="cdca2-104">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdca2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdca2-105">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cdca2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="cdca2-106">Methods</span></span>  

 <span data-ttu-id="cdca2-107">ReliableSessionBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-107">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cdca2-108">속성</span><span class="sxs-lookup"><span data-stu-id="cdca2-108">Properties</span></span>  

 <span data-ttu-id="cdca2-109">ReliableSessionBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-109">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="cdca2-110">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="cdca2-110">AcknowledgementInterval</span></span>  

 <span data-ttu-id="cdca2-111">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="cdca2-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="cdca2-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-113">팩터리에서 만든 신뢰할 수 있는 채널의 메시지 소스에 승인을 보내기 전에 대상이 대기하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-113">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="cdca2-114">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="cdca2-114">FlowControlEnabled</span></span>  

 <span data-ttu-id="cdca2-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="cdca2-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="cdca2-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-117">흐름 제어 활성화 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-117">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="cdca2-118">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="cdca2-118">InactivityTimeout</span></span>  

 <span data-ttu-id="cdca2-119">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="cdca2-119">Data type: datetime</span></span>  
  
 <span data-ttu-id="cdca2-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-121">통신 상대방이 메시지를 보내지 않아도 채널에서 오류로 간주하지 않도록 허용하는 최대 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-121">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="cdca2-122">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="cdca2-122">MaxPendingChannels</span></span>  

 <span data-ttu-id="cdca2-123">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="cdca2-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="cdca2-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-125">수신기에서 수락하기까지 대기할 수 있는 최대 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-125">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="cdca2-126">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="cdca2-126">MaxRetryCount</span></span>  

 <span data-ttu-id="cdca2-127">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="cdca2-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="cdca2-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-129">신뢰할 수 있는 채널이 기본 채널에서 `Send`를 호출하여 아직 승인을 받지 않은 메시지를 다시 전송하기 위해 시도할 수 있는 최대 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-129">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="cdca2-130">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="cdca2-130">MaxTransferWindowSize</span></span>  

 <span data-ttu-id="cdca2-131">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="cdca2-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="cdca2-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-133">신뢰할 수 있는 세션에 대한 최대 전송 창 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-133">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="cdca2-134">주문됨</span><span class="sxs-lookup"><span data-stu-id="cdca2-134">Ordered</span></span>  

 <span data-ttu-id="cdca2-135">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="cdca2-135">Data type: boolean</span></span>  
  
 <span data-ttu-id="cdca2-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-137">메시지가 전송된 순서대로 도착하도록 보장하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-137">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="cdca2-138">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="cdca2-138">ReliableMessagingVersion</span></span>  

 <span data-ttu-id="cdca2-139">데이터 형식: integer</span><span class="sxs-lookup"><span data-stu-id="cdca2-139">Data type: integer</span></span>  
  
 <span data-ttu-id="cdca2-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="cdca2-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cdca2-141">신뢰할 수 있는 세션에 사용된 WS-ReliableMessaging 프로토콜을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-141">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdca2-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdca2-142">Requirements</span></span>  
  
|<span data-ttu-id="cdca2-143">MOF</span><span class="sxs-lookup"><span data-stu-id="cdca2-143">MOF</span></span>|<span data-ttu-id="cdca2-144">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cdca2-145">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="cdca2-145">Namespace</span></span>|<span data-ttu-id="cdca2-146">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdca2-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cdca2-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdca2-147">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
