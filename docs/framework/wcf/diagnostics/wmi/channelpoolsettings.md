---
description: '다음에 대 한 자세한 정보: ChannelPoolSettings'
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: b08c5483e7a0c918393795b4608b9eef16b18341
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757685"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="c7dcd-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c7dcd-103">ChannelPoolSettings</span></span>

<span data-ttu-id="c7dcd-104">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c7dcd-104">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7dcd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7dcd-105">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c7dcd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c7dcd-106">Methods</span></span>  

 <span data-ttu-id="c7dcd-107">ChannelPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-107">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c7dcd-108">속성</span><span class="sxs-lookup"><span data-stu-id="c7dcd-108">Properties</span></span>  

 <span data-ttu-id="c7dcd-109">ChannelPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-109">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="c7dcd-110">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="c7dcd-110">IdleTimeout</span></span>  

 <span data-ttu-id="c7dcd-111">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="c7dcd-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="c7dcd-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c7dcd-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c7dcd-113">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-113">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="c7dcd-114">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="c7dcd-114">LeaseTimeout</span></span>  

 <span data-ttu-id="c7dcd-115">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="c7dcd-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="c7dcd-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c7dcd-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c7dcd-117">시간 제한을 초과하기 전에 대여 작업을 완료하기 위한 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-117">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="c7dcd-118">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c7dcd-118">MaxOutboundChannelsPerEndpoint</span></span>  

 <span data-ttu-id="c7dcd-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="c7dcd-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="c7dcd-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c7dcd-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c7dcd-121">각 엔드포인트에 대한 최대 아웃바운드 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-121">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7dcd-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7dcd-122">Requirements</span></span>  
  
|<span data-ttu-id="c7dcd-123">MOF</span><span class="sxs-lookup"><span data-stu-id="c7dcd-123">MOF</span></span>|<span data-ttu-id="c7dcd-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c7dcd-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c7dcd-125">Namespace</span></span>|<span data-ttu-id="c7dcd-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7dcd-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7dcd-127">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
