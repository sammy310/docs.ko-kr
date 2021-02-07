---
description: '자세한 정보: 4810-DiscoveryMessageWithNullMessageSequence'
title: 4810 - DiscoveryMessageWithNullMessageSequence
ms.date: 03/30/2017
ms.assetid: aa70573e-8a76-486a-9616-ccca8c7008b6
ms.openlocfilehash: e2c767a0c5a39c75a084c1ebcc114e9d15962cbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760253"
---
# <a name="4810---discoverymessagewithnullmessagesequence"></a><span data-ttu-id="439fd-103">4810 - DiscoveryMessageWithNullMessageSequence</span><span class="sxs-lookup"><span data-stu-id="439fd-103">4810 - DiscoveryMessageWithNullMessageSequence</span></span>

## <a name="properties"></a><span data-ttu-id="439fd-104">속성</span><span class="sxs-lookup"><span data-stu-id="439fd-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="439fd-105">ID</span><span class="sxs-lookup"><span data-stu-id="439fd-105">ID</span></span>|<span data-ttu-id="439fd-106">4810</span><span class="sxs-lookup"><span data-stu-id="439fd-106">4810</span></span>|  
|<span data-ttu-id="439fd-107">키워드</span><span class="sxs-lookup"><span data-stu-id="439fd-107">Keywords</span></span>|<span data-ttu-id="439fd-108">검색</span><span class="sxs-lookup"><span data-stu-id="439fd-108">Discovery</span></span>|  
|<span data-ttu-id="439fd-109">Level</span><span class="sxs-lookup"><span data-stu-id="439fd-109">Level</span></span>|<span data-ttu-id="439fd-110">경고</span><span class="sxs-lookup"><span data-stu-id="439fd-110">Warning</span></span>|  
|<span data-ttu-id="439fd-111">채널</span><span class="sxs-lookup"><span data-stu-id="439fd-111">Channel</span></span>|<span data-ttu-id="439fd-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="439fd-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="439fd-113">설명</span><span class="sxs-lookup"><span data-stu-id="439fd-113">Description</span></span>  

 <span data-ttu-id="439fd-114">이 이벤트는 DiscoveryMessageSequence 속성이 없어 검색 메시지가 DiscoveryClient에서 삭제될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="439fd-114">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="439fd-115">메시지</span><span class="sxs-lookup"><span data-stu-id="439fd-115">Message</span></span>  

 <span data-ttu-id="439fd-116">DiscoveryMessageSequence 속성이 없어 messageId='%2'인 %1 메시지가 DiscoveryClient에서 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="439fd-116">A %1 message with messageId='%2' was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="439fd-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="439fd-117">Details</span></span>
