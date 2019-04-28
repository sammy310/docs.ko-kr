---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774298"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="e4f11-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="e4f11-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="e4f11-103">속성</span><span class="sxs-lookup"><span data-stu-id="e4f11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4f11-104">ID</span><span class="sxs-lookup"><span data-stu-id="e4f11-104">ID</span></span>|<span data-ttu-id="e4f11-105">4208</span><span class="sxs-lookup"><span data-stu-id="e4f11-105">4208</span></span>|  
|<span data-ttu-id="e4f11-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e4f11-106">Keywords</span></span>|<span data-ttu-id="e4f11-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e4f11-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e4f11-108">수준</span><span class="sxs-lookup"><span data-stu-id="e4f11-108">Level</span></span>|<span data-ttu-id="e4f11-109">정보</span><span class="sxs-lookup"><span data-stu-id="e4f11-109">Information</span></span>|  
|<span data-ttu-id="e4f11-110">채널</span><span class="sxs-lookup"><span data-stu-id="e4f11-110">Channel</span></span>|<span data-ttu-id="e4f11-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="e4f11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e4f11-112">설명</span><span class="sxs-lookup"><span data-stu-id="e4f11-112">Description</span></span>  
 <span data-ttu-id="e4f11-113">SQL 오류로 인해 SQL 공급자가 SQL 명령을 재시도하고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4f11-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e4f11-114">메시지</span><span class="sxs-lookup"><span data-stu-id="e4f11-114">Message</span></span>  
 <span data-ttu-id="e4f11-115">SQL 오류 %1번으로 인해 SQL 명령을 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f11-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e4f11-116">설명</span><span class="sxs-lookup"><span data-stu-id="e4f11-116">Details</span></span>  
  
|<span data-ttu-id="e4f11-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e4f11-117">Data Item Name</span></span>|<span data-ttu-id="e4f11-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e4f11-118">Data Item Type</span></span>|<span data-ttu-id="e4f11-119">설명</span><span class="sxs-lookup"><span data-stu-id="e4f11-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e4f11-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="e4f11-120">ErrorNumber</span></span>|<span data-ttu-id="e4f11-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4f11-121">xs:string</span></span>|<span data-ttu-id="e4f11-122">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f11-122">The SQL error number.</span></span>|  
|<span data-ttu-id="e4f11-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e4f11-123">AppDomain</span></span>|<span data-ttu-id="e4f11-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4f11-124">xs:string</span></span>|<span data-ttu-id="e4f11-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f11-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
