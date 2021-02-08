---
description: 다음에 대해 자세히 알아보세요. <timeOuts>
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 097569d1742f6486ddfb5fb3c3d98ba106424f45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786592"
---
# \<timeOuts>

<span data-ttu-id="63756-102">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="63756-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="63756-103">구문</span><span class="sxs-lookup"><span data-stu-id="63756-103">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63756-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="63756-104">Attributes and Elements</span></span>  

 <span data-ttu-id="63756-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63756-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63756-106">특성</span><span class="sxs-lookup"><span data-stu-id="63756-106">Attributes</span></span>  
  
|<span data-ttu-id="63756-107">attribute</span><span class="sxs-lookup"><span data-stu-id="63756-107">Attribute</span></span>|<span data-ttu-id="63756-108">설명</span><span class="sxs-lookup"><span data-stu-id="63756-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="63756-109">서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="63756-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="63756-110">서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="63756-110">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63756-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="63756-111">Child Elements</span></span>  

 <span data-ttu-id="63756-112">없음</span><span class="sxs-lookup"><span data-stu-id="63756-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63756-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="63756-113">Parent Elements</span></span>  
  
|<span data-ttu-id="63756-114">요소</span><span class="sxs-lookup"><span data-stu-id="63756-114">Element</span></span>|<span data-ttu-id="63756-115">설명</span><span class="sxs-lookup"><span data-stu-id="63756-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="63756-116">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="63756-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63756-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63756-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="63756-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="63756-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
