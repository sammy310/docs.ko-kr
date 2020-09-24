---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: f7e513bb5c486fa5f7c39c9b2e3cfcd26bd7c219
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157098"
---
# \<timeOuts>

<span data-ttu-id="7ea06-101">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ea06-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="7ea06-102">구문</span><span class="sxs-lookup"><span data-stu-id="7ea06-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ea06-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7ea06-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7ea06-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea06-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ea06-105">특성</span><span class="sxs-lookup"><span data-stu-id="7ea06-105">Attributes</span></span>  
  
|<span data-ttu-id="7ea06-106">attribute</span><span class="sxs-lookup"><span data-stu-id="7ea06-106">Attribute</span></span>|<span data-ttu-id="7ea06-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ea06-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="7ea06-108">서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea06-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="7ea06-109">서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea06-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ea06-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7ea06-110">Child Elements</span></span>  

 <span data-ttu-id="7ea06-111">없음</span><span class="sxs-lookup"><span data-stu-id="7ea06-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ea06-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7ea06-112">Parent Elements</span></span>  
  
|<span data-ttu-id="7ea06-113">요소</span><span class="sxs-lookup"><span data-stu-id="7ea06-113">Element</span></span>|<span data-ttu-id="7ea06-114">설명</span><span class="sxs-lookup"><span data-stu-id="7ea06-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="7ea06-115">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea06-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ea06-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ea06-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="7ea06-117">호스팅</span><span class="sxs-lookup"><span data-stu-id="7ea06-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
