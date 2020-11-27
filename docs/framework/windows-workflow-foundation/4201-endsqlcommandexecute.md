---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 0d6326889077e36ad49aa6267ae7285849c6818d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275868"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="96d75-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="96d75-102">4201 - EndSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="96d75-103">속성</span><span class="sxs-lookup"><span data-stu-id="96d75-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96d75-104">ID</span><span class="sxs-lookup"><span data-stu-id="96d75-104">ID</span></span>|<span data-ttu-id="96d75-105">4201</span><span class="sxs-lookup"><span data-stu-id="96d75-105">4201</span></span>|  
|<span data-ttu-id="96d75-106">키워드</span><span class="sxs-lookup"><span data-stu-id="96d75-106">Keywords</span></span>|<span data-ttu-id="96d75-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="96d75-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="96d75-108">Level</span><span class="sxs-lookup"><span data-stu-id="96d75-108">Level</span></span>|<span data-ttu-id="96d75-109">자세히</span><span class="sxs-lookup"><span data-stu-id="96d75-109">Verbose</span></span>|  
|<span data-ttu-id="96d75-110">채널</span><span class="sxs-lookup"><span data-stu-id="96d75-110">Channel</span></span>|<span data-ttu-id="96d75-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="96d75-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="96d75-112">Description</span><span class="sxs-lookup"><span data-stu-id="96d75-112">Description</span></span>  

 <span data-ttu-id="96d75-113">SQL 명령이 실행을 완료했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96d75-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="96d75-114">메시지</span><span class="sxs-lookup"><span data-stu-id="96d75-114">Message</span></span>  

 <span data-ttu-id="96d75-115">SQL 명령 실행 종료: %1</span><span class="sxs-lookup"><span data-stu-id="96d75-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="96d75-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="96d75-116">Details</span></span>  
  
|<span data-ttu-id="96d75-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="96d75-117">Data Item Name</span></span>|<span data-ttu-id="96d75-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="96d75-118">Data Item Type</span></span>|<span data-ttu-id="96d75-119">Description</span><span class="sxs-lookup"><span data-stu-id="96d75-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="96d75-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="96d75-120">SqlCommand</span></span>|<span data-ttu-id="96d75-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="96d75-121">xs:string</span></span>|<span data-ttu-id="96d75-122">실행된 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="96d75-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="96d75-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="96d75-123">AppDomain</span></span>|<span data-ttu-id="96d75-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="96d75-124">xs:string</span></span>|<span data-ttu-id="96d75-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="96d75-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
