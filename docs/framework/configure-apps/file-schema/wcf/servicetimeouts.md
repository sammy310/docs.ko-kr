---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399558"
---
# <a name="servicetimeouts"></a><span data-ttu-id="a28bb-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="a28bb-101">\<serviceTimeouts></span></span>
<span data-ttu-id="a28bb-102">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a28bb-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="a28bb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a28bb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a28bb-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a28bb-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a28bb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a28bb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a28bb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a28bb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="a28bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a28bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="a28bb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTimeouts 제한 >**</span><span class="sxs-lookup"><span data-stu-id="a28bb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a28bb-109">구문</span><span class="sxs-lookup"><span data-stu-id="a28bb-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="a28bb-110">형식</span><span class="sxs-lookup"><span data-stu-id="a28bb-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a28bb-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a28bb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a28bb-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a28bb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a28bb-113">특성</span><span class="sxs-lookup"><span data-stu-id="a28bb-113">Attributes</span></span>  
  
|<span data-ttu-id="a28bb-114">특성</span><span class="sxs-lookup"><span data-stu-id="a28bb-114">Attribute</span></span>|<span data-ttu-id="a28bb-115">Description</span><span class="sxs-lookup"><span data-stu-id="a28bb-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="a28bb-116">클라이언트에서 서버로 트랜잭션을 전달해야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a28bb-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="a28bb-117">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="a28bb-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a28bb-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a28bb-118">Child Elements</span></span>  
 <span data-ttu-id="a28bb-119">없음</span><span class="sxs-lookup"><span data-stu-id="a28bb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a28bb-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a28bb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a28bb-121">요소</span><span class="sxs-lookup"><span data-stu-id="a28bb-121">Element</span></span>|<span data-ttu-id="a28bb-122">설명</span><span class="sxs-lookup"><span data-stu-id="a28bb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a28bb-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a28bb-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a28bb-124">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a28bb-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a28bb-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="a28bb-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
