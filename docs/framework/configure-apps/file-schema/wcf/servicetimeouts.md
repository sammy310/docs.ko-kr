---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075524"
---
# <a name="servicetimeouts"></a><span data-ttu-id="b4a20-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="b4a20-101">\<serviceTimeouts></span></span>
<span data-ttu-id="b4a20-102">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a20-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="b4a20-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b4a20-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b4a20-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b4a20-104">\<behaviors></span></span>  
<span data-ttu-id="b4a20-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b4a20-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="b4a20-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b4a20-106">\<behavior></span></span>  
<span data-ttu-id="b4a20-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="b4a20-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a20-108">구문</span><span class="sxs-lookup"><span data-stu-id="b4a20-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="b4a20-109">형식</span><span class="sxs-lookup"><span data-stu-id="b4a20-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4a20-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b4a20-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b4a20-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a20-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4a20-112">특성</span><span class="sxs-lookup"><span data-stu-id="b4a20-112">Attributes</span></span>  
  
|<span data-ttu-id="b4a20-113">특성</span><span class="sxs-lookup"><span data-stu-id="b4a20-113">Attribute</span></span>|<span data-ttu-id="b4a20-114">설명</span><span class="sxs-lookup"><span data-stu-id="b4a20-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="b4a20-115">클라이언트에서 서버로 트랜잭션을 전달해야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a20-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="b4a20-116">기본값은 "00: 00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a20-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4a20-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b4a20-117">Child Elements</span></span>  
 <span data-ttu-id="b4a20-118">없음</span><span class="sxs-lookup"><span data-stu-id="b4a20-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4a20-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b4a20-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b4a20-120">요소</span><span class="sxs-lookup"><span data-stu-id="b4a20-120">Element</span></span>|<span data-ttu-id="b4a20-121">설명</span><span class="sxs-lookup"><span data-stu-id="b4a20-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4a20-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b4a20-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b4a20-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a20-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4a20-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4a20-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
