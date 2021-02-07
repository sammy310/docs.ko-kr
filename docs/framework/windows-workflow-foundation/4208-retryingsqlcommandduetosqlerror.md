---
description: '자세한 정보: 4208-RetryingSqlCommandDueToSqlError'
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 11ea2260f6a2ceffc1ffdbfce2cb3e3ce784076d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755306"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="5350c-103">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="5350c-103">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="5350c-104">속성</span><span class="sxs-lookup"><span data-stu-id="5350c-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5350c-105">ID</span><span class="sxs-lookup"><span data-stu-id="5350c-105">ID</span></span>|<span data-ttu-id="5350c-106">4208</span><span class="sxs-lookup"><span data-stu-id="5350c-106">4208</span></span>|  
|<span data-ttu-id="5350c-107">키워드</span><span class="sxs-lookup"><span data-stu-id="5350c-107">Keywords</span></span>|<span data-ttu-id="5350c-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5350c-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="5350c-109">Level</span><span class="sxs-lookup"><span data-stu-id="5350c-109">Level</span></span>|<span data-ttu-id="5350c-110">정보</span><span class="sxs-lookup"><span data-stu-id="5350c-110">Information</span></span>|  
|<span data-ttu-id="5350c-111">채널</span><span class="sxs-lookup"><span data-stu-id="5350c-111">Channel</span></span>|<span data-ttu-id="5350c-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="5350c-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5350c-113">설명</span><span class="sxs-lookup"><span data-stu-id="5350c-113">Description</span></span>  

 <span data-ttu-id="5350c-114">SQL 오류로 인해 SQL 공급자가 SQL 명령을 재시도하고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5350c-114">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5350c-115">메시지</span><span class="sxs-lookup"><span data-stu-id="5350c-115">Message</span></span>  

 <span data-ttu-id="5350c-116">SQL 오류 %1번으로 인해 SQL 명령을 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5350c-116">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5350c-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="5350c-117">Details</span></span>  
  
|<span data-ttu-id="5350c-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5350c-118">Data Item Name</span></span>|<span data-ttu-id="5350c-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5350c-119">Data Item Type</span></span>|<span data-ttu-id="5350c-120">설명</span><span class="sxs-lookup"><span data-stu-id="5350c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5350c-121">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="5350c-121">ErrorNumber</span></span>|<span data-ttu-id="5350c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5350c-122">xs:string</span></span>|<span data-ttu-id="5350c-123">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5350c-123">The SQL error number.</span></span>|  
|<span data-ttu-id="5350c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5350c-124">AppDomain</span></span>|<span data-ttu-id="5350c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5350c-125">xs:string</span></span>|<span data-ttu-id="5350c-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5350c-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
