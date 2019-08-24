---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774454"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="7ca0c-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="7ca0c-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="7ca0c-103">속성</span><span class="sxs-lookup"><span data-stu-id="7ca0c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ca0c-104">ID</span><span class="sxs-lookup"><span data-stu-id="7ca0c-104">ID</span></span>|<span data-ttu-id="7ca0c-105">3557</span><span class="sxs-lookup"><span data-stu-id="7ca0c-105">3557</span></span>|  
|<span data-ttu-id="7ca0c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7ca0c-106">Keywords</span></span>|<span data-ttu-id="7ca0c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="7ca0c-107">WFServices</span></span>|  
|<span data-ttu-id="7ca0c-108">수준</span><span class="sxs-lookup"><span data-stu-id="7ca0c-108">Level</span></span>|<span data-ttu-id="7ca0c-109">정보</span><span class="sxs-lookup"><span data-stu-id="7ca0c-109">Information</span></span>|  
|<span data-ttu-id="7ca0c-110">채널</span><span class="sxs-lookup"><span data-stu-id="7ca0c-110">Channel</span></span>|<span data-ttu-id="7ca0c-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="7ca0c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7ca0c-112">설명</span><span class="sxs-lookup"><span data-stu-id="7ca0c-112">Description</span></span>  
 <span data-ttu-id="7ca0c-113">CommittableTransaction에 대한 EndCommit 호출에서 TransactionException이 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ca0c-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7ca0c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="7ca0c-114">Message</span></span>  
 <span data-ttu-id="7ca0c-115">ID = '%1'인 CommittableTransaction에 대한 EndCommit 호출에서 다음 메시지와 함께 TransactionException이 발생했습니다. '%2'.</span><span class="sxs-lookup"><span data-stu-id="7ca0c-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7ca0c-116">설명</span><span class="sxs-lookup"><span data-stu-id="7ca0c-116">Details</span></span>  
  
|<span data-ttu-id="7ca0c-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7ca0c-117">Data Item Name</span></span>|<span data-ttu-id="7ca0c-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7ca0c-118">Data Item Type</span></span>|<span data-ttu-id="7ca0c-119">설명</span><span class="sxs-lookup"><span data-stu-id="7ca0c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7ca0c-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="7ca0c-120">TransactionId</span></span>|<span data-ttu-id="7ca0c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ca0c-121">xs:string</span></span>|<span data-ttu-id="7ca0c-122">CommittableTransaction의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca0c-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="7ca0c-123">예외</span><span class="sxs-lookup"><span data-stu-id="7ca0c-123">Exception</span></span>|<span data-ttu-id="7ca0c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ca0c-124">xs:string</span></span>|<span data-ttu-id="7ca0c-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="7ca0c-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="7ca0c-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7ca0c-126">AppDomain</span></span>|<span data-ttu-id="7ca0c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ca0c-127">xs:string</span></span>|<span data-ttu-id="7ca0c-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca0c-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
