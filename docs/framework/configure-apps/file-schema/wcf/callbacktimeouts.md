---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398193"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="4304a-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="4304a-101">\<callbackTimeouts></span></span>
<span data-ttu-id="4304a-102">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4304a-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="4304a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4304a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4304a-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4304a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4304a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4304a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4304a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4304a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4304a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4304a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4304a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<callbackTimeOuts 제한 >**</span><span class="sxs-lookup"><span data-stu-id="4304a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4304a-109">구문</span><span class="sxs-lookup"><span data-stu-id="4304a-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="4304a-110">형식</span><span class="sxs-lookup"><span data-stu-id="4304a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4304a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4304a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4304a-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4304a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4304a-113">특성</span><span class="sxs-lookup"><span data-stu-id="4304a-113">Attributes</span></span>  
  
|<span data-ttu-id="4304a-114">특성</span><span class="sxs-lookup"><span data-stu-id="4304a-114">Attribute</span></span>|<span data-ttu-id="4304a-115">Description</span><span class="sxs-lookup"><span data-stu-id="4304a-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="4304a-116">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4304a-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="4304a-117">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="4304a-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4304a-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4304a-118">Child Elements</span></span>  
 <span data-ttu-id="4304a-119">없음</span><span class="sxs-lookup"><span data-stu-id="4304a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4304a-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4304a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4304a-121">요소</span><span class="sxs-lookup"><span data-stu-id="4304a-121">Element</span></span>|<span data-ttu-id="4304a-122">설명</span><span class="sxs-lookup"><span data-stu-id="4304a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4304a-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4304a-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4304a-124">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4304a-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4304a-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="4304a-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
