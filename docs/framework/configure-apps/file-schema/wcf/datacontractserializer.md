---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8ba16d9cc30b07d3e6b0924e6013ec01443867d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704130"
---
# <a name="datacontractserializer"></a><span data-ttu-id="447b1-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="447b1-102">dataContractSerializer</span></span>
<span data-ttu-id="447b1-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="447b1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="447b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="447b1-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="447b1-105">\<behaviors></span></span>  
<span data-ttu-id="447b1-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="447b1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="447b1-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="447b1-107">\<behavior></span></span>  
<span data-ttu-id="447b1-108">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="447b1-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="447b1-109">구문</span><span class="sxs-lookup"><span data-stu-id="447b1-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="447b1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="447b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="447b1-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="447b1-112">특성</span><span class="sxs-lookup"><span data-stu-id="447b1-112">Attributes</span></span>  
  
|<span data-ttu-id="447b1-113">요소</span><span class="sxs-lookup"><span data-stu-id="447b1-113">Element</span></span>|<span data-ttu-id="447b1-114">설명</span><span class="sxs-lookup"><span data-stu-id="447b1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="447b1-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="447b1-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="447b1-116">엔드포인트가 serialize되거나 deserialize될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="447b1-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="447b1-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="447b1-118">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="447b1-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="447b1-119">Child Elements</span></span>  
 <span data-ttu-id="447b1-120">없음</span><span class="sxs-lookup"><span data-stu-id="447b1-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="447b1-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="447b1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="447b1-122">요소</span><span class="sxs-lookup"><span data-stu-id="447b1-122">Element</span></span>|<span data-ttu-id="447b1-123">설명</span><span class="sxs-lookup"><span data-stu-id="447b1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="447b1-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="447b1-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="447b1-125">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="447b1-126">설명</span><span class="sxs-lookup"><span data-stu-id="447b1-126">Remarks</span></span>  
 <span data-ttu-id="447b1-127">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="447b1-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="447b1-128">`<dataContractSerializer>` 동작 요소(있는 경우)는 항상 구성 파일에서 `<enableWebScript>` 동작 요소 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="447b1-129">그렇지 않으면 결과 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="447b1-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447b1-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="447b1-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="447b1-131">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="447b1-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="447b1-132">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="447b1-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
