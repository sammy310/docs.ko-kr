---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008865"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="b7c2e-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b7c2e-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b7c2e-103">속성</span><span class="sxs-lookup"><span data-stu-id="b7c2e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7c2e-104">ID</span><span class="sxs-lookup"><span data-stu-id="b7c2e-104">ID</span></span>|<span data-ttu-id="b7c2e-105">1018</span><span class="sxs-lookup"><span data-stu-id="b7c2e-105">1018</span></span>|  
|<span data-ttu-id="b7c2e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b7c2e-106">Keywords</span></span>|<span data-ttu-id="b7c2e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b7c2e-107">WFRuntime</span></span>|  
|<span data-ttu-id="b7c2e-108">수준</span><span class="sxs-lookup"><span data-stu-id="b7c2e-108">Level</span></span>|<span data-ttu-id="b7c2e-109">자세히</span><span class="sxs-lookup"><span data-stu-id="b7c2e-109">Verbose</span></span>|  
|<span data-ttu-id="b7c2e-110">채널</span><span class="sxs-lookup"><span data-stu-id="b7c2e-110">Channel</span></span>|<span data-ttu-id="b7c2e-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="b7c2e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b7c2e-112">설명</span><span class="sxs-lookup"><span data-stu-id="b7c2e-112">Description</span></span>  
 <span data-ttu-id="b7c2e-113">CancelActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7c2e-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b7c2e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b7c2e-114">Message</span></span>  
 <span data-ttu-id="b7c2e-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c2e-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b7c2e-116">설명</span><span class="sxs-lookup"><span data-stu-id="b7c2e-116">Details</span></span>  
  
|<span data-ttu-id="b7c2e-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b7c2e-117">Data Item Name</span></span>|<span data-ttu-id="b7c2e-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b7c2e-118">Data Item Type</span></span>|<span data-ttu-id="b7c2e-119">설명</span><span class="sxs-lookup"><span data-stu-id="b7c2e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b7c2e-120">활동</span><span class="sxs-lookup"><span data-stu-id="b7c2e-120">Activity</span></span>|<span data-ttu-id="b7c2e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7c2e-121">xs:string</span></span>|<span data-ttu-id="b7c2e-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c2e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b7c2e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b7c2e-123">DisplayName</span></span>|<span data-ttu-id="b7c2e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7c2e-124">xs:string</span></span>|<span data-ttu-id="b7c2e-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c2e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b7c2e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b7c2e-126">InstanceId</span></span>|<span data-ttu-id="b7c2e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7c2e-127">xs:string</span></span>|<span data-ttu-id="b7c2e-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c2e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b7c2e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b7c2e-129">AppDomain</span></span>|<span data-ttu-id="b7c2e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7c2e-130">xs:string</span></span>|<span data-ttu-id="b7c2e-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c2e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
