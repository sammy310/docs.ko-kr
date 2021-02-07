---
description: '자세한 정보: 4206-UnlockInstanceException'
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 7c281b7471869fc2361b1c7fb158559e4c9fae65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676276"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="32028-103">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="32028-103">4206 - UnlockInstanceException</span></span>

## <a name="properties"></a><span data-ttu-id="32028-104">속성</span><span class="sxs-lookup"><span data-stu-id="32028-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32028-105">ID</span><span class="sxs-lookup"><span data-stu-id="32028-105">ID</span></span>|<span data-ttu-id="32028-106">4206</span><span class="sxs-lookup"><span data-stu-id="32028-106">4206</span></span>|  
|<span data-ttu-id="32028-107">키워드</span><span class="sxs-lookup"><span data-stu-id="32028-107">Keywords</span></span>|<span data-ttu-id="32028-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="32028-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="32028-109">Level</span><span class="sxs-lookup"><span data-stu-id="32028-109">Level</span></span>|<span data-ttu-id="32028-110">Error</span><span class="sxs-lookup"><span data-stu-id="32028-110">Error</span></span>|  
|<span data-ttu-id="32028-111">채널</span><span class="sxs-lookup"><span data-stu-id="32028-111">Channel</span></span>|<span data-ttu-id="32028-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="32028-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32028-113">설명</span><span class="sxs-lookup"><span data-stu-id="32028-113">Description</span></span>  

 <span data-ttu-id="32028-114">인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32028-114">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32028-115">메시지</span><span class="sxs-lookup"><span data-stu-id="32028-115">Message</span></span>  

 <span data-ttu-id="32028-116">인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="32028-116">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="32028-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="32028-117">Details</span></span>  
  
|<span data-ttu-id="32028-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="32028-118">Data Item Name</span></span>|<span data-ttu-id="32028-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="32028-119">Data Item Type</span></span>|<span data-ttu-id="32028-120">설명</span><span class="sxs-lookup"><span data-stu-id="32028-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32028-121">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="32028-121">ExceptionMessage</span></span>|<span data-ttu-id="32028-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="32028-122">xs:string</span></span>|<span data-ttu-id="32028-123">SQL 예외로부터의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="32028-123">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="32028-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="32028-124">AppDomain</span></span>|<span data-ttu-id="32028-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="32028-125">xs:string</span></span>|<span data-ttu-id="32028-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="32028-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
