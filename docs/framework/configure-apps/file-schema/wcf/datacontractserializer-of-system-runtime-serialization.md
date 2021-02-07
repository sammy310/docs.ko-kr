---
description: '다음에 대 한 자세한 정보: <dataContractSerializer> <>'
title: <dataContractSerializer> <의>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 3755005782ea773344326d211b9f8f115a97f2ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754422"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="bad9a-103">\<system.runtime.serialization>의 \<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="bad9a-103">\<dataContractSerializer> of \<system.runtime.serialization></span></span>

<span data-ttu-id="bad9a-104"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-104">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="bad9a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bad9a-105">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bad9a-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bad9a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bad9a-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bad9a-108">특성</span><span class="sxs-lookup"><span data-stu-id="bad9a-108">Attributes</span></span>  
  
|<span data-ttu-id="bad9a-109">요소</span><span class="sxs-lookup"><span data-stu-id="bad9a-109">Element</span></span>|<span data-ttu-id="bad9a-110">설명</span><span class="sxs-lookup"><span data-stu-id="bad9a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bad9a-111">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="bad9a-111">ignoreExtensionDataObject</span></span>|<span data-ttu-id="bad9a-112">엔드포인트가 직렬화되거나 역직렬화될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-112">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="bad9a-113">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-113">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="bad9a-114">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="bad9a-114">maxItemsInObjectGraph</span></span>|<span data-ttu-id="bad9a-115">직렬화 또는 역직렬화할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-115">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="bad9a-116">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-116">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bad9a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bad9a-117">Child Elements</span></span>  
  
|<span data-ttu-id="bad9a-118">요소</span><span class="sxs-lookup"><span data-stu-id="bad9a-118">Element</span></span>|<span data-ttu-id="bad9a-119">설명</span><span class="sxs-lookup"><span data-stu-id="bad9a-119">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="bad9a-120">역직렬화할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-120">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="bad9a-121">데이터 계약 및 알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bad9a-121">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bad9a-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bad9a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bad9a-123">요소</span><span class="sxs-lookup"><span data-stu-id="bad9a-123">Element</span></span>|<span data-ttu-id="bad9a-124">설명</span><span class="sxs-lookup"><span data-stu-id="bad9a-124">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="bad9a-125"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9a-125">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bad9a-126">설명</span><span class="sxs-lookup"><span data-stu-id="bad9a-126">Remarks</span></span>  

 <span data-ttu-id="bad9a-127">알려진 형식에 대 한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 및 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bad9a-127">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad9a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bad9a-128">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="bad9a-129">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="bad9a-129">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
