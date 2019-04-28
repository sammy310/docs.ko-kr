---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924009"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="5ebc4-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="5ebc4-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="5ebc4-103">속성</span><span class="sxs-lookup"><span data-stu-id="5ebc4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ebc4-104">ID</span><span class="sxs-lookup"><span data-stu-id="5ebc4-104">ID</span></span>|<span data-ttu-id="5ebc4-105">1126</span><span class="sxs-lookup"><span data-stu-id="5ebc4-105">1126</span></span>|  
|<span data-ttu-id="5ebc4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5ebc4-106">Keywords</span></span>|<span data-ttu-id="5ebc4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5ebc4-107">WFRuntime</span></span>|  
|<span data-ttu-id="5ebc4-108">수준</span><span class="sxs-lookup"><span data-stu-id="5ebc4-108">Level</span></span>|<span data-ttu-id="5ebc4-109">정보</span><span class="sxs-lookup"><span data-stu-id="5ebc4-109">Information</span></span>|  
|<span data-ttu-id="5ebc4-110">채널</span><span class="sxs-lookup"><span data-stu-id="5ebc4-110">Channel</span></span>|<span data-ttu-id="5ebc4-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="5ebc4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ebc4-112">설명</span><span class="sxs-lookup"><span data-stu-id="5ebc4-112">Description</span></span>  
 <span data-ttu-id="5ebc4-113">InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ebc4-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ebc4-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5ebc4-114">Message</span></span>  
 <span data-ttu-id="5ebc4-115">작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebc4-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="5ebc4-116">%2</span><span class="sxs-lookup"><span data-stu-id="5ebc4-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ebc4-117">설명</span><span class="sxs-lookup"><span data-stu-id="5ebc4-117">Details</span></span>  
  
|<span data-ttu-id="5ebc4-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5ebc4-118">Data Item Name</span></span>|<span data-ttu-id="5ebc4-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5ebc4-119">Data Item Type</span></span>|<span data-ttu-id="5ebc4-120">설명</span><span class="sxs-lookup"><span data-stu-id="5ebc4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ebc4-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="5ebc4-121">InvokeMethod</span></span>|<span data-ttu-id="5ebc4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ebc4-122">xs:string</span></span>|<span data-ttu-id="5ebc4-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ebc4-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="5ebc4-124">예외</span><span class="sxs-lookup"><span data-stu-id="5ebc4-124">Exception</span></span>|<span data-ttu-id="5ebc4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ebc4-125">xs:string</span></span>|<span data-ttu-id="5ebc4-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="5ebc4-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="5ebc4-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5ebc4-127">AppDomain</span></span>|<span data-ttu-id="5ebc4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ebc4-128">xs:string</span></span>|<span data-ttu-id="5ebc4-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5ebc4-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
