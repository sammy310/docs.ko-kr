---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 61605d666911cce277bcebbb0a2f803e9a5dcfeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261308"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="141c2-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="141c2-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="141c2-103">속성</span><span class="sxs-lookup"><span data-stu-id="141c2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="141c2-104">ID</span><span class="sxs-lookup"><span data-stu-id="141c2-104">ID</span></span>|<span data-ttu-id="141c2-105">3550</span><span class="sxs-lookup"><span data-stu-id="141c2-105">3550</span></span>|  
|<span data-ttu-id="141c2-106">키워드</span><span class="sxs-lookup"><span data-stu-id="141c2-106">Keywords</span></span>|<span data-ttu-id="141c2-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="141c2-107">WFServices</span></span>|  
|<span data-ttu-id="141c2-108">Level</span><span class="sxs-lookup"><span data-stu-id="141c2-108">Level</span></span>|<span data-ttu-id="141c2-109">정보</span><span class="sxs-lookup"><span data-stu-id="141c2-109">Information</span></span>|  
|<span data-ttu-id="141c2-110">채널</span><span class="sxs-lookup"><span data-stu-id="141c2-110">Channel</span></span>|<span data-ttu-id="141c2-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="141c2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="141c2-112">Description</span><span class="sxs-lookup"><span data-stu-id="141c2-112">Description</span></span>  

 <span data-ttu-id="141c2-113">버퍼링된 수신이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="141c2-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="141c2-114">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="141c2-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="141c2-115">메시지</span><span class="sxs-lookup"><span data-stu-id="141c2-115">Message</span></span>  

 <span data-ttu-id="141c2-116">현재는 '%1' 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="141c2-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="141c2-117">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="141c2-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="141c2-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="141c2-118">Details</span></span>  
  
|<span data-ttu-id="141c2-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="141c2-119">Data Item Name</span></span>|<span data-ttu-id="141c2-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="141c2-120">Data Item Type</span></span>|<span data-ttu-id="141c2-121">Description</span><span class="sxs-lookup"><span data-stu-id="141c2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="141c2-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="141c2-122">OperationName</span></span>|<span data-ttu-id="141c2-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="141c2-123">xs:string</span></span>|<span data-ttu-id="141c2-124">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="141c2-124">The name of the operation.</span></span>|  
|<span data-ttu-id="141c2-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="141c2-125">AppDomain</span></span>|<span data-ttu-id="141c2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="141c2-126">xs:string</span></span>|<span data-ttu-id="141c2-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="141c2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
