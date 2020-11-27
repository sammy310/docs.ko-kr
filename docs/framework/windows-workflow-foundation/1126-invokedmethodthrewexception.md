---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 7caaebe42f49a62fec61ba17a4d3fe3a538e2ab4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262842"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="43041-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="43041-102">1126 - InvokedMethodThrewException</span></span>

## <a name="properties"></a><span data-ttu-id="43041-103">속성</span><span class="sxs-lookup"><span data-stu-id="43041-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43041-104">ID</span><span class="sxs-lookup"><span data-stu-id="43041-104">ID</span></span>|<span data-ttu-id="43041-105">1126</span><span class="sxs-lookup"><span data-stu-id="43041-105">1126</span></span>|  
|<span data-ttu-id="43041-106">키워드</span><span class="sxs-lookup"><span data-stu-id="43041-106">Keywords</span></span>|<span data-ttu-id="43041-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="43041-107">WFRuntime</span></span>|  
|<span data-ttu-id="43041-108">Level</span><span class="sxs-lookup"><span data-stu-id="43041-108">Level</span></span>|<span data-ttu-id="43041-109">정보</span><span class="sxs-lookup"><span data-stu-id="43041-109">Information</span></span>|  
|<span data-ttu-id="43041-110">채널</span><span class="sxs-lookup"><span data-stu-id="43041-110">Channel</span></span>|<span data-ttu-id="43041-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="43041-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="43041-112">Description</span><span class="sxs-lookup"><span data-stu-id="43041-112">Description</span></span>  

 <span data-ttu-id="43041-113">InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43041-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="43041-114">메시지</span><span class="sxs-lookup"><span data-stu-id="43041-114">Message</span></span>  

 <span data-ttu-id="43041-115">작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43041-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="43041-116">%2</span><span class="sxs-lookup"><span data-stu-id="43041-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="43041-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="43041-117">Details</span></span>  
  
|<span data-ttu-id="43041-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="43041-118">Data Item Name</span></span>|<span data-ttu-id="43041-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="43041-119">Data Item Type</span></span>|<span data-ttu-id="43041-120">Description</span><span class="sxs-lookup"><span data-stu-id="43041-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="43041-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="43041-121">InvokeMethod</span></span>|<span data-ttu-id="43041-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="43041-122">xs:string</span></span>|<span data-ttu-id="43041-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="43041-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="43041-124">예외</span><span class="sxs-lookup"><span data-stu-id="43041-124">Exception</span></span>|<span data-ttu-id="43041-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="43041-125">xs:string</span></span>|<span data-ttu-id="43041-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="43041-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="43041-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="43041-127">AppDomain</span></span>|<span data-ttu-id="43041-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="43041-128">xs:string</span></span>|<span data-ttu-id="43041-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="43041-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
