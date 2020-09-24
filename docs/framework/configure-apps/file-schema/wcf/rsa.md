---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 1698ce421b4dcefc6ab94206443d2d7bca47aca8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162285"
---
# \<rsa>

<span data-ttu-id="592ce-101">이 id를 사용 하 여 끝점에 연결 하는 보안 WCF 클라이언트는 서버에서 제공 하는 클레임이이 id를 생성 하는 데 사용 된 RSA 공개 키를 포함 하는 클레임을 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-101">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**  
  
## <a name="syntax"></a><span data-ttu-id="592ce-102">구문</span><span class="sxs-lookup"><span data-stu-id="592ce-102">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="592ce-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="592ce-103">Attributes and Elements</span></span>  

 <span data-ttu-id="592ce-104">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="592ce-105">특성</span><span class="sxs-lookup"><span data-stu-id="592ce-105">Attributes</span></span>  
  
|<span data-ttu-id="592ce-106">attribute</span><span class="sxs-lookup"><span data-stu-id="592ce-106">Attribute</span></span>|<span data-ttu-id="592ce-107">Description</span><span class="sxs-lookup"><span data-stu-id="592ce-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="592ce-108">값</span><span class="sxs-lookup"><span data-stu-id="592ce-108">value</span></span>|<span data-ttu-id="592ce-109">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-109">Optional String.</span></span> <span data-ttu-id="592ce-110">클라이언트에서 비교할 RSA 공개 키 값입니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-110">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="592ce-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="592ce-111">Child Elements</span></span>  

 <span data-ttu-id="592ce-112">없음</span><span class="sxs-lookup"><span data-stu-id="592ce-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="592ce-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="592ce-113">Parent Elements</span></span>  
  
|<span data-ttu-id="592ce-114">요소</span><span class="sxs-lookup"><span data-stu-id="592ce-114">Element</span></span>|<span data-ttu-id="592ce-115">설명</span><span class="sxs-lookup"><span data-stu-id="592ce-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="592ce-116">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-116">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="592ce-117">설명</span><span class="sxs-lookup"><span data-stu-id="592ce-117">Remarks</span></span>  

 <span data-ttu-id="592ce-118">RSA 검사를 사용하면 RSA 키 또는 생성된 고유 RSA 키 값에 따라 하나의 인증서만 사용하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-118">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="592ce-119">이렇게 하면 RSA 키 값이 변경된 경우 기존 클라이언트와 작동하지 않는 서비스 대신 특정 RSA 키에 대한 인증을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-119">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="592ce-120">Id를 사용 하 여 클라이언트에 대 한 서비스의 유효성을 검사 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="592ce-120">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="592ce-121">예제</span><span class="sxs-lookup"><span data-stu-id="592ce-121">Example</span></span>  

 <span data-ttu-id="592ce-122">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 공개 키 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="592ce-122">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="592ce-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="592ce-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="592ce-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="592ce-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
