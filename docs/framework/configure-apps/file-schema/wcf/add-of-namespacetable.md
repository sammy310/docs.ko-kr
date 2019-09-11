---
title: <namespaceTable>의 <add>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850389"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="a29e3-102">\<\<namespaceTable > > 추가</span><span class="sxs-lookup"><span data-stu-id="a29e3-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="a29e3-103">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="a29e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a29e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a29e3-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a29e3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a29e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<라우팅 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="a29e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="a29e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namespaceTable >** ](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="a29e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="a29e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="a29e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a29e3-109">구문</span><span class="sxs-lookup"><span data-stu-id="a29e3-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a29e3-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a29e3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a29e3-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a29e3-112">특성</span><span class="sxs-lookup"><span data-stu-id="a29e3-112">Attributes</span></span>  
  
|<span data-ttu-id="a29e3-113">특성</span><span class="sxs-lookup"><span data-stu-id="a29e3-113">Attribute</span></span>|<span data-ttu-id="a29e3-114">설명</span><span class="sxs-lookup"><span data-stu-id="a29e3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a29e3-115">namespace</span><span class="sxs-lookup"><span data-stu-id="a29e3-115">namespace</span></span>|<span data-ttu-id="a29e3-116">네임스페이스를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="a29e3-117">prefix</span><span class="sxs-lookup"><span data-stu-id="a29e3-117">prefix</span></span>|<span data-ttu-id="a29e3-118">이 네임스페이스에 대한 접두사를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a29e3-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a29e3-119">Child Elements</span></span>  
 <span data-ttu-id="a29e3-120">없음</span><span class="sxs-lookup"><span data-stu-id="a29e3-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a29e3-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a29e3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a29e3-122">요소</span><span class="sxs-lookup"><span data-stu-id="a29e3-122">Element</span></span>|<span data-ttu-id="a29e3-123">Description</span><span class="sxs-lookup"><span data-stu-id="a29e3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a29e3-124">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="a29e3-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="a29e3-125">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a29e3-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="a29e3-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
