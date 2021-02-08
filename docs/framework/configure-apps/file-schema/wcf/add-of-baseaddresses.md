---
description: '다음에 대 한 자세한 정보:: <add><baseAddresses>'
title: <baseAddresses>의 <add>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: b25a4b5551784ecd8e67569c82c1388a144a9c9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804064"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="58f39-103">\<baseAddresses>의 \<add></span><span class="sxs-lookup"><span data-stu-id="58f39-103">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="58f39-104">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58f39-104">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="58f39-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58f39-105">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="58f39-106">Type</span><span class="sxs-lookup"><span data-stu-id="58f39-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58f39-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="58f39-107">Attributes and Elements</span></span>  

 <span data-ttu-id="58f39-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58f39-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58f39-109">특성</span><span class="sxs-lookup"><span data-stu-id="58f39-109">Attributes</span></span>  
  
|<span data-ttu-id="58f39-110">attribute</span><span class="sxs-lookup"><span data-stu-id="58f39-110">Attribute</span></span>|<span data-ttu-id="58f39-111">설명</span><span class="sxs-lookup"><span data-stu-id="58f39-111">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="58f39-112">서비스 호스트에서 사용하는 기본 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="58f39-112">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58f39-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="58f39-113">Child Elements</span></span>  

 <span data-ttu-id="58f39-114">없음</span><span class="sxs-lookup"><span data-stu-id="58f39-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58f39-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="58f39-115">Parent Elements</span></span>  
  
|<span data-ttu-id="58f39-116">요소</span><span class="sxs-lookup"><span data-stu-id="58f39-116">Element</span></span>|<span data-ttu-id="58f39-117">설명</span><span class="sxs-lookup"><span data-stu-id="58f39-117">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="58f39-118">`baseAddress` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="58f39-118">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58f39-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58f39-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="58f39-120">호스팅</span><span class="sxs-lookup"><span data-stu-id="58f39-120">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
