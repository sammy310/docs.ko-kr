---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755586"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="4cdd8-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="4cdd8-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="4cdd8-103">속성</span><span class="sxs-lookup"><span data-stu-id="4cdd8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cdd8-104">ID</span><span class="sxs-lookup"><span data-stu-id="4cdd8-104">ID</span></span>|<span data-ttu-id="4cdd8-105">3550</span><span class="sxs-lookup"><span data-stu-id="4cdd8-105">3550</span></span>|  
|<span data-ttu-id="4cdd8-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4cdd8-106">Keywords</span></span>|<span data-ttu-id="4cdd8-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4cdd8-107">WFServices</span></span>|  
|<span data-ttu-id="4cdd8-108">수준</span><span class="sxs-lookup"><span data-stu-id="4cdd8-108">Level</span></span>|<span data-ttu-id="4cdd8-109">정보</span><span class="sxs-lookup"><span data-stu-id="4cdd8-109">Information</span></span>|  
|<span data-ttu-id="4cdd8-110">채널</span><span class="sxs-lookup"><span data-stu-id="4cdd8-110">Channel</span></span>|<span data-ttu-id="4cdd8-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="4cdd8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4cdd8-112">설명</span><span class="sxs-lookup"><span data-stu-id="4cdd8-112">Description</span></span>  
 <span data-ttu-id="4cdd8-113">버퍼링된 수신이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="4cdd8-114">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4cdd8-115">메시지</span><span class="sxs-lookup"><span data-stu-id="4cdd8-115">Message</span></span>  
 <span data-ttu-id="4cdd8-116">현재는 '%1' 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="4cdd8-117">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4cdd8-118">설명</span><span class="sxs-lookup"><span data-stu-id="4cdd8-118">Details</span></span>  
  
|<span data-ttu-id="4cdd8-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4cdd8-119">Data Item Name</span></span>|<span data-ttu-id="4cdd8-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4cdd8-120">Data Item Type</span></span>|<span data-ttu-id="4cdd8-121">설명</span><span class="sxs-lookup"><span data-stu-id="4cdd8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4cdd8-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="4cdd8-122">OperationName</span></span>|<span data-ttu-id="4cdd8-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cdd8-123">xs:string</span></span>|<span data-ttu-id="4cdd8-124">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-124">The name of the operation.</span></span>|  
|<span data-ttu-id="4cdd8-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4cdd8-125">AppDomain</span></span>|<span data-ttu-id="4cdd8-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cdd8-126">xs:string</span></span>|<span data-ttu-id="4cdd8-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
