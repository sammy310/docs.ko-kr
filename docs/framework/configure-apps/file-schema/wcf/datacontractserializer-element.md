---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: b635f03d1e4a6628a76d678f7366482717276376
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116391"
---
# <a name="datacontractserializer"></a><span data-ttu-id="e9492-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="e9492-101">\<dataContractSerializer></span></span>
<span data-ttu-id="e9492-102"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="e9492-103">이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="e9492-104">하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="e9492-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e9492-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9492-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e9492-106">\<behaviors></span></span>  
<span data-ttu-id="e9492-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e9492-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="e9492-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e9492-108">\<behavior></span></span>  
<span data-ttu-id="e9492-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="e9492-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9492-110">구문</span><span class="sxs-lookup"><span data-stu-id="e9492-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9492-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e9492-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9492-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9492-113">특성</span><span class="sxs-lookup"><span data-stu-id="e9492-113">Attributes</span></span>  
  
|<span data-ttu-id="e9492-114">요소</span><span class="sxs-lookup"><span data-stu-id="e9492-114">Element</span></span>|<span data-ttu-id="e9492-115">설명</span><span class="sxs-lookup"><span data-stu-id="e9492-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9492-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="e9492-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="e9492-117">엔드포인트가 serialize되거나 deserialize될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="e9492-118">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="e9492-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="e9492-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="e9492-120">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="e9492-121">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9492-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9492-122">Child Elements</span></span>  
 <span data-ttu-id="e9492-123">없음</span><span class="sxs-lookup"><span data-stu-id="e9492-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9492-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9492-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e9492-125">요소</span><span class="sxs-lookup"><span data-stu-id="e9492-125">Element</span></span>|<span data-ttu-id="e9492-126">설명</span><span class="sxs-lookup"><span data-stu-id="e9492-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9492-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e9492-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="e9492-128">서비스의 동작에 대한 설정 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="e9492-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="e9492-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="e9492-130"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9492-131">설명</span><span class="sxs-lookup"><span data-stu-id="e9492-131">Remarks</span></span>  
 <span data-ttu-id="e9492-132">이는 두 번째 계층 구조는이 항목의 소개에서 설명 했 듯이 \<X509Extension > 요소가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9492-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="e9492-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="e9492-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="e9492-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="e9492-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="e9492-135">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9492-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9492-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9492-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="e9492-137">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="e9492-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="e9492-138">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="e9492-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
