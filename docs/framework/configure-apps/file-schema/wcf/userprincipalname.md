---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854828"
---
# <a name="userprincipalname"></a><span data-ttu-id="e7f1b-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="e7f1b-101">\<userPrincipalName></span></span>
<span data-ttu-id="e7f1b-102">클라이언트에서 인증할 서비스의 UPN(User Principal Name)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="e7f1b-103">UPN을 설정 하는 방법에 대 한 자세한 내용은 [서비스 id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="e7f1b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7f1b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7f1b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e7f1b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e7f1b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="e7f1b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="e7f1b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<끝점 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="e7f1b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="e7f1b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="e7f1b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="e7f1b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f1b-110">구문</span><span class="sxs-lookup"><span data-stu-id="e7f1b-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f1b-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e7f1b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f1b-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f1b-113">특성</span><span class="sxs-lookup"><span data-stu-id="e7f1b-113">Attributes</span></span>  
  
|<span data-ttu-id="e7f1b-114">특성</span><span class="sxs-lookup"><span data-stu-id="e7f1b-114">Attribute</span></span>|<span data-ttu-id="e7f1b-115">Description</span><span class="sxs-lookup"><span data-stu-id="e7f1b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7f1b-116">value</span><span class="sxs-lookup"><span data-stu-id="e7f1b-116">value</span></span>|<span data-ttu-id="e7f1b-117">사용자 로그온 이름이라고도 하는 사용자 계정 이름 및 사용자 계정이 있는 도메인을 나타내는 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="e7f1b-118">Windows 도메인에 로그온하는 표준 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="e7f1b-119">형식은: someone@example.com (의 경우 전자 메일 주소).</span><span class="sxs-lookup"><span data-stu-id="e7f1b-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f1b-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e7f1b-120">Child Elements</span></span>  
 <span data-ttu-id="e7f1b-121">없음</span><span class="sxs-lookup"><span data-stu-id="e7f1b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f1b-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e7f1b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f1b-123">요소</span><span class="sxs-lookup"><span data-stu-id="e7f1b-123">Element</span></span>|<span data-ttu-id="e7f1b-124">설명</span><span class="sxs-lookup"><span data-stu-id="e7f1b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7f1b-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="e7f1b-125">\<identity></span></span>](identity.md)|<span data-ttu-id="e7f1b-126">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f1b-127">설명</span><span class="sxs-lookup"><span data-stu-id="e7f1b-127">Remarks</span></span>  
 <span data-ttu-id="e7f1b-128">이 id를 사용 하 여 끝점에 연결 하는 WCF (secure Windows Communication Foundation) 클라이언트는 끝점을 사용 하 여 SSPI 인증을 수행할 때 UPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7f1b-129">예제</span><span class="sxs-lookup"><span data-stu-id="e7f1b-129">Example</span></span>  
 <span data-ttu-id="e7f1b-130">다음 구성 코드는 클라이언트에서 인증할 서비스의 UPN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f1b-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="e7f1b-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7f1b-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="e7f1b-132">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="e7f1b-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e7f1b-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="e7f1b-133">\<identity></span></span>](identity.md)
