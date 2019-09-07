---
title: <dataContractSerializer><의 >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398086"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="8b1af-102">\<dataContractSerializer > \<></span><span class="sxs-lookup"><span data-stu-id="8b1af-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="8b1af-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="8b1af-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8b1af-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8b1af-105">&nbsp;&nbsp;[ **\<>를 직렬화 합니다.** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="8b1af-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="8b1af-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="8b1af-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1af-107">구문</span><span class="sxs-lookup"><span data-stu-id="8b1af-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b1af-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8b1af-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8b1af-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b1af-110">특성</span><span class="sxs-lookup"><span data-stu-id="8b1af-110">Attributes</span></span>  
  
|<span data-ttu-id="8b1af-111">요소</span><span class="sxs-lookup"><span data-stu-id="8b1af-111">Element</span></span>|<span data-ttu-id="8b1af-112">설명</span><span class="sxs-lookup"><span data-stu-id="8b1af-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b1af-113">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="8b1af-113">ignoreExtensionDataObject</span></span>|<span data-ttu-id="8b1af-114">엔드포인트가 serialize되거나 deserialize될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-114">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="8b1af-115">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-115">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="8b1af-116">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="8b1af-116">maxItemsInObjectGraph</span></span>|<span data-ttu-id="8b1af-117">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-117">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="8b1af-118">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-118">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b1af-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8b1af-119">Child Elements</span></span>  
  
|<span data-ttu-id="8b1af-120">요소</span><span class="sxs-lookup"><span data-stu-id="8b1af-120">Element</span></span>|<span data-ttu-id="8b1af-121">설명</span><span class="sxs-lookup"><span data-stu-id="8b1af-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b1af-122">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="8b1af-122">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="8b1af-123">deserialize할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-123">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="8b1af-124">데이터 계약 및 알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b1af-124">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b1af-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8b1af-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8b1af-126">요소</span><span class="sxs-lookup"><span data-stu-id="8b1af-126">Element</span></span>|<span data-ttu-id="8b1af-127">설명</span><span class="sxs-lookup"><span data-stu-id="8b1af-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b1af-128">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="8b1af-128">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="8b1af-129"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1af-129">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b1af-130">설명</span><span class="sxs-lookup"><span data-stu-id="8b1af-130">Remarks</span></span>  
 <span data-ttu-id="8b1af-131">알려진 형식에 대 한 자세한 내용은 및 <xref:System.Runtime.Serialization.DataContractSerializer> [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b1af-131">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1af-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b1af-132">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="8b1af-133">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="8b1af-133">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
