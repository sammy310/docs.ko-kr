---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452229"
---
# <a name="dns"></a><span data-ttu-id="eccf1-101">dns > \<</span><span class="sxs-lookup"><span data-stu-id="eccf1-101">\<dns></span></span>
<span data-ttu-id="eccf1-102">서버에서 사용할 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="eccf1-103">서버의 인증서에 같은 값이 있는 DNS가 포함된 경우 이 ID를 X509 인증서 인증 모드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="eccf1-104">SPN에 같은 값이 있는 경우 Windows 인증 모드에도 해당 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="eccf1-105">요소 값을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eccf1-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="eccf1-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eccf1-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eccf1-107">&nbsp;[ **\<system.servicemodel >를**](system-servicemodel.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="eccf1-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eccf1-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="eccf1-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="eccf1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<끝점 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="eccf1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="eccf1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identity >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="eccf1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="eccf1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**dns >**</span><span class="sxs-lookup"><span data-stu-id="eccf1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eccf1-112">구문</span><span class="sxs-lookup"><span data-stu-id="eccf1-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eccf1-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eccf1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="eccf1-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eccf1-115">특성</span><span class="sxs-lookup"><span data-stu-id="eccf1-115">Attributes</span></span>  
  
|<span data-ttu-id="eccf1-116">attribute</span><span class="sxs-lookup"><span data-stu-id="eccf1-116">Attribute</span></span>|<span data-ttu-id="eccf1-117">Description</span><span class="sxs-lookup"><span data-stu-id="eccf1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eccf1-118">값</span><span class="sxs-lookup"><span data-stu-id="eccf1-118">value</span></span>|<span data-ttu-id="eccf1-119">인증서의 DNS입니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-119">The DNS of the certificate.</span></span> <span data-ttu-id="eccf1-120">DNS는 IP 기반 네트워크에서 컴퓨터를 찾는 데 사용하는 산업 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="eccf1-121">사용자는 `https://go.microsoft.com/fwlink/?prd=10929` 또는 `https://go.microsoft.com/fwlink/?LinkID=96165`같은 숫자 기반 주소 보다 쉽게 표시 이름을 기억할 수 있습니다 (예: 207.46.131.137과).</span><span class="sxs-lookup"><span data-stu-id="eccf1-121">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eccf1-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eccf1-122">Child Elements</span></span>  
 <span data-ttu-id="eccf1-123">없음</span><span class="sxs-lookup"><span data-stu-id="eccf1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eccf1-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eccf1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="eccf1-125">요소</span><span class="sxs-lookup"><span data-stu-id="eccf1-125">Element</span></span>|<span data-ttu-id="eccf1-126">Description</span><span class="sxs-lookup"><span data-stu-id="eccf1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eccf1-127">\<id ></span><span class="sxs-lookup"><span data-stu-id="eccf1-127">\<identity></span></span>](identity.md)|<span data-ttu-id="eccf1-128">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eccf1-129">예제</span><span class="sxs-lookup"><span data-stu-id="eccf1-129">Example</span></span>  
 <span data-ttu-id="eccf1-130">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eccf1-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="eccf1-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eccf1-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="eccf1-132">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="eccf1-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="eccf1-133">\<id ></span><span class="sxs-lookup"><span data-stu-id="eccf1-133">\<identity></span></span>](identity.md)
