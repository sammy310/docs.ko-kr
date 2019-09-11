---
title: <certificate> 에 대한 <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850009"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="0bf65-102">\<id >에 \<대 한 인증서 ></span><span class="sxs-lookup"><span data-stu-id="0bf65-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="0bf65-103">클라이언트에 서버의 유효성을 검사하는 데 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf65-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="0bf65-104">요소 값을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bf65-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="0bf65-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0bf65-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0bf65-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0bf65-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0bf65-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="0bf65-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="0bf65-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<끝점 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="0bf65-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="0bf65-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="0bf65-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="0bf65-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<인증서 >**</span><span class="sxs-lookup"><span data-stu-id="0bf65-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf65-111">구문</span><span class="sxs-lookup"><span data-stu-id="0bf65-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bf65-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0bf65-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0bf65-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf65-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bf65-114">특성</span><span class="sxs-lookup"><span data-stu-id="0bf65-114">Attributes</span></span>  
  
|<span data-ttu-id="0bf65-115">특성</span><span class="sxs-lookup"><span data-stu-id="0bf65-115">Attribute</span></span>|<span data-ttu-id="0bf65-116">Description</span><span class="sxs-lookup"><span data-stu-id="0bf65-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bf65-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="0bf65-117">encodedValue</span></span>|<span data-ttu-id="0bf65-118">인증서의 Base64 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf65-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bf65-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0bf65-119">Child Elements</span></span>  
 <span data-ttu-id="0bf65-120">없음</span><span class="sxs-lookup"><span data-stu-id="0bf65-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bf65-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0bf65-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0bf65-122">요소</span><span class="sxs-lookup"><span data-stu-id="0bf65-122">Element</span></span>|<span data-ttu-id="0bf65-123">Description</span><span class="sxs-lookup"><span data-stu-id="0bf65-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bf65-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="0bf65-124">\<identity></span></span>](identity.md)|<span data-ttu-id="0bf65-125">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf65-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0bf65-126">예제</span><span class="sxs-lookup"><span data-stu-id="0bf65-126">Example</span></span>  
 <span data-ttu-id="0bf65-127">다음 코드에서는 클라이언트에 서버의 유효성을 검사하는 데 사용되는 인코딩된 인증서 표현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf65-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="0bf65-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="0bf65-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="0bf65-129">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="0bf65-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0bf65-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="0bf65-130">\<identity></span></span>](identity.md)
