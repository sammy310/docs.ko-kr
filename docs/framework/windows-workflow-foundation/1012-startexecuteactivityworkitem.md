---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: b9cfceb12d56f93c0f9726849e34f4333f1399ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239642"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="c54dc-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="c54dc-102">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="c54dc-103">속성</span><span class="sxs-lookup"><span data-stu-id="c54dc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c54dc-104">ID</span><span class="sxs-lookup"><span data-stu-id="c54dc-104">ID</span></span>|<span data-ttu-id="c54dc-105">1012</span><span class="sxs-lookup"><span data-stu-id="c54dc-105">1012</span></span>|  
|<span data-ttu-id="c54dc-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c54dc-106">Keywords</span></span>|<span data-ttu-id="c54dc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c54dc-107">WFRuntime</span></span>|  
|<span data-ttu-id="c54dc-108">Level</span><span class="sxs-lookup"><span data-stu-id="c54dc-108">Level</span></span>|<span data-ttu-id="c54dc-109">자세히</span><span class="sxs-lookup"><span data-stu-id="c54dc-109">Verbose</span></span>|  
|<span data-ttu-id="c54dc-110">채널</span><span class="sxs-lookup"><span data-stu-id="c54dc-110">Channel</span></span>|<span data-ttu-id="c54dc-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="c54dc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c54dc-112">Description</span><span class="sxs-lookup"><span data-stu-id="c54dc-112">Description</span></span>  

 <span data-ttu-id="c54dc-113">ExecuteActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c54dc-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c54dc-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c54dc-114">Message</span></span>  

 <span data-ttu-id="c54dc-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c54dc-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c54dc-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c54dc-116">Details</span></span>  
  
|<span data-ttu-id="c54dc-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c54dc-117">Data Item Name</span></span>|<span data-ttu-id="c54dc-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c54dc-118">Data Item Type</span></span>|<span data-ttu-id="c54dc-119">Description</span><span class="sxs-lookup"><span data-stu-id="c54dc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c54dc-120">활동</span><span class="sxs-lookup"><span data-stu-id="c54dc-120">Activity</span></span>|<span data-ttu-id="c54dc-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c54dc-121">xs:string</span></span>|<span data-ttu-id="c54dc-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c54dc-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c54dc-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c54dc-123">DisplayName</span></span>|<span data-ttu-id="c54dc-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c54dc-124">xs:string</span></span>|<span data-ttu-id="c54dc-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c54dc-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c54dc-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c54dc-126">InstanceId</span></span>|<span data-ttu-id="c54dc-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c54dc-127">xs:string</span></span>|<span data-ttu-id="c54dc-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c54dc-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c54dc-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c54dc-129">AppDomain</span></span>|<span data-ttu-id="c54dc-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c54dc-130">xs:string</span></span>|<span data-ttu-id="c54dc-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c54dc-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
