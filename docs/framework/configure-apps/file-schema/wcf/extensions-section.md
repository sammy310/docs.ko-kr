---
title: <extensions>여기서
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 4c8b5fe6eef1863ee3f02cb761a3aac61406e446
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918965"
---
# <a name="extensions-section"></a><span data-ttu-id="fd400-102">\<확장 > 섹션</span><span class="sxs-lookup"><span data-stu-id="fd400-102">\<extensions> section</span></span>
<span data-ttu-id="fd400-103">이 구성 섹션에는 사용자 정의 바인딩, 동작 및 확장명의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="fd400-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd400-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd400-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd400-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd400-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd400-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fd400-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd400-108">특성</span><span class="sxs-lookup"><span data-stu-id="fd400-108">Attributes</span></span>  
 <span data-ttu-id="fd400-109">없음</span><span class="sxs-lookup"><span data-stu-id="fd400-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd400-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd400-110">Child Elements</span></span>  
  
|<span data-ttu-id="fd400-111">요소</span><span class="sxs-lookup"><span data-stu-id="fd400-111">Element</span></span>|<span data-ttu-id="fd400-112">Description</span><span class="sxs-lookup"><span data-stu-id="fd400-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd400-113">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="fd400-113">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="fd400-114">이 섹션에는 서비스 또는 엔드포인트 동작을 사용자 지정할 수 있도록 하는 동작 확장을 지정하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="fd400-115">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="fd400-115">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="fd400-116">이 섹션은 시스템 또는 애플리케이션 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="fd400-117">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="fd400-117">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="fd400-118">이 섹션에는 바인딩을 사용자 지정할 수 있도록 하는 바인딩 확장을 지정하는 자식 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="fd400-119">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="fd400-119">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="fd400-120">이 섹션에는 표준 엔드포인트를 등록하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd400-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd400-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fd400-122">요소</span><span class="sxs-lookup"><span data-stu-id="fd400-122">Element</span></span>|<span data-ttu-id="fd400-123">설명</span><span class="sxs-lookup"><span data-stu-id="fd400-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd400-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fd400-124">system.ServiceModel</span></span>|<span data-ttu-id="fd400-125">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fd400-125">The root element of all WCF configuration elements.</span></span>|
