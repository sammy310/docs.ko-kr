---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673422"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="3d4ef-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="3d4ef-101">\<callbackTimeouts></span></span>
<span data-ttu-id="3d4ef-102">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4ef-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="3d4ef-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d4ef-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d4ef-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3d4ef-104">\<behaviors></span></span>  
<span data-ttu-id="3d4ef-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3d4ef-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="3d4ef-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3d4ef-106">\<behavior></span></span>  
<span data-ttu-id="3d4ef-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="3d4ef-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d4ef-108">구문</span><span class="sxs-lookup"><span data-stu-id="3d4ef-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="3d4ef-109">형식</span><span class="sxs-lookup"><span data-stu-id="3d4ef-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d4ef-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3d4ef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d4ef-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4ef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d4ef-112">특성</span><span class="sxs-lookup"><span data-stu-id="3d4ef-112">Attributes</span></span>  
  
|<span data-ttu-id="3d4ef-113">특성</span><span class="sxs-lookup"><span data-stu-id="3d4ef-113">Attribute</span></span>|<span data-ttu-id="3d4ef-114">설명</span><span class="sxs-lookup"><span data-stu-id="3d4ef-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="3d4ef-115">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3d4ef-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="3d4ef-116">기본값은 "00: 00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3d4ef-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d4ef-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3d4ef-117">Child Elements</span></span>  
 <span data-ttu-id="3d4ef-118">없음</span><span class="sxs-lookup"><span data-stu-id="3d4ef-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d4ef-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3d4ef-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3d4ef-120">요소</span><span class="sxs-lookup"><span data-stu-id="3d4ef-120">Element</span></span>|<span data-ttu-id="3d4ef-121">설명</span><span class="sxs-lookup"><span data-stu-id="3d4ef-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d4ef-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3d4ef-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3d4ef-123">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4ef-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d4ef-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="3d4ef-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
