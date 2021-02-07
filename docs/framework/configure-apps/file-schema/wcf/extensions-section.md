---
description: '자세히 알아보기: <extensions> 섹션'
title: <extensions> 여기서
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 65b1de76155b1e3fbd8e5f14a5f4a1cb8c180ec1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664693"
---
# <a name="extensions-section"></a><span data-ttu-id="bd14d-103">\<extensions> 여기서</span><span class="sxs-lookup"><span data-stu-id="bd14d-103">\<extensions> section</span></span>

<span data-ttu-id="bd14d-104">이 구성 섹션에는 사용자 정의 바인딩, 동작 및 확장명의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-104">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="bd14d-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd14d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd14d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bd14d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bd14d-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd14d-108">특성</span><span class="sxs-lookup"><span data-stu-id="bd14d-108">Attributes</span></span>  

 <span data-ttu-id="bd14d-109">없음</span><span class="sxs-lookup"><span data-stu-id="bd14d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd14d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bd14d-110">Child Elements</span></span>  
  
|<span data-ttu-id="bd14d-111">요소</span><span class="sxs-lookup"><span data-stu-id="bd14d-111">Element</span></span>|<span data-ttu-id="bd14d-112">설명</span><span class="sxs-lookup"><span data-stu-id="bd14d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="bd14d-113">이 섹션에는 서비스 또는 엔드포인트 동작을 사용자 지정할 수 있도록 하는 동작 확장을 지정하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-113">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="bd14d-114">이 섹션은 시스템 또는 애플리케이션 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-114">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="bd14d-115">이 섹션에는 바인딩을 사용자 지정할 수 있도록 하는 바인딩 확장을 지정하는 자식 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-115">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="bd14d-116">이 섹션에는 표준 엔드포인트를 등록하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-116">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd14d-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bd14d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bd14d-118">요소</span><span class="sxs-lookup"><span data-stu-id="bd14d-118">Element</span></span>|<span data-ttu-id="bd14d-119">설명</span><span class="sxs-lookup"><span data-stu-id="bd14d-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd14d-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bd14d-120">system.ServiceModel</span></span>|<span data-ttu-id="bd14d-121">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd14d-121">The root element of all WCF configuration elements.</span></span>|
