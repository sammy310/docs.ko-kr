---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 84ced06691ce3b3c9c9573fc9d114335096a849d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157111"
---
# \<system.runtime.serialization>

<span data-ttu-id="2a445-102"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2a445-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="2a445-103">구문</span><span class="sxs-lookup"><span data-stu-id="2a445-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a445-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2a445-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2a445-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a445-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a445-106">특성</span><span class="sxs-lookup"><span data-stu-id="2a445-106">Attributes</span></span>  

 <span data-ttu-id="2a445-107">없음</span><span class="sxs-lookup"><span data-stu-id="2a445-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2a445-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2a445-108">Child Elements</span></span>  
  
|<span data-ttu-id="2a445-109">요소</span><span class="sxs-lookup"><span data-stu-id="2a445-109">Element</span></span>|<span data-ttu-id="2a445-110">설명</span><span class="sxs-lookup"><span data-stu-id="2a445-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="2a445-111">deserialization 시 사용할 알려진 형식을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a445-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a445-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2a445-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2a445-113">요소</span><span class="sxs-lookup"><span data-stu-id="2a445-113">Element</span></span>|<span data-ttu-id="2a445-114">설명</span><span class="sxs-lookup"><span data-stu-id="2a445-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a445-115">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="2a445-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="2a445-116">구성의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2a445-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a445-117">참조</span><span class="sxs-lookup"><span data-stu-id="2a445-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="2a445-118">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="2a445-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="2a445-119">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="2a445-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
