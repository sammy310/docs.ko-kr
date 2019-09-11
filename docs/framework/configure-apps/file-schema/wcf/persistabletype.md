---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855074"
---
# <a name="persistabletype"></a><span data-ttu-id="03bf8-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="03bf8-101">\<persistableType></span></span>
<span data-ttu-id="03bf8-102">모든 지속 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03bf8-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="03bf8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="03bf8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="03bf8-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="03bf8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="03bf8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="03bf8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="03bf8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="03bf8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="03bf8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<persistableTypes >** ](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="03bf8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="03bf8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistableType >**</span><span class="sxs-lookup"><span data-stu-id="03bf8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03bf8-109">구문</span><span class="sxs-lookup"><span data-stu-id="03bf8-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="03bf8-110">형식</span><span class="sxs-lookup"><span data-stu-id="03bf8-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03bf8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="03bf8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03bf8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03bf8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03bf8-113">특성</span><span class="sxs-lookup"><span data-stu-id="03bf8-113">Attributes</span></span>  
  
|<span data-ttu-id="03bf8-114">특성</span><span class="sxs-lookup"><span data-stu-id="03bf8-114">Attribute</span></span>|<span data-ttu-id="03bf8-115">설명</span><span class="sxs-lookup"><span data-stu-id="03bf8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03bf8-116">id</span><span class="sxs-lookup"><span data-stu-id="03bf8-116">id</span></span>|<span data-ttu-id="03bf8-117">지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03bf8-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="03bf8-118">name</span><span class="sxs-lookup"><span data-stu-id="03bf8-118">name</span></span>|<span data-ttu-id="03bf8-119">지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03bf8-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03bf8-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="03bf8-120">Child Elements</span></span>  
 <span data-ttu-id="03bf8-121">없음</span><span class="sxs-lookup"><span data-stu-id="03bf8-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03bf8-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="03bf8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="03bf8-123">요소</span><span class="sxs-lookup"><span data-stu-id="03bf8-123">Element</span></span>|<span data-ttu-id="03bf8-124">Description</span><span class="sxs-lookup"><span data-stu-id="03bf8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03bf8-125">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="03bf8-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="03bf8-126">`persistableType` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="03bf8-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03bf8-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="03bf8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="03bf8-128">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="03bf8-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="03bf8-129">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="03bf8-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="03bf8-130">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="03bf8-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
