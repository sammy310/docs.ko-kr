---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263661"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="e5bd1-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="e5bd1-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="e5bd1-103">속성</span><span class="sxs-lookup"><span data-stu-id="e5bd1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5bd1-104">ID</span><span class="sxs-lookup"><span data-stu-id="e5bd1-104">ID</span></span>|<span data-ttu-id="e5bd1-105">3557</span><span class="sxs-lookup"><span data-stu-id="e5bd1-105">3557</span></span>|  
|<span data-ttu-id="e5bd1-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e5bd1-106">Keywords</span></span>|<span data-ttu-id="e5bd1-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e5bd1-107">WFServices</span></span>|  
|<span data-ttu-id="e5bd1-108">Level</span><span class="sxs-lookup"><span data-stu-id="e5bd1-108">Level</span></span>|<span data-ttu-id="e5bd1-109">정보</span><span class="sxs-lookup"><span data-stu-id="e5bd1-109">Information</span></span>|  
|<span data-ttu-id="e5bd1-110">채널</span><span class="sxs-lookup"><span data-stu-id="e5bd1-110">Channel</span></span>|<span data-ttu-id="e5bd1-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="e5bd1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e5bd1-112">Description</span><span class="sxs-lookup"><span data-stu-id="e5bd1-112">Description</span></span>  

 <span data-ttu-id="e5bd1-113">CommittableTransaction에 대한 EndCommit 호출에서 TransactionException이 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5bd1-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e5bd1-114">메시지</span><span class="sxs-lookup"><span data-stu-id="e5bd1-114">Message</span></span>  

 <span data-ttu-id="e5bd1-115">ID = '%1'인 CommittableTransaction에 대한 EndCommit 호출에서 다음 메시지와 함께 TransactionException이 발생했습니다. '%2'.</span><span class="sxs-lookup"><span data-stu-id="e5bd1-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e5bd1-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e5bd1-116">Details</span></span>  
  
|<span data-ttu-id="e5bd1-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e5bd1-117">Data Item Name</span></span>|<span data-ttu-id="e5bd1-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e5bd1-118">Data Item Type</span></span>|<span data-ttu-id="e5bd1-119">Description</span><span class="sxs-lookup"><span data-stu-id="e5bd1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e5bd1-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="e5bd1-120">TransactionId</span></span>|<span data-ttu-id="e5bd1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e5bd1-121">xs:string</span></span>|<span data-ttu-id="e5bd1-122">CommittableTransaction의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e5bd1-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="e5bd1-123">예외</span><span class="sxs-lookup"><span data-stu-id="e5bd1-123">Exception</span></span>|<span data-ttu-id="e5bd1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e5bd1-124">xs:string</span></span>|<span data-ttu-id="e5bd1-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="e5bd1-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="e5bd1-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e5bd1-126">AppDomain</span></span>|<span data-ttu-id="e5bd1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e5bd1-127">xs:string</span></span>|<span data-ttu-id="e5bd1-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e5bd1-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
