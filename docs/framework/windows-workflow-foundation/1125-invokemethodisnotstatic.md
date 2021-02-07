---
description: '자세한 정보: 1125-InvokeMethodIsNotStatic'
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: cd63b7b75121a70f7d7bad6a799827971aa4eae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667371"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="deae2-103">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="deae2-103">1125 - InvokeMethodIsNotStatic</span></span>

## <a name="properties"></a><span data-ttu-id="deae2-104">속성</span><span class="sxs-lookup"><span data-stu-id="deae2-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="deae2-105">ID</span><span class="sxs-lookup"><span data-stu-id="deae2-105">ID</span></span>|<span data-ttu-id="deae2-106">1125</span><span class="sxs-lookup"><span data-stu-id="deae2-106">1125</span></span>|  
|<span data-ttu-id="deae2-107">키워드</span><span class="sxs-lookup"><span data-stu-id="deae2-107">Keywords</span></span>|<span data-ttu-id="deae2-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="deae2-108">WFRuntime</span></span>|  
|<span data-ttu-id="deae2-109">Level</span><span class="sxs-lookup"><span data-stu-id="deae2-109">Level</span></span>|<span data-ttu-id="deae2-110">정보</span><span class="sxs-lookup"><span data-stu-id="deae2-110">Information</span></span>|  
|<span data-ttu-id="deae2-111">채널</span><span class="sxs-lookup"><span data-stu-id="deae2-111">Channel</span></span>|<span data-ttu-id="deae2-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="deae2-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="deae2-113">설명</span><span class="sxs-lookup"><span data-stu-id="deae2-113">Description</span></span>  

 <span data-ttu-id="deae2-114">CacheMetadata 단계 중 InvokeMethod 작업에서 호출할 메서드가 정적이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="deae2-114">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="deae2-115">메시지</span><span class="sxs-lookup"><span data-stu-id="deae2-115">Message</span></span>  

 <span data-ttu-id="deae2-116">InvokeMethod ''%1' - 메서드가 Static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="deae2-116">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="deae2-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="deae2-117">Details</span></span>  
  
|<span data-ttu-id="deae2-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="deae2-118">Data Item Name</span></span>|<span data-ttu-id="deae2-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="deae2-119">Data Item Type</span></span>|<span data-ttu-id="deae2-120">설명</span><span class="sxs-lookup"><span data-stu-id="deae2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="deae2-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="deae2-121">InvokeMethod</span></span>|<span data-ttu-id="deae2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="deae2-122">xs:string</span></span>|<span data-ttu-id="deae2-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="deae2-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="deae2-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="deae2-124">AppDomain</span></span>|<span data-ttu-id="deae2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="deae2-125">xs:string</span></span>|<span data-ttu-id="deae2-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="deae2-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
