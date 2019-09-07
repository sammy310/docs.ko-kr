---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400441"
---
# <a name="datacontractserializer"></a><span data-ttu-id="3982e-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3982e-102">dataContractSerializer</span></span>
<span data-ttu-id="3982e-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="3982e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3982e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3982e-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3982e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3982e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3982e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3982e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3982e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="3982e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3982e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="3982e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="3982e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3982e-110">구문</span><span class="sxs-lookup"><span data-stu-id="3982e-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3982e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3982e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3982e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3982e-113">특성</span><span class="sxs-lookup"><span data-stu-id="3982e-113">Attributes</span></span>  
  
|<span data-ttu-id="3982e-114">요소</span><span class="sxs-lookup"><span data-stu-id="3982e-114">Element</span></span>|<span data-ttu-id="3982e-115">설명</span><span class="sxs-lookup"><span data-stu-id="3982e-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3982e-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="3982e-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="3982e-117">엔드포인트가 serialize되거나 deserialize될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="3982e-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="3982e-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="3982e-119">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3982e-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3982e-120">Child Elements</span></span>  
 <span data-ttu-id="3982e-121">없음</span><span class="sxs-lookup"><span data-stu-id="3982e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3982e-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3982e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3982e-123">요소</span><span class="sxs-lookup"><span data-stu-id="3982e-123">Element</span></span>|<span data-ttu-id="3982e-124">설명</span><span class="sxs-lookup"><span data-stu-id="3982e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3982e-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3982e-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3982e-126">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3982e-127">설명</span><span class="sxs-lookup"><span data-stu-id="3982e-127">Remarks</span></span>  
 <span data-ttu-id="3982e-128">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3982e-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3982e-129">`<dataContractSerializer>` 동작 요소(있는 경우)는 항상 구성 파일에서 `<enableWebScript>` 동작 요소 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="3982e-130">그렇지 않으면 결과 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3982e-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3982e-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="3982e-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="3982e-132">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="3982e-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3982e-133">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="3982e-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
