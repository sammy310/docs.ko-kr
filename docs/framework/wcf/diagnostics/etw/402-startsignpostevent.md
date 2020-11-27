---
title: 402 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: ff32c900f4e357b7f1eca669a0ea60f80ea24b19
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258324"
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="0e890-102">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="0e890-102">402 - StartSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="0e890-103">속성</span><span class="sxs-lookup"><span data-stu-id="0e890-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e890-104">ID</span><span class="sxs-lookup"><span data-stu-id="0e890-104">ID</span></span>|<span data-ttu-id="0e890-105">402</span><span class="sxs-lookup"><span data-stu-id="0e890-105">402</span></span>|  
|<span data-ttu-id="0e890-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0e890-106">Keywords</span></span>|<span data-ttu-id="0e890-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="0e890-107">Troubleshooting</span></span>|  
|<span data-ttu-id="0e890-108">Level</span><span class="sxs-lookup"><span data-stu-id="0e890-108">Level</span></span>|<span data-ttu-id="0e890-109">정보</span><span class="sxs-lookup"><span data-stu-id="0e890-109">Information</span></span>|  
|<span data-ttu-id="0e890-110">채널</span><span class="sxs-lookup"><span data-stu-id="0e890-110">Channel</span></span>|<span data-ttu-id="0e890-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="0e890-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e890-112">Description</span><span class="sxs-lookup"><span data-stu-id="0e890-112">Description</span></span>  

 <span data-ttu-id="0e890-113">이 이벤트는 엔드투엔드 동작의 시작을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e890-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="0e890-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e890-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e890-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0e890-115">Message</span></span>  

 <span data-ttu-id="0e890-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="0e890-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e890-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0e890-117">Details</span></span>  
  
|<span data-ttu-id="0e890-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0e890-118">Data Item Name</span></span>|<span data-ttu-id="0e890-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0e890-119">Data Item Type</span></span>|<span data-ttu-id="0e890-120">Description</span><span class="sxs-lookup"><span data-stu-id="0e890-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e890-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="0e890-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="0e890-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e890-122">The name of the activity.</span></span>|  
|<span data-ttu-id="0e890-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e890-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0e890-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0e890-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
