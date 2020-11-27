---
title: 4818 - InnerChannelOpenFailed
ms.date: 03/30/2017
ms.assetid: c8ac6447-4fbb-4e08-ab26-91acae48dd11
ms.openlocfilehash: c0db97add82bed91e8e7e3ae763f6f52361b86b3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285787"
---
# <a name="4818---innerchannelopenfailed"></a><span data-ttu-id="347ca-102">4818 - InnerChannelOpenFailed</span><span class="sxs-lookup"><span data-stu-id="347ca-102">4818 - InnerChannelOpenFailed</span></span>

## <a name="properties"></a><span data-ttu-id="347ca-103">속성</span><span class="sxs-lookup"><span data-stu-id="347ca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="347ca-104">ID</span><span class="sxs-lookup"><span data-stu-id="347ca-104">ID</span></span>|<span data-ttu-id="347ca-105">4818</span><span class="sxs-lookup"><span data-stu-id="347ca-105">4818</span></span>|  
|<span data-ttu-id="347ca-106">키워드</span><span class="sxs-lookup"><span data-stu-id="347ca-106">Keywords</span></span>|<span data-ttu-id="347ca-107">검색</span><span class="sxs-lookup"><span data-stu-id="347ca-107">Discovery</span></span>|  
|<span data-ttu-id="347ca-108">Level</span><span class="sxs-lookup"><span data-stu-id="347ca-108">Level</span></span>|<span data-ttu-id="347ca-109">경고</span><span class="sxs-lookup"><span data-stu-id="347ca-109">Warning</span></span>|  
|<span data-ttu-id="347ca-110">채널</span><span class="sxs-lookup"><span data-stu-id="347ca-110">Channel</span></span>|<span data-ttu-id="347ca-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="347ca-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="347ca-112">Description</span><span class="sxs-lookup"><span data-stu-id="347ca-112">Description</span></span>  

 <span data-ttu-id="347ca-113">이 이벤트는 DiscoveryClientChannel이 검색된 엔드포인트로 채널을 열지 못할 경우 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="347ca-113">This event is emitted when the DiscoveryClientChannel failed to open the channel with a discovered endpoint.</span></span> <span data-ttu-id="347ca-114">DiscoveryClientChannel은 이제 사용 가능한 다음 엔드포인트로 검색된 엔드포인트를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="347ca-114">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="message"></a><span data-ttu-id="347ca-115">메시지</span><span class="sxs-lookup"><span data-stu-id="347ca-115">Message</span></span>  

 <span data-ttu-id="347ca-116">DiscoveryClientChannel에서 EndpointAddress='%1' 및 Via='%2'을(를) 사용하는 검색된 엔드포인트로 채널을 열지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="347ca-116">The DiscoveryClientChannel failed to open the channel with a discovered endpoint with EndpointAddress='%1' and Via='%2'.</span></span> <span data-ttu-id="347ca-117">DiscoveryClientChannel은 이제 사용 가능한 다음 엔드포인트로 검색된 엔드포인트를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="347ca-117">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="347ca-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="347ca-118">Details</span></span>
