---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008813"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="04841-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="04841-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="04841-103">속성</span><span class="sxs-lookup"><span data-stu-id="04841-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04841-104">ID</span><span class="sxs-lookup"><span data-stu-id="04841-104">ID</span></span>|<span data-ttu-id="04841-105">1028</span><span class="sxs-lookup"><span data-stu-id="04841-105">1028</span></span>|  
|<span data-ttu-id="04841-106">키워드</span><span class="sxs-lookup"><span data-stu-id="04841-106">Keywords</span></span>|<span data-ttu-id="04841-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="04841-107">WFRuntime</span></span>|  
|<span data-ttu-id="04841-108">수준</span><span class="sxs-lookup"><span data-stu-id="04841-108">Level</span></span>|<span data-ttu-id="04841-109">자세히</span><span class="sxs-lookup"><span data-stu-id="04841-109">Verbose</span></span>|  
|<span data-ttu-id="04841-110">채널</span><span class="sxs-lookup"><span data-stu-id="04841-110">Channel</span></span>|<span data-ttu-id="04841-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="04841-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04841-112">설명</span><span class="sxs-lookup"><span data-stu-id="04841-112">Description</span></span>  
 <span data-ttu-id="04841-113">TransactionContextWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04841-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="04841-114">메시지</span><span class="sxs-lookup"><span data-stu-id="04841-114">Message</span></span>  
 <span data-ttu-id="04841-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="04841-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="04841-116">설명</span><span class="sxs-lookup"><span data-stu-id="04841-116">Details</span></span>  
  
|<span data-ttu-id="04841-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="04841-117">Data Item Name</span></span>|<span data-ttu-id="04841-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="04841-118">Data Item Type</span></span>|<span data-ttu-id="04841-119">설명</span><span class="sxs-lookup"><span data-stu-id="04841-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="04841-120">활동</span><span class="sxs-lookup"><span data-stu-id="04841-120">Activity</span></span>|<span data-ttu-id="04841-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="04841-121">xs:string</span></span>|<span data-ttu-id="04841-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04841-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="04841-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="04841-123">DisplayName</span></span>|<span data-ttu-id="04841-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="04841-124">xs:string</span></span>|<span data-ttu-id="04841-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04841-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="04841-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="04841-126">InstanceId</span></span>|<span data-ttu-id="04841-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="04841-127">xs:string</span></span>|<span data-ttu-id="04841-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04841-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="04841-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="04841-129">AppDomain</span></span>|<span data-ttu-id="04841-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="04841-130">xs:string</span></span>|<span data-ttu-id="04841-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="04841-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
