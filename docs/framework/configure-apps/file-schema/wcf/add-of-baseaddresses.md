---
title: <baseAddresses>의 <add>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850588"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="389ae-102">\<baseAddresses>의 \<add></span><span class="sxs-lookup"><span data-stu-id="389ae-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="389ae-103">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="389ae-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="389ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="389ae-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="389ae-105">Type</span><span class="sxs-lookup"><span data-stu-id="389ae-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="389ae-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="389ae-106">Attributes and Elements</span></span>  
 <span data-ttu-id="389ae-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="389ae-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="389ae-108">특성</span><span class="sxs-lookup"><span data-stu-id="389ae-108">Attributes</span></span>  
  
|<span data-ttu-id="389ae-109">attribute</span><span class="sxs-lookup"><span data-stu-id="389ae-109">Attribute</span></span>|<span data-ttu-id="389ae-110">Description</span><span class="sxs-lookup"><span data-stu-id="389ae-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="389ae-111">서비스 호스트에서 사용하는 기본 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="389ae-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="389ae-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="389ae-112">Child Elements</span></span>  
 <span data-ttu-id="389ae-113">없음</span><span class="sxs-lookup"><span data-stu-id="389ae-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="389ae-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="389ae-114">Parent Elements</span></span>  
  
|<span data-ttu-id="389ae-115">요소</span><span class="sxs-lookup"><span data-stu-id="389ae-115">Element</span></span>|<span data-ttu-id="389ae-116">Description</span><span class="sxs-lookup"><span data-stu-id="389ae-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="389ae-117">`baseAddress` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="389ae-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="389ae-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="389ae-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="389ae-119">호스팅</span><span class="sxs-lookup"><span data-stu-id="389ae-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
