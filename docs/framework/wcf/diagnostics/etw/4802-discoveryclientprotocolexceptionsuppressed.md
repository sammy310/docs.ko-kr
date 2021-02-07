---
description: '자세한 정보: 4802-DiscoveryClientProtocolExceptionSuppressed'
title: 4802 - DiscoveryClientProtocolExceptionSuppressed
ms.date: 03/30/2017
ms.assetid: 568212f7-1060-4f5c-a7a0-1352c7cc743b
ms.openlocfilehash: 5183e9de704e4da4d93376eeb1dbe22f48bad918
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744541"
---
# <a name="4802---discoveryclientprotocolexceptionsuppressed"></a><span data-ttu-id="3810f-103">4802 - DiscoveryClientProtocolExceptionSuppressed</span><span class="sxs-lookup"><span data-stu-id="3810f-103">4802 - DiscoveryClientProtocolExceptionSuppressed</span></span>

## <a name="properties"></a><span data-ttu-id="3810f-104">속성</span><span class="sxs-lookup"><span data-stu-id="3810f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3810f-105">ID</span><span class="sxs-lookup"><span data-stu-id="3810f-105">ID</span></span>|<span data-ttu-id="3810f-106">4802</span><span class="sxs-lookup"><span data-stu-id="3810f-106">4802</span></span>|  
|<span data-ttu-id="3810f-107">키워드</span><span class="sxs-lookup"><span data-stu-id="3810f-107">Keywords</span></span>|<span data-ttu-id="3810f-108">검색</span><span class="sxs-lookup"><span data-stu-id="3810f-108">Discovery</span></span>|  
|<span data-ttu-id="3810f-109">Level</span><span class="sxs-lookup"><span data-stu-id="3810f-109">Level</span></span>|<span data-ttu-id="3810f-110">정보</span><span class="sxs-lookup"><span data-stu-id="3810f-110">Information</span></span>|  
|<span data-ttu-id="3810f-111">채널</span><span class="sxs-lookup"><span data-stu-id="3810f-111">Channel</span></span>|<span data-ttu-id="3810f-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3810f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3810f-113">설명</span><span class="sxs-lookup"><span data-stu-id="3810f-113">Description</span></span>  

 <span data-ttu-id="3810f-114">이 이벤트는 DiscoveryClient를 닫는 동안 ProtocolException이 표시되지 않을 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="3810f-114">This event is emitted when the a ProtocolException was suppressed while closing the DiscoveryClient.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3810f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="3810f-115">Message</span></span>  

 <span data-ttu-id="3810f-116">DiscoveryClient를 닫는 동안에는 ProtocolException이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3810f-116">A ProtocolException was suppressed while closing the DiscoveryClient.</span></span> <span data-ttu-id="3810f-117">DiscoveryService가 DiscoveryClient에 응답을 계속 보내려고 하는 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3810f-117">This could be because a DiscoveryService is still trying to send response to the DiscoveryClient.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3810f-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3810f-118">Details</span></span>
