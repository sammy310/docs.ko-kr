---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: b67f51e634d1294830690dad8c8cffb1fc9a6cd2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399459"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="8c49c-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="8c49c-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="8c49c-103"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49c-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="8c49c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c49c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c49c-105">&nbsp;&nbsp; **\<>를 직렬화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c49c-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c49c-106">구문</span><span class="sxs-lookup"><span data-stu-id="8c49c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c49c-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c49c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8c49c-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c49c-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c49c-109">특성</span><span class="sxs-lookup"><span data-stu-id="8c49c-109">Attributes</span></span>  
 <span data-ttu-id="8c49c-110">없음</span><span class="sxs-lookup"><span data-stu-id="8c49c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c49c-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c49c-111">Child Elements</span></span>  
  
|<span data-ttu-id="8c49c-112">요소</span><span class="sxs-lookup"><span data-stu-id="8c49c-112">Element</span></span>|<span data-ttu-id="8c49c-113">설명</span><span class="sxs-lookup"><span data-stu-id="8c49c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c49c-114">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="8c49c-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="8c49c-115">deserialization 시 사용할 알려진 형식을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c49c-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c49c-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c49c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8c49c-117">요소</span><span class="sxs-lookup"><span data-stu-id="8c49c-117">Element</span></span>|<span data-ttu-id="8c49c-118">설명</span><span class="sxs-lookup"><span data-stu-id="8c49c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c49c-119">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="8c49c-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="8c49c-120">구성의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c49c-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c49c-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="8c49c-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="8c49c-122">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="8c49c-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="8c49c-123">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="8c49c-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
 