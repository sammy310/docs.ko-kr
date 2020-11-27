---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271241"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="81991-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="81991-102">2577 - TryCatchExceptionDuringCancelation</span></span>

## <a name="properties"></a><span data-ttu-id="81991-103">속성</span><span class="sxs-lookup"><span data-stu-id="81991-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81991-104">ID</span><span class="sxs-lookup"><span data-stu-id="81991-104">ID</span></span>|<span data-ttu-id="81991-105">2577</span><span class="sxs-lookup"><span data-stu-id="81991-105">2577</span></span>|  
|<span data-ttu-id="81991-106">키워드</span><span class="sxs-lookup"><span data-stu-id="81991-106">Keywords</span></span>|<span data-ttu-id="81991-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="81991-107">WFActivities</span></span>|  
|<span data-ttu-id="81991-108">Level</span><span class="sxs-lookup"><span data-stu-id="81991-108">Level</span></span>|<span data-ttu-id="81991-109">경고</span><span class="sxs-lookup"><span data-stu-id="81991-109">Warning</span></span>|  
|<span data-ttu-id="81991-110">채널</span><span class="sxs-lookup"><span data-stu-id="81991-110">Channel</span></span>|<span data-ttu-id="81991-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="81991-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="81991-112">Description</span><span class="sxs-lookup"><span data-stu-id="81991-112">Description</span></span>  

 <span data-ttu-id="81991-113">취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81991-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="81991-114">메시지</span><span class="sxs-lookup"><span data-stu-id="81991-114">Message</span></span>  

 <span data-ttu-id="81991-115">취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81991-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="81991-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="81991-116">Details</span></span>  
  
|<span data-ttu-id="81991-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="81991-117">Data Item Name</span></span>|<span data-ttu-id="81991-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="81991-118">Data Item Type</span></span>|<span data-ttu-id="81991-119">Description</span><span class="sxs-lookup"><span data-stu-id="81991-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="81991-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="81991-120">DisplayName</span></span>|<span data-ttu-id="81991-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="81991-121">xs:string</span></span>|<span data-ttu-id="81991-122">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81991-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="81991-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="81991-123">AppDomain</span></span>|<span data-ttu-id="81991-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="81991-124">xs:string</span></span>|<span data-ttu-id="81991-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="81991-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
