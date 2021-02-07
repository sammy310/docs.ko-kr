---
description: '자세한 정보: 4201-EndSqlCommandExecute'
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: e0b98e8da5a0a284bfa55e97f5dde25a2ce42b42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755371"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="35c31-103">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="35c31-103">4201 - EndSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="35c31-104">속성</span><span class="sxs-lookup"><span data-stu-id="35c31-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35c31-105">ID</span><span class="sxs-lookup"><span data-stu-id="35c31-105">ID</span></span>|<span data-ttu-id="35c31-106">4201</span><span class="sxs-lookup"><span data-stu-id="35c31-106">4201</span></span>|  
|<span data-ttu-id="35c31-107">키워드</span><span class="sxs-lookup"><span data-stu-id="35c31-107">Keywords</span></span>|<span data-ttu-id="35c31-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="35c31-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="35c31-109">Level</span><span class="sxs-lookup"><span data-stu-id="35c31-109">Level</span></span>|<span data-ttu-id="35c31-110">자세히</span><span class="sxs-lookup"><span data-stu-id="35c31-110">Verbose</span></span>|  
|<span data-ttu-id="35c31-111">채널</span><span class="sxs-lookup"><span data-stu-id="35c31-111">Channel</span></span>|<span data-ttu-id="35c31-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="35c31-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35c31-113">설명</span><span class="sxs-lookup"><span data-stu-id="35c31-113">Description</span></span>  

 <span data-ttu-id="35c31-114">SQL 명령이 실행을 완료했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="35c31-114">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35c31-115">메시지</span><span class="sxs-lookup"><span data-stu-id="35c31-115">Message</span></span>  

 <span data-ttu-id="35c31-116">SQL 명령 실행 종료: %1</span><span class="sxs-lookup"><span data-stu-id="35c31-116">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="35c31-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="35c31-117">Details</span></span>  
  
|<span data-ttu-id="35c31-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="35c31-118">Data Item Name</span></span>|<span data-ttu-id="35c31-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="35c31-119">Data Item Type</span></span>|<span data-ttu-id="35c31-120">설명</span><span class="sxs-lookup"><span data-stu-id="35c31-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35c31-121">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="35c31-121">SqlCommand</span></span>|<span data-ttu-id="35c31-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="35c31-122">xs:string</span></span>|<span data-ttu-id="35c31-123">실행된 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="35c31-123">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="35c31-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35c31-124">AppDomain</span></span>|<span data-ttu-id="35c31-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="35c31-125">xs:string</span></span>|<span data-ttu-id="35c31-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="35c31-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
