---
title: <namespaceTable>의 <add>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e65b66170465a8b3bb60754feebb7730b959d9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089720"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="df3b2-102">\<추가 >의 \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="df3b2-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="df3b2-103">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df3b2-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="df3b2-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="df3b2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="df3b2-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="df3b2-105">\<routing></span></span>  
<span data-ttu-id="df3b2-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="df3b2-106">\<namespaceTable></span></span>  
<span data-ttu-id="df3b2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="df3b2-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df3b2-108">구문</span><span class="sxs-lookup"><span data-stu-id="df3b2-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df3b2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="df3b2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="df3b2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df3b2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df3b2-111">특성</span><span class="sxs-lookup"><span data-stu-id="df3b2-111">Attributes</span></span>  
  
|<span data-ttu-id="df3b2-112">특성</span><span class="sxs-lookup"><span data-stu-id="df3b2-112">Attribute</span></span>|<span data-ttu-id="df3b2-113">설명</span><span class="sxs-lookup"><span data-stu-id="df3b2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df3b2-114">namespace</span><span class="sxs-lookup"><span data-stu-id="df3b2-114">namespace</span></span>|<span data-ttu-id="df3b2-115">네임스페이스를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df3b2-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="df3b2-116">prefix</span><span class="sxs-lookup"><span data-stu-id="df3b2-116">prefix</span></span>|<span data-ttu-id="df3b2-117">이 네임스페이스에 대한 접두사를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df3b2-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df3b2-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="df3b2-118">Child Elements</span></span>  
 <span data-ttu-id="df3b2-119">없음</span><span class="sxs-lookup"><span data-stu-id="df3b2-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df3b2-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="df3b2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="df3b2-121">요소</span><span class="sxs-lookup"><span data-stu-id="df3b2-121">Element</span></span>|<span data-ttu-id="df3b2-122">설명</span><span class="sxs-lookup"><span data-stu-id="df3b2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df3b2-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="df3b2-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="df3b2-124">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df3b2-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df3b2-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="df3b2-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
