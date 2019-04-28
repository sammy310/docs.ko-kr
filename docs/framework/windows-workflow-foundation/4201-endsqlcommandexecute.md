---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 75c1cdd10aca6b177911bd9d2f51468016eb9e15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774363"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="aa84a-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="aa84a-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="aa84a-103">속성</span><span class="sxs-lookup"><span data-stu-id="aa84a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa84a-104">ID</span><span class="sxs-lookup"><span data-stu-id="aa84a-104">ID</span></span>|<span data-ttu-id="aa84a-105">4201</span><span class="sxs-lookup"><span data-stu-id="aa84a-105">4201</span></span>|  
|<span data-ttu-id="aa84a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="aa84a-106">Keywords</span></span>|<span data-ttu-id="aa84a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="aa84a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="aa84a-108">수준</span><span class="sxs-lookup"><span data-stu-id="aa84a-108">Level</span></span>|<span data-ttu-id="aa84a-109">자세히</span><span class="sxs-lookup"><span data-stu-id="aa84a-109">Verbose</span></span>|  
|<span data-ttu-id="aa84a-110">채널</span><span class="sxs-lookup"><span data-stu-id="aa84a-110">Channel</span></span>|<span data-ttu-id="aa84a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="aa84a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa84a-112">설명</span><span class="sxs-lookup"><span data-stu-id="aa84a-112">Description</span></span>  
 <span data-ttu-id="aa84a-113">SQL 명령이 실행을 완료했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa84a-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa84a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="aa84a-114">Message</span></span>  
 <span data-ttu-id="aa84a-115">SQL 명령 실행 종료: %1</span><span class="sxs-lookup"><span data-stu-id="aa84a-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa84a-116">설명</span><span class="sxs-lookup"><span data-stu-id="aa84a-116">Details</span></span>  
  
|<span data-ttu-id="aa84a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="aa84a-117">Data Item Name</span></span>|<span data-ttu-id="aa84a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="aa84a-118">Data Item Type</span></span>|<span data-ttu-id="aa84a-119">설명</span><span class="sxs-lookup"><span data-stu-id="aa84a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa84a-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="aa84a-120">SqlCommand</span></span>|<span data-ttu-id="aa84a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa84a-121">xs:string</span></span>|<span data-ttu-id="aa84a-122">실행된 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="aa84a-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="aa84a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa84a-123">AppDomain</span></span>|<span data-ttu-id="aa84a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa84a-124">xs:string</span></span>|<span data-ttu-id="aa84a-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="aa84a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
