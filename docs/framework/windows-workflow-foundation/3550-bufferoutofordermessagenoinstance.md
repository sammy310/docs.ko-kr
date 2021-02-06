---
description: '자세한 정보: 3550-BufferOutOfOrderMessageNoInstance'
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: cb51f9fa32de1b56560f9593dae2ec82c100dc65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631452"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="92c4b-103">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="92c4b-103">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="92c4b-104">속성</span><span class="sxs-lookup"><span data-stu-id="92c4b-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92c4b-105">ID</span><span class="sxs-lookup"><span data-stu-id="92c4b-105">ID</span></span>|<span data-ttu-id="92c4b-106">3550</span><span class="sxs-lookup"><span data-stu-id="92c4b-106">3550</span></span>|  
|<span data-ttu-id="92c4b-107">키워드</span><span class="sxs-lookup"><span data-stu-id="92c4b-107">Keywords</span></span>|<span data-ttu-id="92c4b-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="92c4b-108">WFServices</span></span>|  
|<span data-ttu-id="92c4b-109">Level</span><span class="sxs-lookup"><span data-stu-id="92c4b-109">Level</span></span>|<span data-ttu-id="92c4b-110">정보</span><span class="sxs-lookup"><span data-stu-id="92c4b-110">Information</span></span>|  
|<span data-ttu-id="92c4b-111">채널</span><span class="sxs-lookup"><span data-stu-id="92c4b-111">Channel</span></span>|<span data-ttu-id="92c4b-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="92c4b-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="92c4b-113">설명</span><span class="sxs-lookup"><span data-stu-id="92c4b-113">Description</span></span>  

 <span data-ttu-id="92c4b-114">버퍼링된 수신이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92c4b-114">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="92c4b-115">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c4b-115">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="92c4b-116">메시지</span><span class="sxs-lookup"><span data-stu-id="92c4b-116">Message</span></span>  

 <span data-ttu-id="92c4b-117">현재는 '%1' 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92c4b-117">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="92c4b-118">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c4b-118">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="92c4b-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="92c4b-119">Details</span></span>  
  
|<span data-ttu-id="92c4b-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="92c4b-120">Data Item Name</span></span>|<span data-ttu-id="92c4b-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="92c4b-121">Data Item Type</span></span>|<span data-ttu-id="92c4b-122">설명</span><span class="sxs-lookup"><span data-stu-id="92c4b-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="92c4b-123">OperationName</span><span class="sxs-lookup"><span data-stu-id="92c4b-123">OperationName</span></span>|<span data-ttu-id="92c4b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="92c4b-124">xs:string</span></span>|<span data-ttu-id="92c4b-125">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="92c4b-125">The name of the operation.</span></span>|  
|<span data-ttu-id="92c4b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="92c4b-126">AppDomain</span></span>|<span data-ttu-id="92c4b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="92c4b-127">xs:string</span></span>|<span data-ttu-id="92c4b-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="92c4b-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
