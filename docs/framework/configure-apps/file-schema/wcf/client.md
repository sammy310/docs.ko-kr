---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 2e0352efdd5b709984338fe4484b120bddb7d545
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164361"
---
# <a name="client"></a><span data-ttu-id="a2573-101">\<client></span><span class="sxs-lookup"><span data-stu-id="a2573-101">\<client></span></span>
<span data-ttu-id="a2573-102">`client` 요소는 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="a2573-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a2573-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2573-104">\<client></span><span class="sxs-lookup"><span data-stu-id="a2573-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2573-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2573-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2573-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a2573-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a2573-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2573-108">특성</span><span class="sxs-lookup"><span data-stu-id="a2573-108">Attributes</span></span>  
 <span data-ttu-id="a2573-109">없음</span><span class="sxs-lookup"><span data-stu-id="a2573-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2573-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a2573-110">Child Elements</span></span>  
  
|<span data-ttu-id="a2573-111">요소</span><span class="sxs-lookup"><span data-stu-id="a2573-111">Element</span></span>|<span data-ttu-id="a2573-112">설명</span><span class="sxs-lookup"><span data-stu-id="a2573-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2573-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="a2573-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="a2573-114">이 클라이언트가 연결할 수 있는 엔드포인트를 지정하는 엔드포인트 요소 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="a2573-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="a2573-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="a2573-116">메타데이터 처리를 위한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2573-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a2573-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a2573-118">요소</span><span class="sxs-lookup"><span data-stu-id="a2573-118">Element</span></span>|<span data-ttu-id="a2573-119">설명</span><span class="sxs-lookup"><span data-stu-id="a2573-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2573-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a2573-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="a2573-121">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2573-122">설명</span><span class="sxs-lookup"><span data-stu-id="a2573-122">Remarks</span></span>  
 <span data-ttu-id="a2573-123">`client` 섹션은 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="a2573-124">클라이언트 섹션에 나열된 각 엔드포인트는 자체의 바인딩, 동작 및 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="a2573-125">각 끝점은 `name` 및 `contract` 특성 조합에 의해 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="a2573-126">클라이언트 코드는 클라이언트가 구현하는 서비스에 대한 엔드포인트에 연결하기 위한 `name`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="a2573-127">`name` 특성을 생략하면 엔드포인트는 구현하는 계약에 대한 기본 엔드포인트로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="a2573-128">또한 이 섹션에서는 메타데이터 처리를 위한 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2573-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2573-129">예제</span><span class="sxs-lookup"><span data-stu-id="a2573-129">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="a2573-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="a2573-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="a2573-131">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="a2573-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="a2573-132">클라이언트</span><span class="sxs-lookup"><span data-stu-id="a2573-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
