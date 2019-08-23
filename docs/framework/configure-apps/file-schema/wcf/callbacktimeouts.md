---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: d57a888a19e684ac13632c1ab2476e304667c3e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919659"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="fd3da-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="fd3da-101">\<callbackTimeouts></span></span>
<span data-ttu-id="fd3da-102">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3da-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="fd3da-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd3da-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd3da-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fd3da-104">\<behaviors></span></span>  
<span data-ttu-id="fd3da-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="fd3da-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="fd3da-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fd3da-106">\<behavior></span></span>  
<span data-ttu-id="fd3da-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="fd3da-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3da-108">구문</span><span class="sxs-lookup"><span data-stu-id="fd3da-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="fd3da-109">형식</span><span class="sxs-lookup"><span data-stu-id="fd3da-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd3da-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd3da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd3da-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd3da-112">특성</span><span class="sxs-lookup"><span data-stu-id="fd3da-112">Attributes</span></span>  
  
|<span data-ttu-id="fd3da-113">특성</span><span class="sxs-lookup"><span data-stu-id="fd3da-113">Attribute</span></span>|<span data-ttu-id="fd3da-114">설명</span><span class="sxs-lookup"><span data-stu-id="fd3da-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="fd3da-115">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3da-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="fd3da-116">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3da-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd3da-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd3da-117">Child Elements</span></span>  
 <span data-ttu-id="fd3da-118">없음</span><span class="sxs-lookup"><span data-stu-id="fd3da-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd3da-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd3da-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fd3da-120">요소</span><span class="sxs-lookup"><span data-stu-id="fd3da-120">Element</span></span>|<span data-ttu-id="fd3da-121">설명</span><span class="sxs-lookup"><span data-stu-id="fd3da-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd3da-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fd3da-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="fd3da-123">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3da-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd3da-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd3da-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
