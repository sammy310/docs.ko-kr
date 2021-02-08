---
description: '자세히 알아보기: OneWayBindingElement'
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 9c2ccc301bd854c7b85fcc53551ed6def329a8fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803089"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="f071d-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="f071d-103">OneWayBindingElement</span></span>

<span data-ttu-id="f071d-104">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="f071d-104">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f071d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f071d-105">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f071d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f071d-106">Methods</span></span>  

 <span data-ttu-id="f071d-107">OneWayBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-107">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f071d-108">속성</span><span class="sxs-lookup"><span data-stu-id="f071d-108">Properties</span></span>  

 <span data-ttu-id="f071d-109">OneWayBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-109">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="f071d-110">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f071d-110">ChannelPoolSettings</span></span>  

 <span data-ttu-id="f071d-111">데이터 형식: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f071d-111">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="f071d-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f071d-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f071d-113">채널 풀 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-113">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="f071d-114">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="f071d-114">MaxAcceptedChannels</span></span>  

 <span data-ttu-id="f071d-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="f071d-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="f071d-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f071d-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f071d-117">허용되는 최대 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-117">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="f071d-118">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="f071d-118">PacketRoutable</span></span>  

 <span data-ttu-id="f071d-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="f071d-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="f071d-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f071d-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f071d-121">패킷을 라우팅할 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-121">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f071d-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f071d-122">Requirements</span></span>  
  
|<span data-ttu-id="f071d-123">MOF</span><span class="sxs-lookup"><span data-stu-id="f071d-123">MOF</span></span>|<span data-ttu-id="f071d-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f071d-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f071d-125">Namespace</span></span>|<span data-ttu-id="f071d-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f071d-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f071d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f071d-127">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
