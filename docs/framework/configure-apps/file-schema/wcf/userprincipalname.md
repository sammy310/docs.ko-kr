---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 353d3e2d88e3515e54deadab85c37ce3be26ef29
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203867"
---
# \<userPrincipalName>

<span data-ttu-id="88abb-101">클라이언트에서 인증할 서비스의 UPN(User Principal Name)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-101">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="88abb-102">UPN을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88abb-102">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="88abb-103">구문</span><span class="sxs-lookup"><span data-stu-id="88abb-103">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88abb-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="88abb-104">Attributes and Elements</span></span>  

 <span data-ttu-id="88abb-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88abb-106">특성</span><span class="sxs-lookup"><span data-stu-id="88abb-106">Attributes</span></span>  
  
|<span data-ttu-id="88abb-107">attribute</span><span class="sxs-lookup"><span data-stu-id="88abb-107">Attribute</span></span>|<span data-ttu-id="88abb-108">Description</span><span class="sxs-lookup"><span data-stu-id="88abb-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88abb-109">값</span><span class="sxs-lookup"><span data-stu-id="88abb-109">value</span></span>|<span data-ttu-id="88abb-110">사용자 로그온 이름이라고도 하는 사용자 계정 이름 및 사용자 계정이 있는 도메인을 나타내는 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-110">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="88abb-111">Windows 도메인에 로그온하는 표준 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-111">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="88abb-112">형식은 someone@example.com (전자 메일 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-112">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88abb-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="88abb-113">Child Elements</span></span>  

 <span data-ttu-id="88abb-114">없음</span><span class="sxs-lookup"><span data-stu-id="88abb-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88abb-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="88abb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="88abb-116">요소</span><span class="sxs-lookup"><span data-stu-id="88abb-116">Element</span></span>|<span data-ttu-id="88abb-117">설명</span><span class="sxs-lookup"><span data-stu-id="88abb-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="88abb-118">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88abb-119">설명</span><span class="sxs-lookup"><span data-stu-id="88abb-119">Remarks</span></span>  

 <span data-ttu-id="88abb-120">이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 끝점을 사용 하 여 SSPI 인증을 수행할 때 UPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88abb-121">예제</span><span class="sxs-lookup"><span data-stu-id="88abb-121">Example</span></span>  

 <span data-ttu-id="88abb-122">다음 구성 코드는 클라이언트에서 인증할 서비스의 UPN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88abb-122">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="88abb-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88abb-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="88abb-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="88abb-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
