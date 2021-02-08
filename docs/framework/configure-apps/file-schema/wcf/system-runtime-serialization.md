---
description: 자세한 내용은 <>을 (를) 확인 하세요.
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: cf1d95c8650e4b6979d4f34b0bed1fa395911f2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786631"
---
# \<system.runtime.serialization>

<span data-ttu-id="50321-103"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="50321-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="50321-104">구문</span><span class="sxs-lookup"><span data-stu-id="50321-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50321-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="50321-105">Attributes and Elements</span></span>  

 <span data-ttu-id="50321-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50321-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50321-107">특성</span><span class="sxs-lookup"><span data-stu-id="50321-107">Attributes</span></span>  

 <span data-ttu-id="50321-108">없음</span><span class="sxs-lookup"><span data-stu-id="50321-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50321-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="50321-109">Child Elements</span></span>  
  
|<span data-ttu-id="50321-110">요소</span><span class="sxs-lookup"><span data-stu-id="50321-110">Element</span></span>|<span data-ttu-id="50321-111">설명</span><span class="sxs-lookup"><span data-stu-id="50321-111">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="50321-112">deserialization 시 사용할 알려진 형식을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50321-112">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50321-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="50321-113">Parent Elements</span></span>  
  
|<span data-ttu-id="50321-114">요소</span><span class="sxs-lookup"><span data-stu-id="50321-114">Element</span></span>|<span data-ttu-id="50321-115">설명</span><span class="sxs-lookup"><span data-stu-id="50321-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50321-116">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="50321-116">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="50321-117">구성의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="50321-117">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50321-118">참조</span><span class="sxs-lookup"><span data-stu-id="50321-118">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="50321-119">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="50321-119">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="50321-120">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="50321-120">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
