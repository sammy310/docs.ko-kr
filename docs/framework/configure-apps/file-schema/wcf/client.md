---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "72773942"
---
# \<client>
<span data-ttu-id="c20b8-101">ph x="1" /&gt; 요소는 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="c20b8-102">구문</span><span class="sxs-lookup"><span data-stu-id="c20b8-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="c20b8-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c20b8-103">Attributes and Elements</span></span>
 <span data-ttu-id="c20b8-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c20b8-105">특성</span><span class="sxs-lookup"><span data-stu-id="c20b8-105">Attributes</span></span>
 <span data-ttu-id="c20b8-106">None</span><span class="sxs-lookup"><span data-stu-id="c20b8-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c20b8-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c20b8-107">Child Elements</span></span>

|<span data-ttu-id="c20b8-108">요소</span><span class="sxs-lookup"><span data-stu-id="c20b8-108">Element</span></span>|<span data-ttu-id="c20b8-109">Description</span><span class="sxs-lookup"><span data-stu-id="c20b8-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="c20b8-110">이 클라이언트가 연결할 수 있는 끝점을 지정 하는 끝점 요소 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="c20b8-111">메타데이터 처리를 위한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c20b8-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c20b8-112">Parent Elements</span></span>

|<span data-ttu-id="c20b8-113">요소</span><span class="sxs-lookup"><span data-stu-id="c20b8-113">Element</span></span>|<span data-ttu-id="c20b8-114">Description</span><span class="sxs-lookup"><span data-stu-id="c20b8-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="c20b8-115">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c20b8-116">설명</span><span class="sxs-lookup"><span data-stu-id="c20b8-116">Remarks</span></span>
 <span data-ttu-id="c20b8-117">ph x="1" /&gt; 섹션은 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="c20b8-118">클라이언트 섹션에 나열된 각 엔드포인트는 자체의 바인딩, 동작 및 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="c20b8-119">각 끝점은 `name` 및 `contract` 특성 조합에 의해 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="c20b8-120">클라이언트 코드는 클라이언트가 구현하는 서비스에 대한 엔드포인트에 연결하기 위한 `name`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="c20b8-121">ph x="1" /&gt; 특성을 생략하면 엔드포인트는 구현하는 계약에 대한 기본 엔드포인트로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="c20b8-122">또한 이 섹션에서는 메타데이터 처리를 위한 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c20b8-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="c20b8-123">예제</span><span class="sxs-lookup"><span data-stu-id="c20b8-123">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c20b8-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c20b8-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="c20b8-125">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c20b8-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c20b8-126">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c20b8-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
