---
description: '자세한 정보: 1126-InvokedMethodThrewException'
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 35c4311a4ab7750cc54a5c9ffb379f34b1cb12aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667358"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="a2365-103">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="a2365-103">1126 - InvokedMethodThrewException</span></span>

## <a name="properties"></a><span data-ttu-id="a2365-104">속성</span><span class="sxs-lookup"><span data-stu-id="a2365-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2365-105">ID</span><span class="sxs-lookup"><span data-stu-id="a2365-105">ID</span></span>|<span data-ttu-id="a2365-106">1126</span><span class="sxs-lookup"><span data-stu-id="a2365-106">1126</span></span>|  
|<span data-ttu-id="a2365-107">키워드</span><span class="sxs-lookup"><span data-stu-id="a2365-107">Keywords</span></span>|<span data-ttu-id="a2365-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a2365-108">WFRuntime</span></span>|  
|<span data-ttu-id="a2365-109">Level</span><span class="sxs-lookup"><span data-stu-id="a2365-109">Level</span></span>|<span data-ttu-id="a2365-110">정보</span><span class="sxs-lookup"><span data-stu-id="a2365-110">Information</span></span>|  
|<span data-ttu-id="a2365-111">채널</span><span class="sxs-lookup"><span data-stu-id="a2365-111">Channel</span></span>|<span data-ttu-id="a2365-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="a2365-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a2365-113">설명</span><span class="sxs-lookup"><span data-stu-id="a2365-113">Description</span></span>  

 <span data-ttu-id="a2365-114">InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2365-114">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a2365-115">메시지</span><span class="sxs-lookup"><span data-stu-id="a2365-115">Message</span></span>  

 <span data-ttu-id="a2365-116">작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2365-116">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="a2365-117">%2</span><span class="sxs-lookup"><span data-stu-id="a2365-117">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="a2365-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a2365-118">Details</span></span>  
  
|<span data-ttu-id="a2365-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a2365-119">Data Item Name</span></span>|<span data-ttu-id="a2365-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a2365-120">Data Item Type</span></span>|<span data-ttu-id="a2365-121">설명</span><span class="sxs-lookup"><span data-stu-id="a2365-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a2365-122">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a2365-122">InvokeMethod</span></span>|<span data-ttu-id="a2365-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2365-123">xs:string</span></span>|<span data-ttu-id="a2365-124">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2365-124">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="a2365-125">예외</span><span class="sxs-lookup"><span data-stu-id="a2365-125">Exception</span></span>|<span data-ttu-id="a2365-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2365-126">xs:string</span></span>|<span data-ttu-id="a2365-127">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="a2365-127">The exception details for the exception</span></span>|  
|<span data-ttu-id="a2365-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a2365-128">AppDomain</span></span>|<span data-ttu-id="a2365-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2365-129">xs:string</span></span>|<span data-ttu-id="a2365-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a2365-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
