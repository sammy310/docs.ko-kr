---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854968"
---
# \<timeOuts>
<span data-ttu-id="45372-101">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45372-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="45372-102">구문</span><span class="sxs-lookup"><span data-stu-id="45372-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45372-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="45372-103">Attributes and Elements</span></span>  
 <span data-ttu-id="45372-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45372-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45372-105">특성</span><span class="sxs-lookup"><span data-stu-id="45372-105">Attributes</span></span>  
  
|<span data-ttu-id="45372-106">attribute</span><span class="sxs-lookup"><span data-stu-id="45372-106">Attribute</span></span>|<span data-ttu-id="45372-107">Description</span><span class="sxs-lookup"><span data-stu-id="45372-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="45372-108">서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="45372-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="45372-109">서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="45372-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45372-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="45372-110">Child Elements</span></span>  
 <span data-ttu-id="45372-111">없음</span><span class="sxs-lookup"><span data-stu-id="45372-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45372-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="45372-112">Parent Elements</span></span>  
  
|<span data-ttu-id="45372-113">요소</span><span class="sxs-lookup"><span data-stu-id="45372-113">Element</span></span>|<span data-ttu-id="45372-114">Description</span><span class="sxs-lookup"><span data-stu-id="45372-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="45372-115">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="45372-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45372-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45372-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="45372-117">호스팅</span><span class="sxs-lookup"><span data-stu-id="45372-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
