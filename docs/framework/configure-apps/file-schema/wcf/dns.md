---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 26b45b17ecd7bbd3fffb5d03553834ec22eedc62
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611174"
---
# <a name="dns"></a><span data-ttu-id="27c11-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="27c11-101">\<dns></span></span>
<span data-ttu-id="27c11-102">서버에서 사용할 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="27c11-103">서버의 인증서에 같은 값이 있는 DNS가 포함된 경우 이 ID를 X509 인증서 인증 모드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="27c11-104">SPN에 같은 값이 있는 경우 Windows 인증 모드에도 해당 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="27c11-105">요소 값을 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="27c11-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="27c11-106">\<identity></span></span>  
<span data-ttu-id="27c11-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="27c11-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c11-108">구문</span><span class="sxs-lookup"><span data-stu-id="27c11-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27c11-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="27c11-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27c11-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27c11-111">특성</span><span class="sxs-lookup"><span data-stu-id="27c11-111">Attributes</span></span>  
  
|<span data-ttu-id="27c11-112">특성</span><span class="sxs-lookup"><span data-stu-id="27c11-112">Attribute</span></span>|<span data-ttu-id="27c11-113">설명</span><span class="sxs-lookup"><span data-stu-id="27c11-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27c11-114">값</span><span class="sxs-lookup"><span data-stu-id="27c11-114">value</span></span>|<span data-ttu-id="27c11-115">인증서의 DNS입니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-115">The DNS of the certificate.</span></span> <span data-ttu-id="27c11-116">DNS는 IP 기반 네트워크에서 컴퓨터를 찾는 데 사용하는 산업 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="27c11-117">사용자가 기억 하기 쉬운 표시 이름 같은 <https://go.microsoft.com/fwlink/?prd=10929> 나 [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165)207.46.131.137와 같은 번호 기반 주소를 보다 쉽게, 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27c11-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="27c11-118">Child Elements</span></span>  
 <span data-ttu-id="27c11-119">없음</span><span class="sxs-lookup"><span data-stu-id="27c11-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27c11-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="27c11-120">Parent Elements</span></span>  
  
|<span data-ttu-id="27c11-121">요소</span><span class="sxs-lookup"><span data-stu-id="27c11-121">Element</span></span>|<span data-ttu-id="27c11-122">설명</span><span class="sxs-lookup"><span data-stu-id="27c11-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c11-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="27c11-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="27c11-124">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27c11-125">예제</span><span class="sxs-lookup"><span data-stu-id="27c11-125">Example</span></span>  
 <span data-ttu-id="27c11-126">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27c11-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="27c11-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="27c11-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="27c11-128">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="27c11-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="27c11-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="27c11-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
