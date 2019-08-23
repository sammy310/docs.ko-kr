---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 7e440810fee1dddb7025d1385b1edb4838d98a39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925918"
---
# <a name="datacontractserializer"></a><span data-ttu-id="65066-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="65066-101">\<dataContractSerializer></span></span>
<span data-ttu-id="65066-102"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="65066-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="65066-103">이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="65066-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="65066-104">하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="65066-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="65066-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="65066-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="65066-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="65066-106">\<behaviors></span></span>  
<span data-ttu-id="65066-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="65066-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="65066-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="65066-108">\<behavior></span></span>  
<span data-ttu-id="65066-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="65066-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65066-110">구문</span><span class="sxs-lookup"><span data-stu-id="65066-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65066-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="65066-111">Attributes and Elements</span></span>  
 <span data-ttu-id="65066-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65066-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65066-113">특성</span><span class="sxs-lookup"><span data-stu-id="65066-113">Attributes</span></span>  
  
|<span data-ttu-id="65066-114">요소</span><span class="sxs-lookup"><span data-stu-id="65066-114">Element</span></span>|<span data-ttu-id="65066-115">Description</span><span class="sxs-lookup"><span data-stu-id="65066-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65066-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="65066-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="65066-117">엔드포인트가 serialize되거나 deserialize될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="65066-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="65066-118">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65066-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="65066-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="65066-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="65066-120">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="65066-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="65066-121">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="65066-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65066-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="65066-122">Child Elements</span></span>  
 <span data-ttu-id="65066-123">없음</span><span class="sxs-lookup"><span data-stu-id="65066-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65066-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="65066-124">Parent Elements</span></span>  
  
|<span data-ttu-id="65066-125">요소</span><span class="sxs-lookup"><span data-stu-id="65066-125">Element</span></span>|<span data-ttu-id="65066-126">설명</span><span class="sxs-lookup"><span data-stu-id="65066-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65066-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="65066-127">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="65066-128">서비스의 동작에 대한 설정 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="65066-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="65066-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="65066-129">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="65066-130"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="65066-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65066-131">설명</span><span class="sxs-lookup"><span data-stu-id="65066-131">Remarks</span></span>  
 <span data-ttu-id="65066-132">이 항목의 소개에 명시 된 대로 \<X509Extension > 요소가 발생 하는 두 번째 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="65066-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="65066-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="65066-133">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="65066-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="65066-134">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="65066-135">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65066-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65066-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="65066-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="65066-137">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="65066-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="65066-138">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="65066-138">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
