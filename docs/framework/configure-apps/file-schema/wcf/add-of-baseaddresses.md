---
title: <baseAddresses>의 <add>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: cd0ef5cc5f0f809bdafa23bd312e7e30fcdccc21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181611"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="bd019-102">\<baseAddresses>의 \<add></span><span class="sxs-lookup"><span data-stu-id="bd019-102">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="bd019-103">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bd019-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="bd019-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd019-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="bd019-105">형식</span><span class="sxs-lookup"><span data-stu-id="bd019-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd019-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bd019-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bd019-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd019-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd019-108">특성</span><span class="sxs-lookup"><span data-stu-id="bd019-108">Attributes</span></span>  
  
|<span data-ttu-id="bd019-109">attribute</span><span class="sxs-lookup"><span data-stu-id="bd019-109">Attribute</span></span>|<span data-ttu-id="bd019-110">설명</span><span class="sxs-lookup"><span data-stu-id="bd019-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="bd019-111">서비스 호스트에서 사용하는 기본 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bd019-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd019-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bd019-112">Child Elements</span></span>  

 <span data-ttu-id="bd019-113">없음</span><span class="sxs-lookup"><span data-stu-id="bd019-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd019-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bd019-114">Parent Elements</span></span>  
  
|<span data-ttu-id="bd019-115">요소</span><span class="sxs-lookup"><span data-stu-id="bd019-115">Element</span></span>|<span data-ttu-id="bd019-116">설명</span><span class="sxs-lookup"><span data-stu-id="bd019-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="bd019-117">`baseAddress` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bd019-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd019-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd019-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="bd019-119">호스팅</span><span class="sxs-lookup"><span data-stu-id="bd019-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
