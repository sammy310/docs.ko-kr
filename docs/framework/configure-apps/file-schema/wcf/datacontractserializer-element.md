---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 2a994a8ba97d4c65fdaba5a85e779dd9935e3074
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195037"
---
# \<dataContractSerializer>

<span data-ttu-id="9d833-101"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="9d833-102">이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="9d833-103">하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="9d833-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d833-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d833-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9d833-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9d833-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d833-107">특성</span><span class="sxs-lookup"><span data-stu-id="9d833-107">Attributes</span></span>  
  
|<span data-ttu-id="9d833-108">요소</span><span class="sxs-lookup"><span data-stu-id="9d833-108">Element</span></span>|<span data-ttu-id="9d833-109">설명</span><span class="sxs-lookup"><span data-stu-id="9d833-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d833-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="9d833-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="9d833-111">엔드포인트가 직렬화되거나 역직렬화될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="9d833-112">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="9d833-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="9d833-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="9d833-114">직렬화 또는 역직렬화할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="9d833-115">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d833-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9d833-116">Child Elements</span></span>  

 <span data-ttu-id="9d833-117">없음</span><span class="sxs-lookup"><span data-stu-id="9d833-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d833-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9d833-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9d833-119">요소</span><span class="sxs-lookup"><span data-stu-id="9d833-119">Element</span></span>|<span data-ttu-id="9d833-120">설명</span><span class="sxs-lookup"><span data-stu-id="9d833-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="9d833-121">서비스의 동작에 대한 설정 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="9d833-122"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9d833-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d833-123">설명</span><span class="sxs-lookup"><span data-stu-id="9d833-123">Remarks</span></span>  

 <span data-ttu-id="9d833-124">이 항목의 소개에 명시 된 대로이 항목은 요소가 발생 하는 두 번째 계층 구조입니다 \<X509Extension> .</span><span class="sxs-lookup"><span data-stu-id="9d833-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="9d833-125">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d833-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d833-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d833-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="9d833-127">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="9d833-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="9d833-128">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="9d833-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
