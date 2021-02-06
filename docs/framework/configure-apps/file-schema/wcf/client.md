---
description: 다음에 대해 자세히 알아보세요. <client>
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 9765460602738f49963ea521b3f00ed7c63cc568
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638862"
---
# \<client>

<span data-ttu-id="d9653-102">ph x="1" /&gt; 요소는 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="d9653-103">구문</span><span class="sxs-lookup"><span data-stu-id="d9653-103">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d9653-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d9653-104">Attributes and Elements</span></span>

 <span data-ttu-id="d9653-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9653-106">특성</span><span class="sxs-lookup"><span data-stu-id="d9653-106">Attributes</span></span>

 <span data-ttu-id="d9653-107">None</span><span class="sxs-lookup"><span data-stu-id="d9653-107">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9653-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d9653-108">Child Elements</span></span>

|<span data-ttu-id="d9653-109">요소</span><span class="sxs-lookup"><span data-stu-id="d9653-109">Element</span></span>|<span data-ttu-id="d9653-110">설명</span><span class="sxs-lookup"><span data-stu-id="d9653-110">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="d9653-111">이 클라이언트가 연결할 수 있는 끝점을 지정 하는 끝점 요소 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-111">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="d9653-112">메타데이터 처리를 위한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-112">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d9653-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d9653-113">Parent Elements</span></span>

|<span data-ttu-id="d9653-114">요소</span><span class="sxs-lookup"><span data-stu-id="d9653-114">Element</span></span>|<span data-ttu-id="d9653-115">설명</span><span class="sxs-lookup"><span data-stu-id="d9653-115">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="d9653-116">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-116">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9653-117">설명</span><span class="sxs-lookup"><span data-stu-id="d9653-117">Remarks</span></span>

 <span data-ttu-id="d9653-118">ph x="1" /&gt; 섹션은 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-118">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="d9653-119">클라이언트 섹션에 나열된 각 엔드포인트는 자체의 바인딩, 동작 및 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-119">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="d9653-120">각 끝점은 `name` 및 `contract` 특성 조합에 의해 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-120">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="d9653-121">클라이언트 코드는 클라이언트가 구현하는 서비스에 대한 엔드포인트에 연결하기 위한 `name`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-121">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="d9653-122">ph x="1" /&gt; 특성을 생략하면 엔드포인트는 구현하는 계약에 대한 기본 엔드포인트로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-122">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="d9653-123">또한 이 섹션에서는 메타데이터 처리를 위한 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9653-123">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="d9653-124">예제</span><span class="sxs-lookup"><span data-stu-id="d9653-124">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d9653-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9653-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="d9653-126">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d9653-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="d9653-127">클라이언트</span><span class="sxs-lookup"><span data-stu-id="d9653-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
