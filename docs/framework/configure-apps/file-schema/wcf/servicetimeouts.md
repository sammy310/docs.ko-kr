---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399558"
---
# \<serviceTimeouts>
<span data-ttu-id="08646-101">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08646-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="08646-102">구문</span><span class="sxs-lookup"><span data-stu-id="08646-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="08646-103">Type</span><span class="sxs-lookup"><span data-stu-id="08646-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08646-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="08646-104">Attributes and Elements</span></span>  
 <span data-ttu-id="08646-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08646-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08646-106">특성</span><span class="sxs-lookup"><span data-stu-id="08646-106">Attributes</span></span>  
  
|<span data-ttu-id="08646-107">attribute</span><span class="sxs-lookup"><span data-stu-id="08646-107">Attribute</span></span>|<span data-ttu-id="08646-108">Description</span><span class="sxs-lookup"><span data-stu-id="08646-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="08646-109">클라이언트에서 서버로 트랜잭션을 전달해야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08646-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="08646-110">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="08646-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08646-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="08646-111">Child Elements</span></span>  
 <span data-ttu-id="08646-112">없음</span><span class="sxs-lookup"><span data-stu-id="08646-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08646-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="08646-113">Parent Elements</span></span>  
  
|<span data-ttu-id="08646-114">요소</span><span class="sxs-lookup"><span data-stu-id="08646-114">Element</span></span>|<span data-ttu-id="08646-115">Description</span><span class="sxs-lookup"><span data-stu-id="08646-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="08646-116">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08646-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08646-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08646-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
