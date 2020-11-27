---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 48182d7c5fe8f29842a17f28c0ea296f93b31089
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251258"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="5244b-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="5244b-102">4206 - UnlockInstanceException</span></span>

## <a name="properties"></a><span data-ttu-id="5244b-103">속성</span><span class="sxs-lookup"><span data-stu-id="5244b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5244b-104">ID</span><span class="sxs-lookup"><span data-stu-id="5244b-104">ID</span></span>|<span data-ttu-id="5244b-105">4206</span><span class="sxs-lookup"><span data-stu-id="5244b-105">4206</span></span>|  
|<span data-ttu-id="5244b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5244b-106">Keywords</span></span>|<span data-ttu-id="5244b-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5244b-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5244b-108">Level</span><span class="sxs-lookup"><span data-stu-id="5244b-108">Level</span></span>|<span data-ttu-id="5244b-109">오류</span><span class="sxs-lookup"><span data-stu-id="5244b-109">Error</span></span>|  
|<span data-ttu-id="5244b-110">채널</span><span class="sxs-lookup"><span data-stu-id="5244b-110">Channel</span></span>|<span data-ttu-id="5244b-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="5244b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5244b-112">Description</span><span class="sxs-lookup"><span data-stu-id="5244b-112">Description</span></span>  

 <span data-ttu-id="5244b-113">인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5244b-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5244b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5244b-114">Message</span></span>  

 <span data-ttu-id="5244b-115">인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5244b-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5244b-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="5244b-116">Details</span></span>  
  
|<span data-ttu-id="5244b-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5244b-117">Data Item Name</span></span>|<span data-ttu-id="5244b-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5244b-118">Data Item Type</span></span>|<span data-ttu-id="5244b-119">Description</span><span class="sxs-lookup"><span data-stu-id="5244b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5244b-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="5244b-120">ExceptionMessage</span></span>|<span data-ttu-id="5244b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5244b-121">xs:string</span></span>|<span data-ttu-id="5244b-122">SQL 예외로부터의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="5244b-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="5244b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5244b-123">AppDomain</span></span>|<span data-ttu-id="5244b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5244b-124">xs:string</span></span>|<span data-ttu-id="5244b-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5244b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
