---
title: <namespaceTable>의 <add>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7d055d4933f1ad625d6842f91a140f668c05c64e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204998"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="7c511-102">\<namespaceTable>의 \<add></span><span class="sxs-lookup"><span data-stu-id="7c511-102">\<add> of \<namespaceTable></span></span>

<span data-ttu-id="7c511-103">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c511-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7c511-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c511-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c511-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7c511-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7c511-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c511-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c511-107">특성</span><span class="sxs-lookup"><span data-stu-id="7c511-107">Attributes</span></span>  
  
|<span data-ttu-id="7c511-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7c511-108">Attribute</span></span>|<span data-ttu-id="7c511-109">설명</span><span class="sxs-lookup"><span data-stu-id="7c511-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c511-110">namespace</span><span class="sxs-lookup"><span data-stu-id="7c511-110">namespace</span></span>|<span data-ttu-id="7c511-111">네임스페이스를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7c511-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="7c511-112">접두사</span><span class="sxs-lookup"><span data-stu-id="7c511-112">prefix</span></span>|<span data-ttu-id="7c511-113">이 네임스페이스에 대한 접두사를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7c511-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c511-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7c511-114">Child Elements</span></span>  

 <span data-ttu-id="7c511-115">없음</span><span class="sxs-lookup"><span data-stu-id="7c511-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c511-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7c511-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7c511-117">요소</span><span class="sxs-lookup"><span data-stu-id="7c511-117">Element</span></span>|<span data-ttu-id="7c511-118">설명</span><span class="sxs-lookup"><span data-stu-id="7c511-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="7c511-119">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c511-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c511-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c511-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
