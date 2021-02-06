---
description: 다음에 대해 자세히 알아보세요. <callbackTimeouts>
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 8e2e05ad23f661c38430ccddc615c37705e6fc44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639200"
---
# \<callbackTimeouts>

<span data-ttu-id="f017c-102">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f017c-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="f017c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f017c-103">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="f017c-104">Type</span><span class="sxs-lookup"><span data-stu-id="f017c-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f017c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f017c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f017c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f017c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f017c-107">특성</span><span class="sxs-lookup"><span data-stu-id="f017c-107">Attributes</span></span>  
  
|<span data-ttu-id="f017c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f017c-108">Attribute</span></span>|<span data-ttu-id="f017c-109">설명</span><span class="sxs-lookup"><span data-stu-id="f017c-109">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="f017c-110">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f017c-110">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="f017c-111">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="f017c-111">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f017c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f017c-112">Child Elements</span></span>  

 <span data-ttu-id="f017c-113">없음</span><span class="sxs-lookup"><span data-stu-id="f017c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f017c-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f017c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f017c-115">요소</span><span class="sxs-lookup"><span data-stu-id="f017c-115">Element</span></span>|<span data-ttu-id="f017c-116">설명</span><span class="sxs-lookup"><span data-stu-id="f017c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f017c-117">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f017c-117">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f017c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f017c-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
