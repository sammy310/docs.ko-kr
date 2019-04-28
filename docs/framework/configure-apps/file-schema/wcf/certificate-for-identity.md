---
title: <certificate> 에 대한 <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 76bdcb40d5016d7fcbff6c0d9769819f710065fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673358"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="fe2b8-102">\<인증서 >에 대 한 \<identity ></span><span class="sxs-lookup"><span data-stu-id="fe2b8-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="fe2b8-103">클라이언트에 서버의 유효성을 검사하는 데 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b8-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="fe2b8-104">요소 값을 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b8-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="fe2b8-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="fe2b8-105">\<identity></span></span>  
<span data-ttu-id="fe2b8-106">\<certificate></span><span class="sxs-lookup"><span data-stu-id="fe2b8-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe2b8-107">구문</span><span class="sxs-lookup"><span data-stu-id="fe2b8-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe2b8-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fe2b8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fe2b8-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe2b8-110">특성</span><span class="sxs-lookup"><span data-stu-id="fe2b8-110">Attributes</span></span>  
  
|<span data-ttu-id="fe2b8-111">특성</span><span class="sxs-lookup"><span data-stu-id="fe2b8-111">Attribute</span></span>|<span data-ttu-id="fe2b8-112">설명</span><span class="sxs-lookup"><span data-stu-id="fe2b8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe2b8-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="fe2b8-113">encodedValue</span></span>|<span data-ttu-id="fe2b8-114">인증서의 Base64 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b8-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe2b8-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fe2b8-115">Child Elements</span></span>  
 <span data-ttu-id="fe2b8-116">없음</span><span class="sxs-lookup"><span data-stu-id="fe2b8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe2b8-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fe2b8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fe2b8-118">요소</span><span class="sxs-lookup"><span data-stu-id="fe2b8-118">Element</span></span>|<span data-ttu-id="fe2b8-119">설명</span><span class="sxs-lookup"><span data-stu-id="fe2b8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe2b8-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="fe2b8-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="fe2b8-121">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b8-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fe2b8-122">예제</span><span class="sxs-lookup"><span data-stu-id="fe2b8-122">Example</span></span>  
 <span data-ttu-id="fe2b8-123">다음 코드에서는 클라이언트에 서버의 유효성을 검사하는 데 사용되는 인코딩된 인증서 표현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2b8-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="fe2b8-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="fe2b8-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="fe2b8-125">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="fe2b8-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fe2b8-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="fe2b8-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
