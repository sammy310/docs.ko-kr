---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924243"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="9daa1-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="9daa1-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9daa1-103">속성</span><span class="sxs-lookup"><span data-stu-id="9daa1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9daa1-104">ID</span><span class="sxs-lookup"><span data-stu-id="9daa1-104">ID</span></span>|<span data-ttu-id="9daa1-105">1033</span><span class="sxs-lookup"><span data-stu-id="9daa1-105">1033</span></span>|  
|<span data-ttu-id="9daa1-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9daa1-106">Keywords</span></span>|<span data-ttu-id="9daa1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9daa1-107">WFRuntime</span></span>|  
|<span data-ttu-id="9daa1-108">수준</span><span class="sxs-lookup"><span data-stu-id="9daa1-108">Level</span></span>|<span data-ttu-id="9daa1-109">자세히</span><span class="sxs-lookup"><span data-stu-id="9daa1-109">Verbose</span></span>|  
|<span data-ttu-id="9daa1-110">채널</span><span class="sxs-lookup"><span data-stu-id="9daa1-110">Channel</span></span>|<span data-ttu-id="9daa1-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="9daa1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9daa1-112">설명</span><span class="sxs-lookup"><span data-stu-id="9daa1-112">Description</span></span>  
 <span data-ttu-id="9daa1-113">RuntimeWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9daa1-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9daa1-114">메시지</span><span class="sxs-lookup"><span data-stu-id="9daa1-114">Message</span></span>  
 <span data-ttu-id="9daa1-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9daa1-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9daa1-116">설명</span><span class="sxs-lookup"><span data-stu-id="9daa1-116">Details</span></span>  
  
|<span data-ttu-id="9daa1-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9daa1-117">Data Item Name</span></span>|<span data-ttu-id="9daa1-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9daa1-118">Data Item Type</span></span>|<span data-ttu-id="9daa1-119">설명</span><span class="sxs-lookup"><span data-stu-id="9daa1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9daa1-120">활동</span><span class="sxs-lookup"><span data-stu-id="9daa1-120">Activity</span></span>|<span data-ttu-id="9daa1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa1-121">xs:string</span></span>|<span data-ttu-id="9daa1-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9daa1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9daa1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9daa1-123">DisplayName</span></span>|<span data-ttu-id="9daa1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa1-124">xs:string</span></span>|<span data-ttu-id="9daa1-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9daa1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9daa1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9daa1-126">InstanceId</span></span>|<span data-ttu-id="9daa1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa1-127">xs:string</span></span>|<span data-ttu-id="9daa1-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9daa1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9daa1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9daa1-129">AppDomain</span></span>|<span data-ttu-id="9daa1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa1-130">xs:string</span></span>|<span data-ttu-id="9daa1-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9daa1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
