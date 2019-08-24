---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: 09e079864369115c773c58c451fc5e0a33a3ae9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774376"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="0e084-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="0e084-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="0e084-103">속성</span><span class="sxs-lookup"><span data-stu-id="0e084-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e084-104">ID</span><span class="sxs-lookup"><span data-stu-id="0e084-104">ID</span></span>|<span data-ttu-id="0e084-105">4202</span><span class="sxs-lookup"><span data-stu-id="0e084-105">4202</span></span>|  
|<span data-ttu-id="0e084-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0e084-106">Keywords</span></span>|<span data-ttu-id="0e084-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="0e084-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="0e084-108">수준</span><span class="sxs-lookup"><span data-stu-id="0e084-108">Level</span></span>|<span data-ttu-id="0e084-109">자세히</span><span class="sxs-lookup"><span data-stu-id="0e084-109">Verbose</span></span>|  
|<span data-ttu-id="0e084-110">채널</span><span class="sxs-lookup"><span data-stu-id="0e084-110">Channel</span></span>|<span data-ttu-id="0e084-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="0e084-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e084-112">설명</span><span class="sxs-lookup"><span data-stu-id="0e084-112">Description</span></span>  
 <span data-ttu-id="0e084-113">SQL 명령이 실행되고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e084-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e084-114">메시지</span><span class="sxs-lookup"><span data-stu-id="0e084-114">Message</span></span>  
 <span data-ttu-id="0e084-115">SQL 명령 실행 시작: %1</span><span class="sxs-lookup"><span data-stu-id="0e084-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e084-116">설명</span><span class="sxs-lookup"><span data-stu-id="0e084-116">Details</span></span>  
  
|<span data-ttu-id="0e084-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0e084-117">Data Item Name</span></span>|<span data-ttu-id="0e084-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0e084-118">Data Item Type</span></span>|<span data-ttu-id="0e084-119">설명</span><span class="sxs-lookup"><span data-stu-id="0e084-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e084-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="0e084-120">SqlCommand</span></span>|<span data-ttu-id="0e084-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e084-121">xs:string</span></span>|<span data-ttu-id="0e084-122">실행된 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="0e084-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="0e084-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e084-123">AppDomain</span></span>|<span data-ttu-id="0e084-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e084-124">xs:string</span></span>|<span data-ttu-id="0e084-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0e084-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
