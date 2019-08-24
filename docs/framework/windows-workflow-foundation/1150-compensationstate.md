---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923866"
---
# <a name="1150---compensationstate"></a><span data-ttu-id="10663-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="10663-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="10663-103">속성</span><span class="sxs-lookup"><span data-stu-id="10663-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10663-104">ID</span><span class="sxs-lookup"><span data-stu-id="10663-104">ID</span></span>|<span data-ttu-id="10663-105">1150</span><span class="sxs-lookup"><span data-stu-id="10663-105">1150</span></span>|  
|<span data-ttu-id="10663-106">키워드</span><span class="sxs-lookup"><span data-stu-id="10663-106">Keywords</span></span>|<span data-ttu-id="10663-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="10663-107">WFActivities</span></span>|  
|<span data-ttu-id="10663-108">수준</span><span class="sxs-lookup"><span data-stu-id="10663-108">Level</span></span>|<span data-ttu-id="10663-109">정보</span><span class="sxs-lookup"><span data-stu-id="10663-109">Information</span></span>|  
|<span data-ttu-id="10663-110">채널</span><span class="sxs-lookup"><span data-stu-id="10663-110">Channel</span></span>|<span data-ttu-id="10663-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="10663-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10663-112">설명</span><span class="sxs-lookup"><span data-stu-id="10663-112">Description</span></span>  
 <span data-ttu-id="10663-113">CompensableActivity에서 상태 변경을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10663-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10663-114">메시지</span><span class="sxs-lookup"><span data-stu-id="10663-114">Message</span></span>  
 <span data-ttu-id="10663-115">CompensableActivity '%1'은(는) '%2' 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10663-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10663-116">설명</span><span class="sxs-lookup"><span data-stu-id="10663-116">Details</span></span>  
  
|<span data-ttu-id="10663-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="10663-117">Data Item Name</span></span>|<span data-ttu-id="10663-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="10663-118">Data Item Type</span></span>|<span data-ttu-id="10663-119">설명</span><span class="sxs-lookup"><span data-stu-id="10663-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10663-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="10663-120">DisplayName</span></span>|<span data-ttu-id="10663-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="10663-121">xs:string</span></span>|<span data-ttu-id="10663-122">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10663-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="10663-123">상태</span><span class="sxs-lookup"><span data-stu-id="10663-123">State</span></span>|<span data-ttu-id="10663-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="10663-124">xs:string</span></span>|<span data-ttu-id="10663-125">보정 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10663-125">The compensation state.</span></span>|  
|<span data-ttu-id="10663-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10663-126">AppDomain</span></span>|<span data-ttu-id="10663-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="10663-127">xs:string</span></span>|<span data-ttu-id="10663-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10663-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
