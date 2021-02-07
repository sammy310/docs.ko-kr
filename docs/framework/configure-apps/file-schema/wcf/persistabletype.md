---
description: 다음에 대해 자세히 알아보세요. <persistableType>
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: eadbb951d751dd88ce974edc8d5b343a1469b758
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683634"
---
# \<persistableType>

<span data-ttu-id="52dc9-102">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52dc9-102">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="52dc9-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="52dc9-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="52dc9-104">Type</span><span class="sxs-lookup"><span data-stu-id="52dc9-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52dc9-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52dc9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="52dc9-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52dc9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52dc9-107">특성</span><span class="sxs-lookup"><span data-stu-id="52dc9-107">Attributes</span></span>  
  
|<span data-ttu-id="52dc9-108">attribute</span><span class="sxs-lookup"><span data-stu-id="52dc9-108">Attribute</span></span>|<span data-ttu-id="52dc9-109">Description</span><span class="sxs-lookup"><span data-stu-id="52dc9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52dc9-110">id</span><span class="sxs-lookup"><span data-stu-id="52dc9-110">id</span></span>|<span data-ttu-id="52dc9-111">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52dc9-111">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="52dc9-112">name</span><span class="sxs-lookup"><span data-stu-id="52dc9-112">name</span></span>|<span data-ttu-id="52dc9-113">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52dc9-113">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52dc9-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52dc9-114">Child Elements</span></span>  

 <span data-ttu-id="52dc9-115">없음</span><span class="sxs-lookup"><span data-stu-id="52dc9-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52dc9-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52dc9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="52dc9-117">요소</span><span class="sxs-lookup"><span data-stu-id="52dc9-117">Element</span></span>|<span data-ttu-id="52dc9-118">설명</span><span class="sxs-lookup"><span data-stu-id="52dc9-118">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="52dc9-119">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="52dc9-119">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52dc9-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52dc9-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="52dc9-121">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="52dc9-121">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="52dc9-122">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="52dc9-122">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
