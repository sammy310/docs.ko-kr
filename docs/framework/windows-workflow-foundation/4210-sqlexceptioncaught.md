---
description: '자세한 정보: 4210-SqlExceptionCaught'
title: 4210 - SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 58846d02b6d1e388e3aef2bff76f51cba4990f2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777881"
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="3888b-103">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="3888b-103">4210 - SqlExceptionCaught</span></span>

## <a name="properties"></a><span data-ttu-id="3888b-104">속성</span><span class="sxs-lookup"><span data-stu-id="3888b-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3888b-105">ID</span><span class="sxs-lookup"><span data-stu-id="3888b-105">ID</span></span>|<span data-ttu-id="3888b-106">4210</span><span class="sxs-lookup"><span data-stu-id="3888b-106">4210</span></span>|  
|<span data-ttu-id="3888b-107">키워드</span><span class="sxs-lookup"><span data-stu-id="3888b-107">Keywords</span></span>|<span data-ttu-id="3888b-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3888b-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="3888b-109">Level</span><span class="sxs-lookup"><span data-stu-id="3888b-109">Level</span></span>|<span data-ttu-id="3888b-110">경고</span><span class="sxs-lookup"><span data-stu-id="3888b-110">Warning</span></span>|  
|<span data-ttu-id="3888b-111">채널</span><span class="sxs-lookup"><span data-stu-id="3888b-111">Channel</span></span>|<span data-ttu-id="3888b-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3888b-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3888b-113">설명</span><span class="sxs-lookup"><span data-stu-id="3888b-113">Description</span></span>  

 <span data-ttu-id="3888b-114">SQL 예외가 catch되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3888b-114">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3888b-115">메시지</span><span class="sxs-lookup"><span data-stu-id="3888b-115">Message</span></span>  

 <span data-ttu-id="3888b-116">SQL 예외 %1번 메시지 %2을(를) catch했습니다.</span><span class="sxs-lookup"><span data-stu-id="3888b-116">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3888b-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3888b-117">Details</span></span>  
  
|<span data-ttu-id="3888b-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3888b-118">Data Item Name</span></span>|<span data-ttu-id="3888b-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3888b-119">Data Item Type</span></span>|<span data-ttu-id="3888b-120">설명</span><span class="sxs-lookup"><span data-stu-id="3888b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3888b-121">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="3888b-121">ErrorNumber</span></span>|<span data-ttu-id="3888b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3888b-122">xs:string</span></span>|<span data-ttu-id="3888b-123">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3888b-123">The SQL error number.</span></span>|  
|<span data-ttu-id="3888b-124">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="3888b-124">ExceptionMessage</span></span>|<span data-ttu-id="3888b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3888b-125">xs:string</span></span>|<span data-ttu-id="3888b-126">SQL 예외로부터의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="3888b-126">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="3888b-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3888b-127">AppDomain</span></span>|<span data-ttu-id="3888b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3888b-128">xs:string</span></span>|<span data-ttu-id="3888b-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3888b-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
