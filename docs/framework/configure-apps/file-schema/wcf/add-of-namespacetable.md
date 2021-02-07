---
description: '다음에 대 한 자세한 정보:: <add><namespaceTable>'
title: <namespaceTable>의 <add>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: b7804bdec4a1fb2199c81ba0dde031b80b451d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750262"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="fd8ab-103">\<namespaceTable>의 \<add></span><span class="sxs-lookup"><span data-stu-id="fd8ab-103">\<add> of \<namespaceTable></span></span>

<span data-ttu-id="fd8ab-104">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd8ab-104">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fd8ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd8ab-105">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd8ab-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd8ab-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fd8ab-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd8ab-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd8ab-108">특성</span><span class="sxs-lookup"><span data-stu-id="fd8ab-108">Attributes</span></span>  
  
|<span data-ttu-id="fd8ab-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fd8ab-109">Attribute</span></span>|<span data-ttu-id="fd8ab-110">설명</span><span class="sxs-lookup"><span data-stu-id="fd8ab-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd8ab-111">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fd8ab-111">namespace</span></span>|<span data-ttu-id="fd8ab-112">네임스페이스를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd8ab-112">A string containing the namespace.</span></span>|  
|<span data-ttu-id="fd8ab-113">접두사</span><span class="sxs-lookup"><span data-stu-id="fd8ab-113">prefix</span></span>|<span data-ttu-id="fd8ab-114">이 네임스페이스에 대한 접두사를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd8ab-114">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd8ab-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd8ab-115">Child Elements</span></span>  

 <span data-ttu-id="fd8ab-116">없음</span><span class="sxs-lookup"><span data-stu-id="fd8ab-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd8ab-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd8ab-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fd8ab-118">요소</span><span class="sxs-lookup"><span data-stu-id="fd8ab-118">Element</span></span>|<span data-ttu-id="fd8ab-119">설명</span><span class="sxs-lookup"><span data-stu-id="fd8ab-119">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="fd8ab-120">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd8ab-120">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd8ab-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd8ab-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
