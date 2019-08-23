---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933828"
---
# <a name="persistabletype"></a><span data-ttu-id="f3b1a-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="f3b1a-101">\<persistableType></span></span>
<span data-ttu-id="f3b1a-102">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="f3b1a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f3b1a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3b1a-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="f3b1a-104">\<comContracts></span></span>  
<span data-ttu-id="f3b1a-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="f3b1a-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b1a-106">구문</span><span class="sxs-lookup"><span data-stu-id="f3b1a-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="f3b1a-107">형식</span><span class="sxs-lookup"><span data-stu-id="f3b1a-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3b1a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f3b1a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3b1a-110">특성</span><span class="sxs-lookup"><span data-stu-id="f3b1a-110">Attributes</span></span>  
  
|<span data-ttu-id="f3b1a-111">특성</span><span class="sxs-lookup"><span data-stu-id="f3b1a-111">Attribute</span></span>|<span data-ttu-id="f3b1a-112">설명</span><span class="sxs-lookup"><span data-stu-id="f3b1a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3b1a-113">id</span><span class="sxs-lookup"><span data-stu-id="f3b1a-113">id</span></span>|<span data-ttu-id="f3b1a-114">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="f3b1a-115">name</span><span class="sxs-lookup"><span data-stu-id="f3b1a-115">name</span></span>|<span data-ttu-id="f3b1a-116">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3b1a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-117">Child Elements</span></span>  
 <span data-ttu-id="f3b1a-118">없음</span><span class="sxs-lookup"><span data-stu-id="f3b1a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3b1a-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f3b1a-120">요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-120">Element</span></span>|<span data-ttu-id="f3b1a-121">Description</span><span class="sxs-lookup"><span data-stu-id="f3b1a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3b1a-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="f3b1a-122">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="f3b1a-123">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3b1a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="f3b1a-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="f3b1a-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="f3b1a-125">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="f3b1a-126">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="f3b1a-126">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="f3b1a-127">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="f3b1a-127">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
