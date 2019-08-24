---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 3c981888b491f2797a431c2103ba3f5f0bd17046
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774324"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="02feb-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="02feb-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="02feb-103">속성</span><span class="sxs-lookup"><span data-stu-id="02feb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02feb-104">ID</span><span class="sxs-lookup"><span data-stu-id="02feb-104">ID</span></span>|<span data-ttu-id="02feb-105">4206</span><span class="sxs-lookup"><span data-stu-id="02feb-105">4206</span></span>|  
|<span data-ttu-id="02feb-106">키워드</span><span class="sxs-lookup"><span data-stu-id="02feb-106">Keywords</span></span>|<span data-ttu-id="02feb-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="02feb-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="02feb-108">수준</span><span class="sxs-lookup"><span data-stu-id="02feb-108">Level</span></span>|<span data-ttu-id="02feb-109">Error</span><span class="sxs-lookup"><span data-stu-id="02feb-109">Error</span></span>|  
|<span data-ttu-id="02feb-110">채널</span><span class="sxs-lookup"><span data-stu-id="02feb-110">Channel</span></span>|<span data-ttu-id="02feb-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="02feb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02feb-112">설명</span><span class="sxs-lookup"><span data-stu-id="02feb-112">Description</span></span>  
 <span data-ttu-id="02feb-113">인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02feb-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02feb-114">메시지</span><span class="sxs-lookup"><span data-stu-id="02feb-114">Message</span></span>  
 <span data-ttu-id="02feb-115">인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="02feb-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02feb-116">설명</span><span class="sxs-lookup"><span data-stu-id="02feb-116">Details</span></span>  
  
|<span data-ttu-id="02feb-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="02feb-117">Data Item Name</span></span>|<span data-ttu-id="02feb-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="02feb-118">Data Item Type</span></span>|<span data-ttu-id="02feb-119">설명</span><span class="sxs-lookup"><span data-stu-id="02feb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02feb-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="02feb-120">ExceptionMessage</span></span>|<span data-ttu-id="02feb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="02feb-121">xs:string</span></span>|<span data-ttu-id="02feb-122">SQL 예외로부터의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="02feb-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="02feb-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02feb-123">AppDomain</span></span>|<span data-ttu-id="02feb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="02feb-124">xs:string</span></span>|<span data-ttu-id="02feb-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="02feb-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
