---
description: '자세한 정보: 2577-TryCatchExceptionDuringCancelation'
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: e02e7722dadfe38b9fc1fbb92e809ae8f80cbd2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778102"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="6efd3-103">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="6efd3-103">2577 - TryCatchExceptionDuringCancelation</span></span>

## <a name="properties"></a><span data-ttu-id="6efd3-104">속성</span><span class="sxs-lookup"><span data-stu-id="6efd3-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6efd3-105">ID</span><span class="sxs-lookup"><span data-stu-id="6efd3-105">ID</span></span>|<span data-ttu-id="6efd3-106">2577</span><span class="sxs-lookup"><span data-stu-id="6efd3-106">2577</span></span>|  
|<span data-ttu-id="6efd3-107">키워드</span><span class="sxs-lookup"><span data-stu-id="6efd3-107">Keywords</span></span>|<span data-ttu-id="6efd3-108">WFActivities</span><span class="sxs-lookup"><span data-stu-id="6efd3-108">WFActivities</span></span>|  
|<span data-ttu-id="6efd3-109">Level</span><span class="sxs-lookup"><span data-stu-id="6efd3-109">Level</span></span>|<span data-ttu-id="6efd3-110">경고</span><span class="sxs-lookup"><span data-stu-id="6efd3-110">Warning</span></span>|  
|<span data-ttu-id="6efd3-111">채널</span><span class="sxs-lookup"><span data-stu-id="6efd3-111">Channel</span></span>|<span data-ttu-id="6efd3-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="6efd3-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6efd3-113">설명</span><span class="sxs-lookup"><span data-stu-id="6efd3-113">Description</span></span>  

 <span data-ttu-id="6efd3-114">취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6efd3-114">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6efd3-115">메시지</span><span class="sxs-lookup"><span data-stu-id="6efd3-115">Message</span></span>  

 <span data-ttu-id="6efd3-116">취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6efd3-116">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6efd3-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="6efd3-117">Details</span></span>  
  
|<span data-ttu-id="6efd3-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="6efd3-118">Data Item Name</span></span>|<span data-ttu-id="6efd3-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="6efd3-119">Data Item Type</span></span>|<span data-ttu-id="6efd3-120">Description</span><span class="sxs-lookup"><span data-stu-id="6efd3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6efd3-121">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6efd3-121">DisplayName</span></span>|<span data-ttu-id="6efd3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6efd3-122">xs:string</span></span>|<span data-ttu-id="6efd3-123">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6efd3-123">The display name of the activity.</span></span>|  
|<span data-ttu-id="6efd3-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6efd3-124">AppDomain</span></span>|<span data-ttu-id="6efd3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6efd3-125">xs:string</span></span>|<span data-ttu-id="6efd3-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6efd3-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
