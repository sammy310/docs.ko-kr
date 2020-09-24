---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0e4cbc50c25d4fa1f67f283f2b52d4b174428cd3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153926"
---
# <a name="datacontractserializer"></a><span data-ttu-id="c9e8d-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="c9e8d-102">dataContractSerializer</span></span>

<span data-ttu-id="c9e8d-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="c9e8d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9e8d-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9e8d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c9e8d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c9e8d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9e8d-107">특성</span><span class="sxs-lookup"><span data-stu-id="c9e8d-107">Attributes</span></span>  
  
|<span data-ttu-id="c9e8d-108">요소</span><span class="sxs-lookup"><span data-stu-id="c9e8d-108">Element</span></span>|<span data-ttu-id="c9e8d-109">설명</span><span class="sxs-lookup"><span data-stu-id="c9e8d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9e8d-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="c9e8d-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="c9e8d-111">엔드포인트가 직렬화되거나 역직렬화될 때 해당 엔드포인트에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="c9e8d-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="c9e8d-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="c9e8d-113">직렬화 또는 역직렬화할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9e8d-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c9e8d-114">Child Elements</span></span>  

 <span data-ttu-id="c9e8d-115">없음</span><span class="sxs-lookup"><span data-stu-id="c9e8d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9e8d-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c9e8d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c9e8d-117">요소</span><span class="sxs-lookup"><span data-stu-id="c9e8d-117">Element</span></span>|<span data-ttu-id="c9e8d-118">설명</span><span class="sxs-lookup"><span data-stu-id="c9e8d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c9e8d-119">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9e8d-120">설명</span><span class="sxs-lookup"><span data-stu-id="c9e8d-120">Remarks</span></span>  

 <span data-ttu-id="c9e8d-121">알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="c9e8d-122">`<dataContractSerializer>` 동작 요소(있는 경우)는 항상 구성 파일에서 `<enableWebScript>` 동작 요소 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="c9e8d-123">그렇지 않으면 결과 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e8d-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e8d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9e8d-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="c9e8d-125">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="c9e8d-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="c9e8d-126">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="c9e8d-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
