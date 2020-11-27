---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: d3f27c6ed28efe9d099dcedfc676b839ae9b1dee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275842"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="c166d-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="c166d-102">4202 - StartSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="c166d-103">속성</span><span class="sxs-lookup"><span data-stu-id="c166d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c166d-104">ID</span><span class="sxs-lookup"><span data-stu-id="c166d-104">ID</span></span>|<span data-ttu-id="c166d-105">4202</span><span class="sxs-lookup"><span data-stu-id="c166d-105">4202</span></span>|  
|<span data-ttu-id="c166d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c166d-106">Keywords</span></span>|<span data-ttu-id="c166d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c166d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c166d-108">Level</span><span class="sxs-lookup"><span data-stu-id="c166d-108">Level</span></span>|<span data-ttu-id="c166d-109">자세히</span><span class="sxs-lookup"><span data-stu-id="c166d-109">Verbose</span></span>|  
|<span data-ttu-id="c166d-110">채널</span><span class="sxs-lookup"><span data-stu-id="c166d-110">Channel</span></span>|<span data-ttu-id="c166d-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="c166d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c166d-112">Description</span><span class="sxs-lookup"><span data-stu-id="c166d-112">Description</span></span>  

 <span data-ttu-id="c166d-113">SQL 명령이 실행되고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c166d-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c166d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c166d-114">Message</span></span>  

 <span data-ttu-id="c166d-115">SQL 명령 실행 시작: %1</span><span class="sxs-lookup"><span data-stu-id="c166d-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="c166d-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c166d-116">Details</span></span>  
  
|<span data-ttu-id="c166d-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c166d-117">Data Item Name</span></span>|<span data-ttu-id="c166d-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c166d-118">Data Item Type</span></span>|<span data-ttu-id="c166d-119">Description</span><span class="sxs-lookup"><span data-stu-id="c166d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c166d-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="c166d-120">SqlCommand</span></span>|<span data-ttu-id="c166d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c166d-121">xs:string</span></span>|<span data-ttu-id="c166d-122">실행된 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c166d-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="c166d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c166d-123">AppDomain</span></span>|<span data-ttu-id="c166d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c166d-124">xs:string</span></span>|<span data-ttu-id="c166d-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c166d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
