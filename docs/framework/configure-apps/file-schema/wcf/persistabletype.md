---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083740"
---
# <a name="persistabletype"></a><span data-ttu-id="b5184-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="b5184-101">\<persistableType></span></span>
<span data-ttu-id="b5184-102">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5184-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="b5184-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b5184-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b5184-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="b5184-104">\<comContracts></span></span>  
<span data-ttu-id="b5184-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="b5184-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5184-106">구문</span><span class="sxs-lookup"><span data-stu-id="b5184-106">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="b5184-107">형식</span><span class="sxs-lookup"><span data-stu-id="b5184-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5184-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b5184-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b5184-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5184-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5184-110">특성</span><span class="sxs-lookup"><span data-stu-id="b5184-110">Attributes</span></span>  
  
|<span data-ttu-id="b5184-111">특성</span><span class="sxs-lookup"><span data-stu-id="b5184-111">Attribute</span></span>|<span data-ttu-id="b5184-112">설명</span><span class="sxs-lookup"><span data-stu-id="b5184-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5184-113">ID</span><span class="sxs-lookup"><span data-stu-id="b5184-113">id</span></span>|<span data-ttu-id="b5184-114">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5184-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="b5184-115">name</span><span class="sxs-lookup"><span data-stu-id="b5184-115">name</span></span>|<span data-ttu-id="b5184-116">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5184-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5184-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b5184-117">Child Elements</span></span>  
 <span data-ttu-id="b5184-118">없음</span><span class="sxs-lookup"><span data-stu-id="b5184-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5184-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b5184-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b5184-120">요소</span><span class="sxs-lookup"><span data-stu-id="b5184-120">Element</span></span>|<span data-ttu-id="b5184-121">설명</span><span class="sxs-lookup"><span data-stu-id="b5184-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5184-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="b5184-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="b5184-123">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b5184-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5184-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="b5184-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="b5184-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="b5184-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="b5184-126">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="b5184-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="b5184-127">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b5184-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
