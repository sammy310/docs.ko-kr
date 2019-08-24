---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009957"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="75a37-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="75a37-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="75a37-103">속성</span><span class="sxs-lookup"><span data-stu-id="75a37-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75a37-104">ID</span><span class="sxs-lookup"><span data-stu-id="75a37-104">ID</span></span>|<span data-ttu-id="75a37-105">1131</span><span class="sxs-lookup"><span data-stu-id="75a37-105">1131</span></span>|  
|<span data-ttu-id="75a37-106">키워드</span><span class="sxs-lookup"><span data-stu-id="75a37-106">Keywords</span></span>|<span data-ttu-id="75a37-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="75a37-107">WFRuntime</span></span>|  
|<span data-ttu-id="75a37-108">수준</span><span class="sxs-lookup"><span data-stu-id="75a37-108">Level</span></span>|<span data-ttu-id="75a37-109">정보</span><span class="sxs-lookup"><span data-stu-id="75a37-109">Information</span></span>|  
|<span data-ttu-id="75a37-110">채널</span><span class="sxs-lookup"><span data-stu-id="75a37-110">Channel</span></span>|<span data-ttu-id="75a37-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="75a37-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="75a37-112">설명</span><span class="sxs-lookup"><span data-stu-id="75a37-112">Description</span></span>  
 <span data-ttu-id="75a37-113">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75a37-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="75a37-114">메시지</span><span class="sxs-lookup"><span data-stu-id="75a37-114">Message</span></span>  
 <span data-ttu-id="75a37-115">InvokeMethod '%1'' - 메서드에서 ''%2' 및 '%3'의 비동기 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75a37-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="75a37-116">설명</span><span class="sxs-lookup"><span data-stu-id="75a37-116">Details</span></span>  
  
|<span data-ttu-id="75a37-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="75a37-117">Data Item Name</span></span>|<span data-ttu-id="75a37-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="75a37-118">Data Item Type</span></span>|<span data-ttu-id="75a37-119">설명</span><span class="sxs-lookup"><span data-stu-id="75a37-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="75a37-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="75a37-120">InvokeMethod</span></span>|<span data-ttu-id="75a37-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="75a37-121">xs:string</span></span>|<span data-ttu-id="75a37-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75a37-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="75a37-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="75a37-123">BeginMethod</span></span>|<span data-ttu-id="75a37-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="75a37-124">xs:string</span></span>|<span data-ttu-id="75a37-125">Begin 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75a37-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="75a37-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="75a37-126">EndMethod</span></span>|<span data-ttu-id="75a37-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="75a37-127">xs:string</span></span>|<span data-ttu-id="75a37-128">End 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75a37-128">The name of the end method.</span></span>|  
|<span data-ttu-id="75a37-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="75a37-129">AppDomain</span></span>|<span data-ttu-id="75a37-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="75a37-130">xs:string</span></span>|<span data-ttu-id="75a37-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="75a37-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
