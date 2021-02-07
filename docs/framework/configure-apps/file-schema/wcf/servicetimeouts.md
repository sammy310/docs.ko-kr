---
description: 다음에 대해 자세히 알아보세요. <serviceTimeouts>
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: bc9ef99078f8c6fa3b441604e14df928eec054e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682730"
---
# \<serviceTimeouts>

<span data-ttu-id="b2e1b-102">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-102">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="b2e1b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2e1b-103">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="b2e1b-104">Type</span><span class="sxs-lookup"><span data-stu-id="b2e1b-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2e1b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2e1b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b2e1b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2e1b-107">특성</span><span class="sxs-lookup"><span data-stu-id="b2e1b-107">Attributes</span></span>  
  
|<span data-ttu-id="b2e1b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b2e1b-108">Attribute</span></span>|<span data-ttu-id="b2e1b-109">설명</span><span class="sxs-lookup"><span data-stu-id="b2e1b-109">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="b2e1b-110">클라이언트에서 서버로 트랜잭션을 전달해야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-110">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="b2e1b-111">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-111">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2e1b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2e1b-112">Child Elements</span></span>  

 <span data-ttu-id="b2e1b-113">없음</span><span class="sxs-lookup"><span data-stu-id="b2e1b-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2e1b-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2e1b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b2e1b-115">요소</span><span class="sxs-lookup"><span data-stu-id="b2e1b-115">Element</span></span>|<span data-ttu-id="b2e1b-116">설명</span><span class="sxs-lookup"><span data-stu-id="b2e1b-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b2e1b-117">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2e1b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2e1b-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
