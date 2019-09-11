---
title: <extensions>여기서
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855362"
---
# <a name="extensions-section"></a><span data-ttu-id="b6d1b-102">\<확장 > 섹션</span><span class="sxs-lookup"><span data-stu-id="b6d1b-102">\<extensions> section</span></span>
<span data-ttu-id="b6d1b-103">이 구성 섹션에는 사용자 정의 바인딩, 동작 및 확장명의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="b6d1b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6d1b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6d1b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b6d1b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b6d1b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<확장 >**</span><span class="sxs-lookup"><span data-stu-id="b6d1b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d1b-107">구문</span><span class="sxs-lookup"><span data-stu-id="b6d1b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6d1b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b6d1b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b6d1b-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6d1b-110">특성</span><span class="sxs-lookup"><span data-stu-id="b6d1b-110">Attributes</span></span>  
 <span data-ttu-id="b6d1b-111">없음</span><span class="sxs-lookup"><span data-stu-id="b6d1b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6d1b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b6d1b-112">Child Elements</span></span>  
  
|<span data-ttu-id="b6d1b-113">요소</span><span class="sxs-lookup"><span data-stu-id="b6d1b-113">Element</span></span>|<span data-ttu-id="b6d1b-114">설명</span><span class="sxs-lookup"><span data-stu-id="b6d1b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6d1b-115">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="b6d1b-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="b6d1b-116">이 섹션에는 서비스 또는 엔드포인트 동작을 사용자 지정할 수 있도록 하는 동작 확장을 지정하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="b6d1b-117">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="b6d1b-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="b6d1b-118">이 섹션은 시스템 또는 애플리케이션 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="b6d1b-119">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="b6d1b-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="b6d1b-120">이 섹션에는 바인딩을 사용자 지정할 수 있도록 하는 바인딩 확장을 지정하는 자식 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="b6d1b-121">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="b6d1b-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="b6d1b-122">이 섹션에는 표준 엔드포인트를 등록하는 자식 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6d1b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b6d1b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b6d1b-124">요소</span><span class="sxs-lookup"><span data-stu-id="b6d1b-124">Element</span></span>|<span data-ttu-id="b6d1b-125">Description</span><span class="sxs-lookup"><span data-stu-id="b6d1b-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6d1b-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b6d1b-126">system.ServiceModel</span></span>|<span data-ttu-id="b6d1b-127">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d1b-127">The root element of all WCF configuration elements.</span></span>|
