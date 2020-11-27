---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280418"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="3ffb3-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="3ffb3-102">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="3ffb3-103">속성</span><span class="sxs-lookup"><span data-stu-id="3ffb3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ffb3-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ffb3-104">ID</span></span>|<span data-ttu-id="3ffb3-105">4208</span><span class="sxs-lookup"><span data-stu-id="3ffb3-105">4208</span></span>|  
|<span data-ttu-id="3ffb3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3ffb3-106">Keywords</span></span>|<span data-ttu-id="3ffb3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3ffb3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3ffb3-108">Level</span><span class="sxs-lookup"><span data-stu-id="3ffb3-108">Level</span></span>|<span data-ttu-id="3ffb3-109">정보</span><span class="sxs-lookup"><span data-stu-id="3ffb3-109">Information</span></span>|  
|<span data-ttu-id="3ffb3-110">채널</span><span class="sxs-lookup"><span data-stu-id="3ffb3-110">Channel</span></span>|<span data-ttu-id="3ffb3-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3ffb3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ffb3-112">Description</span><span class="sxs-lookup"><span data-stu-id="3ffb3-112">Description</span></span>  

 <span data-ttu-id="3ffb3-113">SQL 오류로 인해 SQL 공급자가 SQL 명령을 재시도하고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ffb3-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ffb3-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3ffb3-114">Message</span></span>  

 <span data-ttu-id="3ffb3-115">SQL 오류 %1번으로 인해 SQL 명령을 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3ffb3-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ffb3-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3ffb3-116">Details</span></span>  
  
|<span data-ttu-id="3ffb3-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3ffb3-117">Data Item Name</span></span>|<span data-ttu-id="3ffb3-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3ffb3-118">Data Item Type</span></span>|<span data-ttu-id="3ffb3-119">Description</span><span class="sxs-lookup"><span data-stu-id="3ffb3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ffb3-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="3ffb3-120">ErrorNumber</span></span>|<span data-ttu-id="3ffb3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ffb3-121">xs:string</span></span>|<span data-ttu-id="3ffb3-122">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffb3-122">The SQL error number.</span></span>|  
|<span data-ttu-id="3ffb3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ffb3-123">AppDomain</span></span>|<span data-ttu-id="3ffb3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ffb3-124">xs:string</span></span>|<span data-ttu-id="3ffb3-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffb3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
