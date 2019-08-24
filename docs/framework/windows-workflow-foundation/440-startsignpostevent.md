---
title: 440 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 4b2b6b0fa9df4725edd4929512eb1d7534d933b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774172"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="68147-102">440 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="68147-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="68147-103">속성</span><span class="sxs-lookup"><span data-stu-id="68147-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68147-104">ID</span><span class="sxs-lookup"><span data-stu-id="68147-104">ID</span></span>|<span data-ttu-id="68147-105">440</span><span class="sxs-lookup"><span data-stu-id="68147-105">440</span></span>|  
|<span data-ttu-id="68147-106">키워드</span><span class="sxs-lookup"><span data-stu-id="68147-106">Keywords</span></span>|<span data-ttu-id="68147-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="68147-107">Troubleshooting</span></span>|  
|<span data-ttu-id="68147-108">수준</span><span class="sxs-lookup"><span data-stu-id="68147-108">Level</span></span>|<span data-ttu-id="68147-109">정보</span><span class="sxs-lookup"><span data-stu-id="68147-109">Information</span></span>|  
|<span data-ttu-id="68147-110">채널</span><span class="sxs-lookup"><span data-stu-id="68147-110">Channel</span></span>|<span data-ttu-id="68147-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="68147-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="68147-112">설명</span><span class="sxs-lookup"><span data-stu-id="68147-112">Description</span></span>  
 <span data-ttu-id="68147-113">동작 추적에서 보내거나 받을 메시지가 동작 경계를 넘기 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68147-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="68147-114">메시지</span><span class="sxs-lookup"><span data-stu-id="68147-114">Message</span></span>  
 <span data-ttu-id="68147-115">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="68147-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="68147-116">설명</span><span class="sxs-lookup"><span data-stu-id="68147-116">Details</span></span>  
  
|<span data-ttu-id="68147-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="68147-117">Data Item Name</span></span>|<span data-ttu-id="68147-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="68147-118">Data Item Type</span></span>|<span data-ttu-id="68147-119">설명</span><span class="sxs-lookup"><span data-stu-id="68147-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="68147-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="68147-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="68147-121">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68147-121">The name of the activity.</span></span>|  
|<span data-ttu-id="68147-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="68147-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="68147-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="68147-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
