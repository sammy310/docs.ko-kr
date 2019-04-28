---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755625"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="73986-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="73986-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="73986-103">속성</span><span class="sxs-lookup"><span data-stu-id="73986-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73986-104">ID</span><span class="sxs-lookup"><span data-stu-id="73986-104">ID</span></span>|<span data-ttu-id="73986-105">2577</span><span class="sxs-lookup"><span data-stu-id="73986-105">2577</span></span>|  
|<span data-ttu-id="73986-106">키워드</span><span class="sxs-lookup"><span data-stu-id="73986-106">Keywords</span></span>|<span data-ttu-id="73986-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="73986-107">WFActivities</span></span>|  
|<span data-ttu-id="73986-108">수준</span><span class="sxs-lookup"><span data-stu-id="73986-108">Level</span></span>|<span data-ttu-id="73986-109">경고</span><span class="sxs-lookup"><span data-stu-id="73986-109">Warning</span></span>|  
|<span data-ttu-id="73986-110">채널</span><span class="sxs-lookup"><span data-stu-id="73986-110">Channel</span></span>|<span data-ttu-id="73986-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="73986-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73986-112">설명</span><span class="sxs-lookup"><span data-stu-id="73986-112">Description</span></span>  
 <span data-ttu-id="73986-113">취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73986-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73986-114">메시지</span><span class="sxs-lookup"><span data-stu-id="73986-114">Message</span></span>  
 <span data-ttu-id="73986-115">취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73986-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73986-116">설명</span><span class="sxs-lookup"><span data-stu-id="73986-116">Details</span></span>  
  
|<span data-ttu-id="73986-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="73986-117">Data Item Name</span></span>|<span data-ttu-id="73986-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="73986-118">Data Item Type</span></span>|<span data-ttu-id="73986-119">설명</span><span class="sxs-lookup"><span data-stu-id="73986-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73986-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="73986-120">DisplayName</span></span>|<span data-ttu-id="73986-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="73986-121">xs:string</span></span>|<span data-ttu-id="73986-122">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73986-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="73986-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73986-123">AppDomain</span></span>|<span data-ttu-id="73986-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="73986-124">xs:string</span></span>|<span data-ttu-id="73986-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="73986-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
