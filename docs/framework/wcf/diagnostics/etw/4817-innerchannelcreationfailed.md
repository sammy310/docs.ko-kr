---
description: '자세한 정보: 4817-InnerChannelCreationFailed'
title: 4817 - InnerChannelCreationFailed
ms.date: 03/30/2017
ms.assetid: c1a20619-beda-49b9-bb64-76b6a009c32b
ms.openlocfilehash: ae6dae8a6ffd090a192301bd9236413765c4f16e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783653"
---
# <a name="4817---innerchannelcreationfailed"></a><span data-ttu-id="bed15-103">4817 - InnerChannelCreationFailed</span><span class="sxs-lookup"><span data-stu-id="bed15-103">4817 - InnerChannelCreationFailed</span></span>

## <a name="properties"></a><span data-ttu-id="bed15-104">속성</span><span class="sxs-lookup"><span data-stu-id="bed15-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bed15-105">ID</span><span class="sxs-lookup"><span data-stu-id="bed15-105">ID</span></span>|<span data-ttu-id="bed15-106">4817</span><span class="sxs-lookup"><span data-stu-id="bed15-106">4817</span></span>|  
|<span data-ttu-id="bed15-107">키워드</span><span class="sxs-lookup"><span data-stu-id="bed15-107">Keywords</span></span>|<span data-ttu-id="bed15-108">검색</span><span class="sxs-lookup"><span data-stu-id="bed15-108">Discovery</span></span>|  
|<span data-ttu-id="bed15-109">Level</span><span class="sxs-lookup"><span data-stu-id="bed15-109">Level</span></span>|<span data-ttu-id="bed15-110">경고</span><span class="sxs-lookup"><span data-stu-id="bed15-110">Warning</span></span>|  
|<span data-ttu-id="bed15-111">채널</span><span class="sxs-lookup"><span data-stu-id="bed15-111">Channel</span></span>|<span data-ttu-id="bed15-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="bed15-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bed15-113">설명</span><span class="sxs-lookup"><span data-stu-id="bed15-113">Description</span></span>  

 <span data-ttu-id="bed15-114">이 이벤트는 DiscoveryClientChannel이 검색된 엔드포인트로 채널을 만들지 못할 경우 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="bed15-114">This event is emitted when the DiscoveryClientChannel failed to create the channel with a discovered endpoint.</span></span> <span data-ttu-id="bed15-115">DiscoveryClientChannel은 이제 사용 가능한 다음 엔드포인트로 검색된 엔드포인트를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bed15-115">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bed15-116">메시지</span><span class="sxs-lookup"><span data-stu-id="bed15-116">Message</span></span>  

 <span data-ttu-id="bed15-117">DiscoveryClientChannel에서 EndpointAddress='%1' 및 Via='%2'을(를) 사용하는 검색된 엔드포인트로 채널을 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="bed15-117">The DiscoveryClientChannel failed to create the channel with a discovered endpoint with EndpointAddress='%1' and Via='%2'.</span></span> <span data-ttu-id="bed15-118">DiscoveryClientChannel은 이제 사용 가능한 다음 엔드포인트로 검색된 엔드포인트를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bed15-118">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bed15-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="bed15-119">Details</span></span>
