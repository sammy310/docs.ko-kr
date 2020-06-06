---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855074"
---
# \<persistableType>
<span data-ttu-id="a7c5b-101">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c5b-101">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="a7c5b-102">구문</span><span class="sxs-lookup"><span data-stu-id="a7c5b-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="a7c5b-103">Type</span><span class="sxs-lookup"><span data-stu-id="a7c5b-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7c5b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a7c5b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="a7c5b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c5b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7c5b-106">특성</span><span class="sxs-lookup"><span data-stu-id="a7c5b-106">Attributes</span></span>  
  
|<span data-ttu-id="a7c5b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="a7c5b-107">Attribute</span></span>|<span data-ttu-id="a7c5b-108">Description</span><span class="sxs-lookup"><span data-stu-id="a7c5b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7c5b-109">id</span><span class="sxs-lookup"><span data-stu-id="a7c5b-109">id</span></span>|<span data-ttu-id="a7c5b-110">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c5b-110">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="a7c5b-111">name</span><span class="sxs-lookup"><span data-stu-id="a7c5b-111">name</span></span>|<span data-ttu-id="a7c5b-112">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c5b-112">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7c5b-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a7c5b-113">Child Elements</span></span>  
 <span data-ttu-id="a7c5b-114">None</span><span class="sxs-lookup"><span data-stu-id="a7c5b-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7c5b-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a7c5b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a7c5b-116">요소</span><span class="sxs-lookup"><span data-stu-id="a7c5b-116">Element</span></span>|<span data-ttu-id="a7c5b-117">Description</span><span class="sxs-lookup"><span data-stu-id="a7c5b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="a7c5b-118">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c5b-118">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7c5b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7c5b-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="a7c5b-120">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="a7c5b-120">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a7c5b-121">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="a7c5b-121">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
