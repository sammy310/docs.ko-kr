---
title: <extensions> 여기서
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: f3eb5d446291dfa6b7c8e0f1ee2b6a5cf53c2162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185784"
---
# <a name="extensions-section"></a><span data-ttu-id="bb0d6-102">\<extensions> 여기서</span><span class="sxs-lookup"><span data-stu-id="bb0d6-102">\<extensions> section</span></span>

<span data-ttu-id="bb0d6-103">이 구성 섹션에는 사용자 정의 바인딩, 동작 및 확장명의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="bb0d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb0d6-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb0d6-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bb0d6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bb0d6-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb0d6-107">특성</span><span class="sxs-lookup"><span data-stu-id="bb0d6-107">Attributes</span></span>  

 <span data-ttu-id="bb0d6-108">없음</span><span class="sxs-lookup"><span data-stu-id="bb0d6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb0d6-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bb0d6-109">Child Elements</span></span>  
  
|<span data-ttu-id="bb0d6-110">요소</span><span class="sxs-lookup"><span data-stu-id="bb0d6-110">Element</span></span>|<span data-ttu-id="bb0d6-111">설명</span><span class="sxs-lookup"><span data-stu-id="bb0d6-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="bb0d6-112">이 섹션에는 서비스 또는 엔드포인트 동작을 사용자 지정할 수 있도록 하는 동작 확장을 지정하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="bb0d6-113">이 섹션은 시스템 또는 애플리케이션 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="bb0d6-114">이 섹션에는 바인딩을 사용자 지정할 수 있도록 하는 바인딩 확장을 지정하는 자식 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="bb0d6-115">이 섹션에는 표준 엔드포인트를 등록하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb0d6-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bb0d6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bb0d6-117">요소</span><span class="sxs-lookup"><span data-stu-id="bb0d6-117">Element</span></span>|<span data-ttu-id="bb0d6-118">설명</span><span class="sxs-lookup"><span data-stu-id="bb0d6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb0d6-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bb0d6-119">system.ServiceModel</span></span>|<span data-ttu-id="bb0d6-120">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d6-120">The root element of all WCF configuration elements.</span></span>|
