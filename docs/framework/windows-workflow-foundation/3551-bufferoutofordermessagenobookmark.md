---
description: '자세한 정보: 3551-BufferOutOfOrderMessageNoBookmark'
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 573056fed1753ac55c51d9a074047e8eea15e229
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777998"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="e68ff-103">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="e68ff-103">3551 - BufferOutOfOrderMessageNoBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="e68ff-104">속성</span><span class="sxs-lookup"><span data-stu-id="e68ff-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e68ff-105">ID</span><span class="sxs-lookup"><span data-stu-id="e68ff-105">ID</span></span>|<span data-ttu-id="e68ff-106">3551</span><span class="sxs-lookup"><span data-stu-id="e68ff-106">3551</span></span>|  
|<span data-ttu-id="e68ff-107">키워드</span><span class="sxs-lookup"><span data-stu-id="e68ff-107">Keywords</span></span>|<span data-ttu-id="e68ff-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="e68ff-108">WFServices</span></span>|  
|<span data-ttu-id="e68ff-109">Level</span><span class="sxs-lookup"><span data-stu-id="e68ff-109">Level</span></span>|<span data-ttu-id="e68ff-110">정보</span><span class="sxs-lookup"><span data-stu-id="e68ff-110">Information</span></span>|  
|<span data-ttu-id="e68ff-111">채널</span><span class="sxs-lookup"><span data-stu-id="e68ff-111">Channel</span></span>|<span data-ttu-id="e68ff-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="e68ff-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e68ff-113">설명</span><span class="sxs-lookup"><span data-stu-id="e68ff-113">Description</span></span>  

 <span data-ttu-id="e68ff-114">책갈피 다시 시작이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-114">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="e68ff-115">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 버퍼링된 수신 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-115">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e68ff-116">메시지</span><span class="sxs-lookup"><span data-stu-id="e68ff-116">Message</span></span>  

 <span data-ttu-id="e68ff-117">현재는 서비스 인스턴스 '%1'에서 '%2' 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-117">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="e68ff-118">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-118">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e68ff-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e68ff-119">Details</span></span>  
  
|<span data-ttu-id="e68ff-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e68ff-120">Data Item Name</span></span>|<span data-ttu-id="e68ff-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e68ff-121">Data Item Type</span></span>|<span data-ttu-id="e68ff-122">설명</span><span class="sxs-lookup"><span data-stu-id="e68ff-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e68ff-123">OperationName</span><span class="sxs-lookup"><span data-stu-id="e68ff-123">OperationName</span></span>|<span data-ttu-id="e68ff-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e68ff-124">xs:string</span></span>|<span data-ttu-id="e68ff-125">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-125">The name of the operation.</span></span>|  
|<span data-ttu-id="e68ff-126">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="e68ff-126">ServiceInstanceId</span></span>|<span data-ttu-id="e68ff-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e68ff-127">xs:string</span></span>|<span data-ttu-id="e68ff-128">서비스 인스턴스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-128">The id of the service instance.</span></span>|  
|<span data-ttu-id="e68ff-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e68ff-129">AppDomain</span></span>|<span data-ttu-id="e68ff-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e68ff-130">xs:string</span></span>|<span data-ttu-id="e68ff-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e68ff-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
