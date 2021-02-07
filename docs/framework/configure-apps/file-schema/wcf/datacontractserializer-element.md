---
description: 다음에 대해 자세히 알아보세요. <dataContractSerializer>
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 0705a40f55d76ef46a7debcd4ecfb5235c7c0d21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754435"
---
# \<dataContractSerializer>

<span data-ttu-id="78ecf-102"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="78ecf-103">이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="78ecf-104">하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="78ecf-105">구문</span><span class="sxs-lookup"><span data-stu-id="78ecf-105">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78ecf-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78ecf-106">Attributes and Elements</span></span>  

 <span data-ttu-id="78ecf-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78ecf-108">특성</span><span class="sxs-lookup"><span data-stu-id="78ecf-108">Attributes</span></span>  
  
|<span data-ttu-id="78ecf-109">요소</span><span class="sxs-lookup"><span data-stu-id="78ecf-109">Element</span></span>|<span data-ttu-id="78ecf-110">설명</span><span class="sxs-lookup"><span data-stu-id="78ecf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78ecf-111">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="78ecf-111">ignoreExtensionDataObject</span></span>|<span data-ttu-id="78ecf-112">엔드포인트가 직렬화되거나 역직렬화될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-112">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="78ecf-113">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-113">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="78ecf-114">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="78ecf-114">maxItemsInObjectGraph</span></span>|<span data-ttu-id="78ecf-115">직렬화 또는 역직렬화할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-115">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="78ecf-116">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-116">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78ecf-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78ecf-117">Child Elements</span></span>  

 <span data-ttu-id="78ecf-118">없음</span><span class="sxs-lookup"><span data-stu-id="78ecf-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78ecf-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78ecf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="78ecf-120">요소</span><span class="sxs-lookup"><span data-stu-id="78ecf-120">Element</span></span>|<span data-ttu-id="78ecf-121">설명</span><span class="sxs-lookup"><span data-stu-id="78ecf-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="78ecf-122">서비스의 동작에 대한 설정 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-122">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="78ecf-123"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecf-123">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78ecf-124">설명</span><span class="sxs-lookup"><span data-stu-id="78ecf-124">Remarks</span></span>  

 <span data-ttu-id="78ecf-125">이 항목의 소개에 명시 된 대로이 항목은 요소가 발생 하는 두 번째 계층 구조입니다 \<X509Extension> .</span><span class="sxs-lookup"><span data-stu-id="78ecf-125">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="78ecf-126">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78ecf-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ecf-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78ecf-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="78ecf-128">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="78ecf-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="78ecf-129">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="78ecf-129">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
