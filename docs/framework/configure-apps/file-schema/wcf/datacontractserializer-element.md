---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400447"
---
# <a name="datacontractserializer"></a><span data-ttu-id="735a9-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="735a9-101">\<dataContractSerializer></span></span>
<span data-ttu-id="735a9-102"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="735a9-103">이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="735a9-104">하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
<span data-ttu-id="735a9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="735a9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="735a9-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="735a9-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="735a9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="735a9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="735a9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="735a9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="735a9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="735a9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="735a9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="735a9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735a9-111">구문</span><span class="sxs-lookup"><span data-stu-id="735a9-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="735a9-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="735a9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="735a9-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="735a9-114">특성</span><span class="sxs-lookup"><span data-stu-id="735a9-114">Attributes</span></span>  
  
|<span data-ttu-id="735a9-115">요소</span><span class="sxs-lookup"><span data-stu-id="735a9-115">Element</span></span>|<span data-ttu-id="735a9-116">Description</span><span class="sxs-lookup"><span data-stu-id="735a9-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="735a9-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="735a9-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="735a9-118">엔드포인트가 serialize되거나 deserialize될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="735a9-119">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="735a9-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="735a9-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="735a9-121">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="735a9-122">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="735a9-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="735a9-123">Child Elements</span></span>  
 <span data-ttu-id="735a9-124">없음</span><span class="sxs-lookup"><span data-stu-id="735a9-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="735a9-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="735a9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="735a9-126">요소</span><span class="sxs-lookup"><span data-stu-id="735a9-126">Element</span></span>|<span data-ttu-id="735a9-127">설명</span><span class="sxs-lookup"><span data-stu-id="735a9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="735a9-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="735a9-128">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="735a9-129">서비스의 동작에 대한 설정 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="735a9-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="735a9-130">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="735a9-131"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="735a9-132">설명</span><span class="sxs-lookup"><span data-stu-id="735a9-132">Remarks</span></span>  
 <span data-ttu-id="735a9-133">이 항목의 소개에 명시 된 대로 \<X509Extension > 요소가 발생 하는 두 번째 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="735a9-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="735a9-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="735a9-134">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="735a9-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="735a9-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="735a9-136">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="735a9-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735a9-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="735a9-137">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="735a9-138">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="735a9-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="735a9-139">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="735a9-139">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
