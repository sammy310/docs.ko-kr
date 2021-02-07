---
description: '자세한 정보: dataContractSerializer'
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 5dee59ba97a1632c142179aee79058dd3ce8c349
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754409"
---
# <a name="datacontractserializer"></a><span data-ttu-id="5aa21-103">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="5aa21-103">dataContractSerializer</span></span>

<span data-ttu-id="5aa21-104"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-104">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="5aa21-105">구문</span><span class="sxs-lookup"><span data-stu-id="5aa21-105">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5aa21-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5aa21-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5aa21-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5aa21-108">특성</span><span class="sxs-lookup"><span data-stu-id="5aa21-108">Attributes</span></span>  
  
|<span data-ttu-id="5aa21-109">요소</span><span class="sxs-lookup"><span data-stu-id="5aa21-109">Element</span></span>|<span data-ttu-id="5aa21-110">설명</span><span class="sxs-lookup"><span data-stu-id="5aa21-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5aa21-111">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="5aa21-111">ignoreExtensionDataObject</span></span>|<span data-ttu-id="5aa21-112">엔드포인트가 직렬화되거나 역직렬화될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-112">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="5aa21-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="5aa21-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="5aa21-114">직렬화 또는 역직렬화할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5aa21-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5aa21-115">Child Elements</span></span>  

 <span data-ttu-id="5aa21-116">없음</span><span class="sxs-lookup"><span data-stu-id="5aa21-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5aa21-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5aa21-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5aa21-118">요소</span><span class="sxs-lookup"><span data-stu-id="5aa21-118">Element</span></span>|<span data-ttu-id="5aa21-119">설명</span><span class="sxs-lookup"><span data-stu-id="5aa21-119">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5aa21-120">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-120">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5aa21-121">설명</span><span class="sxs-lookup"><span data-stu-id="5aa21-121">Remarks</span></span>  

 <span data-ttu-id="5aa21-122">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5aa21-122">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5aa21-123">`<dataContractSerializer>` 동작 요소(있는 경우)는 항상 구성 파일에서 `<enableWebScript>` 동작 요소 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-123">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="5aa21-124">그렇지 않으면 결과 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa21-124">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa21-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5aa21-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="5aa21-126">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="5aa21-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="5aa21-127">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="5aa21-127">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
