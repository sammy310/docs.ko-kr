---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: f117c7759bab1759a7d614db275de88f8b37c331
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774428"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="99cec-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="99cec-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="99cec-103">속성</span><span class="sxs-lookup"><span data-stu-id="99cec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99cec-104">ID</span><span class="sxs-lookup"><span data-stu-id="99cec-104">ID</span></span>|<span data-ttu-id="99cec-105">39456</span><span class="sxs-lookup"><span data-stu-id="99cec-105">39456</span></span>|  
|<span data-ttu-id="99cec-106">키워드</span><span class="sxs-lookup"><span data-stu-id="99cec-106">Keywords</span></span>|<span data-ttu-id="99cec-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="99cec-107">WFTracking</span></span>|  
|<span data-ttu-id="99cec-108">수준</span><span class="sxs-lookup"><span data-stu-id="99cec-108">Level</span></span>|<span data-ttu-id="99cec-109">경고</span><span class="sxs-lookup"><span data-stu-id="99cec-109">Warning</span></span>|  
|<span data-ttu-id="99cec-110">채널</span><span class="sxs-lookup"><span data-stu-id="99cec-110">Channel</span></span>|<span data-ttu-id="99cec-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="99cec-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="99cec-112">설명</span><span class="sxs-lookup"><span data-stu-id="99cec-112">Description</span></span>  
 <span data-ttu-id="99cec-113">추적 레코드의 크기가 ETW 세션 공급자에서 허용하는 최대값을 초과하기 때문에 추적 레코드가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99cec-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="99cec-114">메시지</span><span class="sxs-lookup"><span data-stu-id="99cec-114">Message</span></span>  
 <span data-ttu-id="99cec-115">추적 레코드 %1의 크기가 %2 공급자의 ETW 세션에서 허용된 최대값을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="99cec-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="99cec-116">설명</span><span class="sxs-lookup"><span data-stu-id="99cec-116">Details</span></span>  
  
|<span data-ttu-id="99cec-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="99cec-117">Data Item Name</span></span>|<span data-ttu-id="99cec-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="99cec-118">Data Item Type</span></span>|<span data-ttu-id="99cec-119">설명</span><span class="sxs-lookup"><span data-stu-id="99cec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="99cec-120">예외</span><span class="sxs-lookup"><span data-stu-id="99cec-120">Exception</span></span>|<span data-ttu-id="99cec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="99cec-121">xs:string</span></span>|<span data-ttu-id="99cec-122">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="99cec-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="99cec-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="99cec-123">AppDomain</span></span>|<span data-ttu-id="99cec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="99cec-124">xs:string</span></span>|<span data-ttu-id="99cec-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="99cec-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
