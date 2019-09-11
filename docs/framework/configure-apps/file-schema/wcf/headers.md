---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855177"
---
# <a name="headers"></a><span data-ttu-id="2967a-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="2967a-101">\<headers></span></span>
<span data-ttu-id="2967a-102">하나 이상의 SOAP 헤더와 해당 기본 URI로 엔드포인트에 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="2967a-103">이 유용한 하나의 시나리오 집합이 SOAP 매개 시나리오 집합입니다. 이 시나리오 집합에서는 엔드포인트에 매개자를 대상으로 한 SOAP 헤더를 포함할 해당 엔드포인트의 클라이언트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="2967a-104">이 구성 요소는 그러한 사용자 지정 주소 헤더를 정의하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="2967a-105">엔드포인트 헤더 컬렉션의 항목은 사용자 정의 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="2967a-106">각 요소는 올바른 형식의 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="2967a-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2967a-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2967a-108">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2967a-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2967a-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="2967a-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="2967a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<끝점 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="2967a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="2967a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<헤더 >**</span><span class="sxs-lookup"><span data-stu-id="2967a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2967a-112">구문</span><span class="sxs-lookup"><span data-stu-id="2967a-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2967a-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2967a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2967a-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2967a-115">특성</span><span class="sxs-lookup"><span data-stu-id="2967a-115">Attributes</span></span>  
 <span data-ttu-id="2967a-116">없음</span><span class="sxs-lookup"><span data-stu-id="2967a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2967a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2967a-117">Child Elements</span></span>  
 <span data-ttu-id="2967a-118">사용자 정의 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2967a-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2967a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2967a-120">요소</span><span class="sxs-lookup"><span data-stu-id="2967a-120">Element</span></span>|<span data-ttu-id="2967a-121">Description</span><span class="sxs-lookup"><span data-stu-id="2967a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2967a-122">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="2967a-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="2967a-123">다양한 형식의 엔드포인트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2967a-124">설명</span><span class="sxs-lookup"><span data-stu-id="2967a-124">Remarks</span></span>  
 <span data-ttu-id="2967a-125">선택적 헤더는 엔드포인트를 확인하거나 상호 작용하는 데 필요한 자세한 주소 지정 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="2967a-126">예를 들어 헤더는 들어오는 메시지를 처리하는 방법, 엔드포인트가 회신 메시지를 보내야 하는 위치 또는 여러 인스턴스를 사용할 수 있는 경우 특정 사용자의 들어오는 메시지를 처리하는 데 사용할 서비스 인스턴스를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2967a-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="2967a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="2967a-128">종점 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="2967a-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
