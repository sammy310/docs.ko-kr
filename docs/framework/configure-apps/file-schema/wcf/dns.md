---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: adfd94365ceb0ddc3164a6baef838c16027b4bc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190140"
---
# \<dns>

<span data-ttu-id="59ef8-101">서버에서 사용할 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="59ef8-102">서버의 인증서에 같은 값이 있는 DNS가 포함된 경우 이 ID를 X509 인증서 인증 모드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="59ef8-103">또한 SPN에 동일한 값이 있는 경우 Windows 인증 모드에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="59ef8-104">요소 값을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59ef8-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="59ef8-105">구문</span><span class="sxs-lookup"><span data-stu-id="59ef8-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59ef8-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="59ef8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="59ef8-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59ef8-108">특성</span><span class="sxs-lookup"><span data-stu-id="59ef8-108">Attributes</span></span>  
  
|<span data-ttu-id="59ef8-109">attribute</span><span class="sxs-lookup"><span data-stu-id="59ef8-109">Attribute</span></span>|<span data-ttu-id="59ef8-110">Description</span><span class="sxs-lookup"><span data-stu-id="59ef8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59ef8-111">값</span><span class="sxs-lookup"><span data-stu-id="59ef8-111">value</span></span>|<span data-ttu-id="59ef8-112">인증서의 DNS입니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-112">The DNS of the certificate.</span></span> <span data-ttu-id="59ef8-113">DNS는 IP 기반 네트워크에서 컴퓨터를 찾는 데 사용하는 산업 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="59ef8-114">사용자는 또는와 같은 표시 이름을 `https://go.microsoft.com/fwlink/?prd=10929` 207.46.131.137과 같은 `https://go.microsoft.com/fwlink/?LinkID=96165` 숫자 기반 주소 보다 쉽게 기억할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59ef8-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="59ef8-115">Child Elements</span></span>  

 <span data-ttu-id="59ef8-116">없음</span><span class="sxs-lookup"><span data-stu-id="59ef8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59ef8-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="59ef8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59ef8-118">요소</span><span class="sxs-lookup"><span data-stu-id="59ef8-118">Element</span></span>|<span data-ttu-id="59ef8-119">설명</span><span class="sxs-lookup"><span data-stu-id="59ef8-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="59ef8-120">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59ef8-121">예제</span><span class="sxs-lookup"><span data-stu-id="59ef8-121">Example</span></span>  

 <span data-ttu-id="59ef8-122">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59ef8-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="59ef8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59ef8-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="59ef8-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="59ef8-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
