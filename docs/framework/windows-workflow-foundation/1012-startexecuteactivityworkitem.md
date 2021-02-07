---
description: '자세한 정보: 1012-StartExecuteActivityWorkItem'
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: 3b57fc6d37a6708a4e22537de87a2566612088e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99714887"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="73373-103">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="73373-103">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="73373-104">속성</span><span class="sxs-lookup"><span data-stu-id="73373-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73373-105">ID</span><span class="sxs-lookup"><span data-stu-id="73373-105">ID</span></span>|<span data-ttu-id="73373-106">1012</span><span class="sxs-lookup"><span data-stu-id="73373-106">1012</span></span>|  
|<span data-ttu-id="73373-107">키워드</span><span class="sxs-lookup"><span data-stu-id="73373-107">Keywords</span></span>|<span data-ttu-id="73373-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="73373-108">WFRuntime</span></span>|  
|<span data-ttu-id="73373-109">Level</span><span class="sxs-lookup"><span data-stu-id="73373-109">Level</span></span>|<span data-ttu-id="73373-110">자세히</span><span class="sxs-lookup"><span data-stu-id="73373-110">Verbose</span></span>|  
|<span data-ttu-id="73373-111">채널</span><span class="sxs-lookup"><span data-stu-id="73373-111">Channel</span></span>|<span data-ttu-id="73373-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="73373-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73373-113">설명</span><span class="sxs-lookup"><span data-stu-id="73373-113">Description</span></span>  

 <span data-ttu-id="73373-114">ExecuteActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73373-114">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73373-115">메시지</span><span class="sxs-lookup"><span data-stu-id="73373-115">Message</span></span>  

 <span data-ttu-id="73373-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="73373-116">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73373-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="73373-117">Details</span></span>  
  
|<span data-ttu-id="73373-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="73373-118">Data Item Name</span></span>|<span data-ttu-id="73373-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="73373-119">Data Item Type</span></span>|<span data-ttu-id="73373-120">설명</span><span class="sxs-lookup"><span data-stu-id="73373-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73373-121">활동</span><span class="sxs-lookup"><span data-stu-id="73373-121">Activity</span></span>|<span data-ttu-id="73373-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="73373-122">xs:string</span></span>|<span data-ttu-id="73373-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73373-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="73373-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="73373-124">DisplayName</span></span>|<span data-ttu-id="73373-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="73373-125">xs:string</span></span>|<span data-ttu-id="73373-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73373-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="73373-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="73373-127">InstanceId</span></span>|<span data-ttu-id="73373-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="73373-128">xs:string</span></span>|<span data-ttu-id="73373-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="73373-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="73373-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73373-130">AppDomain</span></span>|<span data-ttu-id="73373-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="73373-131">xs:string</span></span>|<span data-ttu-id="73373-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="73373-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
