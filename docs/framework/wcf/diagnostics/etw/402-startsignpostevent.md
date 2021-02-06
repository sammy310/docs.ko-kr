---
description: '자세한 정보: 402-StartSignpostEvent'
title: 402 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: e77cac50be2a2e96fabe1301aaeab7ff74142e5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99656685"
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="4a56c-103">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="4a56c-103">402 - StartSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="4a56c-104">속성</span><span class="sxs-lookup"><span data-stu-id="4a56c-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a56c-105">ID</span><span class="sxs-lookup"><span data-stu-id="4a56c-105">ID</span></span>|<span data-ttu-id="4a56c-106">402</span><span class="sxs-lookup"><span data-stu-id="4a56c-106">402</span></span>|  
|<span data-ttu-id="4a56c-107">키워드</span><span class="sxs-lookup"><span data-stu-id="4a56c-107">Keywords</span></span>|<span data-ttu-id="4a56c-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="4a56c-108">Troubleshooting</span></span>|  
|<span data-ttu-id="4a56c-109">Level</span><span class="sxs-lookup"><span data-stu-id="4a56c-109">Level</span></span>|<span data-ttu-id="4a56c-110">정보</span><span class="sxs-lookup"><span data-stu-id="4a56c-110">Information</span></span>|  
|<span data-ttu-id="4a56c-111">채널</span><span class="sxs-lookup"><span data-stu-id="4a56c-111">Channel</span></span>|<span data-ttu-id="4a56c-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="4a56c-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4a56c-113">설명</span><span class="sxs-lookup"><span data-stu-id="4a56c-113">Description</span></span>  

 <span data-ttu-id="4a56c-114">이 이벤트는 엔드투엔드 동작의 시작을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a56c-114">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="4a56c-115">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a56c-115">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4a56c-116">메시지</span><span class="sxs-lookup"><span data-stu-id="4a56c-116">Message</span></span>  

 <span data-ttu-id="4a56c-117">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="4a56c-117">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4a56c-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4a56c-118">Details</span></span>  
  
|<span data-ttu-id="4a56c-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4a56c-119">Data Item Name</span></span>|<span data-ttu-id="4a56c-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4a56c-120">Data Item Type</span></span>|<span data-ttu-id="4a56c-121">설명</span><span class="sxs-lookup"><span data-stu-id="4a56c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4a56c-122">Extended Data</span><span class="sxs-lookup"><span data-stu-id="4a56c-122">Extended Data</span></span>|`xs:string`|<span data-ttu-id="4a56c-123">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a56c-123">The name of the activity.</span></span>|  
|<span data-ttu-id="4a56c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4a56c-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4a56c-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4a56c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
