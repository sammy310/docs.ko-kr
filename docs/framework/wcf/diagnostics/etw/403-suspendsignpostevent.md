---
title: 403 - SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 727d164b9cd47657af0d7810103a766f33cb35de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758056"
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="5eb8f-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="5eb8f-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="5eb8f-103">속성</span><span class="sxs-lookup"><span data-stu-id="5eb8f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5eb8f-104">ID</span><span class="sxs-lookup"><span data-stu-id="5eb8f-104">ID</span></span>|<span data-ttu-id="5eb8f-105">403</span><span class="sxs-lookup"><span data-stu-id="5eb8f-105">403</span></span>|  
|<span data-ttu-id="5eb8f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5eb8f-106">Keywords</span></span>|<span data-ttu-id="5eb8f-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="5eb8f-107">Troubleshooting</span></span>|  
|<span data-ttu-id="5eb8f-108">수준</span><span class="sxs-lookup"><span data-stu-id="5eb8f-108">Level</span></span>|<span data-ttu-id="5eb8f-109">정보</span><span class="sxs-lookup"><span data-stu-id="5eb8f-109">Information</span></span>|  
|<span data-ttu-id="5eb8f-110">채널</span><span class="sxs-lookup"><span data-stu-id="5eb8f-110">Channel</span></span>|<span data-ttu-id="5eb8f-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="5eb8f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5eb8f-112">설명</span><span class="sxs-lookup"><span data-stu-id="5eb8f-112">Description</span></span>  
 <span data-ttu-id="5eb8f-113">이 이벤트는 엔드투엔드 동작의 일시 중단을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="5eb8f-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5eb8f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="5eb8f-115">Message</span></span>  
 <span data-ttu-id="5eb8f-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5eb8f-117">설명</span><span class="sxs-lookup"><span data-stu-id="5eb8f-117">Details</span></span>  
  
|<span data-ttu-id="5eb8f-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5eb8f-118">Data Item Name</span></span>|<span data-ttu-id="5eb8f-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5eb8f-119">Data Item Type</span></span>|<span data-ttu-id="5eb8f-120">설명</span><span class="sxs-lookup"><span data-stu-id="5eb8f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5eb8f-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="5eb8f-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="5eb8f-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-122">The name of the activity.</span></span>|  
|<span data-ttu-id="5eb8f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5eb8f-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5eb8f-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
