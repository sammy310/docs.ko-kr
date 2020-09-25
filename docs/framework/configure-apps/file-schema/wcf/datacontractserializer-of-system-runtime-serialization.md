---
title: <dataContractSerializer> <의>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: a8d379e7a37bca0cdb58836a6afdf814320e2411
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190191"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="55607-102">\<system.runtime.serialization>의 \<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="55607-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>

<span data-ttu-id="55607-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55607-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="55607-104">구문</span><span class="sxs-lookup"><span data-stu-id="55607-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55607-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="55607-105">Attributes and Elements</span></span>  

 <span data-ttu-id="55607-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55607-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55607-107">특성</span><span class="sxs-lookup"><span data-stu-id="55607-107">Attributes</span></span>  
  
|<span data-ttu-id="55607-108">요소</span><span class="sxs-lookup"><span data-stu-id="55607-108">Element</span></span>|<span data-ttu-id="55607-109">설명</span><span class="sxs-lookup"><span data-stu-id="55607-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55607-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="55607-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="55607-111">엔드포인트가 직렬화되거나 역직렬화될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55607-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="55607-112">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55607-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="55607-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="55607-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="55607-114">직렬화 또는 역직렬화할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="55607-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="55607-115">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="55607-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55607-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="55607-116">Child Elements</span></span>  
  
|<span data-ttu-id="55607-117">요소</span><span class="sxs-lookup"><span data-stu-id="55607-117">Element</span></span>|<span data-ttu-id="55607-118">설명</span><span class="sxs-lookup"><span data-stu-id="55607-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="55607-119">역직렬화할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55607-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="55607-120">데이터 계약 및 알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55607-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55607-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="55607-121">Parent Elements</span></span>  
  
|<span data-ttu-id="55607-122">요소</span><span class="sxs-lookup"><span data-stu-id="55607-122">Element</span></span>|<span data-ttu-id="55607-123">설명</span><span class="sxs-lookup"><span data-stu-id="55607-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="55607-124"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55607-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55607-125">설명</span><span class="sxs-lookup"><span data-stu-id="55607-125">Remarks</span></span>  

 <span data-ttu-id="55607-126">알려진 형식에 대 한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 및 [데이터 계약 알려진 형식](../../../wcf/feature-details/data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55607-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55607-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55607-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="55607-128">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="55607-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
