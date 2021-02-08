---
description: '자세한 정보: 3557-TransactedReceiveScopeEndCommitFailed'
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 7865ae27e7ce5b3f13b3567f3f8aeebd6edf3fd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777985"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="573aa-103">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="573aa-103">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="573aa-104">속성</span><span class="sxs-lookup"><span data-stu-id="573aa-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="573aa-105">ID</span><span class="sxs-lookup"><span data-stu-id="573aa-105">ID</span></span>|<span data-ttu-id="573aa-106">3557</span><span class="sxs-lookup"><span data-stu-id="573aa-106">3557</span></span>|  
|<span data-ttu-id="573aa-107">키워드</span><span class="sxs-lookup"><span data-stu-id="573aa-107">Keywords</span></span>|<span data-ttu-id="573aa-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="573aa-108">WFServices</span></span>|  
|<span data-ttu-id="573aa-109">Level</span><span class="sxs-lookup"><span data-stu-id="573aa-109">Level</span></span>|<span data-ttu-id="573aa-110">정보</span><span class="sxs-lookup"><span data-stu-id="573aa-110">Information</span></span>|  
|<span data-ttu-id="573aa-111">채널</span><span class="sxs-lookup"><span data-stu-id="573aa-111">Channel</span></span>|<span data-ttu-id="573aa-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="573aa-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="573aa-113">설명</span><span class="sxs-lookup"><span data-stu-id="573aa-113">Description</span></span>  

 <span data-ttu-id="573aa-114">CommittableTransaction에 대한 EndCommit 호출에서 TransactionException이 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="573aa-114">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="573aa-115">메시지</span><span class="sxs-lookup"><span data-stu-id="573aa-115">Message</span></span>  

 <span data-ttu-id="573aa-116">ID = '%1'인 CommittableTransaction에 대한 EndCommit 호출에서 다음 메시지와 함께 TransactionException이 발생했습니다. '%2'.</span><span class="sxs-lookup"><span data-stu-id="573aa-116">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="573aa-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="573aa-117">Details</span></span>  
  
|<span data-ttu-id="573aa-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="573aa-118">Data Item Name</span></span>|<span data-ttu-id="573aa-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="573aa-119">Data Item Type</span></span>|<span data-ttu-id="573aa-120">설명</span><span class="sxs-lookup"><span data-stu-id="573aa-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="573aa-121">TransactionId</span><span class="sxs-lookup"><span data-stu-id="573aa-121">TransactionId</span></span>|<span data-ttu-id="573aa-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="573aa-122">xs:string</span></span>|<span data-ttu-id="573aa-123">CommittableTransaction의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="573aa-123">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="573aa-124">예외</span><span class="sxs-lookup"><span data-stu-id="573aa-124">Exception</span></span>|<span data-ttu-id="573aa-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="573aa-125">xs:string</span></span>|<span data-ttu-id="573aa-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="573aa-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="573aa-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="573aa-127">AppDomain</span></span>|<span data-ttu-id="573aa-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="573aa-128">xs:string</span></span>|<span data-ttu-id="573aa-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="573aa-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
