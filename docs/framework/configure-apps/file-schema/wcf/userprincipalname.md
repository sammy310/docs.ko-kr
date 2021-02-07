---
description: 다음에 대해 자세히 알아보세요. <userPrincipalName>
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 73ace3d6f3d5cb88f2630a4a2ae319decf420021
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664420"
---
# \<userPrincipalName>

<span data-ttu-id="94b38-102">클라이언트에서 인증할 서비스의 UPN(User Principal Name)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="94b38-103">UPN을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94b38-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="94b38-104">구문</span><span class="sxs-lookup"><span data-stu-id="94b38-104">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94b38-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="94b38-105">Attributes and Elements</span></span>  

 <span data-ttu-id="94b38-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94b38-107">특성</span><span class="sxs-lookup"><span data-stu-id="94b38-107">Attributes</span></span>  
  
|<span data-ttu-id="94b38-108">attribute</span><span class="sxs-lookup"><span data-stu-id="94b38-108">Attribute</span></span>|<span data-ttu-id="94b38-109">Description</span><span class="sxs-lookup"><span data-stu-id="94b38-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94b38-110">값</span><span class="sxs-lookup"><span data-stu-id="94b38-110">value</span></span>|<span data-ttu-id="94b38-111">사용자 로그온 이름이라고도 하는 사용자 계정 이름 및 사용자 계정이 있는 도메인을 나타내는 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-111">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="94b38-112">Windows 도메인에 로그온하는 표준 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-112">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="94b38-113">형식은 someone@example.com (전자 메일 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-113">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94b38-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="94b38-114">Child Elements</span></span>  

 <span data-ttu-id="94b38-115">없음</span><span class="sxs-lookup"><span data-stu-id="94b38-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94b38-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="94b38-116">Parent Elements</span></span>  
  
|<span data-ttu-id="94b38-117">요소</span><span class="sxs-lookup"><span data-stu-id="94b38-117">Element</span></span>|<span data-ttu-id="94b38-118">설명</span><span class="sxs-lookup"><span data-stu-id="94b38-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="94b38-119">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-119">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94b38-120">설명</span><span class="sxs-lookup"><span data-stu-id="94b38-120">Remarks</span></span>  

 <span data-ttu-id="94b38-121">이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 끝점을 사용 하 여 SSPI 인증을 수행할 때 UPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-121">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94b38-122">예제</span><span class="sxs-lookup"><span data-stu-id="94b38-122">Example</span></span>  

 <span data-ttu-id="94b38-123">다음 구성 코드는 클라이언트에서 인증할 서비스의 UPN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b38-123">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="94b38-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94b38-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="94b38-125">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="94b38-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
