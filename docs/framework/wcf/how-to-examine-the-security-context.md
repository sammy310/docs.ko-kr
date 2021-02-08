---
description: '자세한 정보: 방법: 보안 컨텍스트 검사'
title: '방법: 보안 컨텍스트 검사'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: e82491a877cf1f741767c91d1e7c304ba7676e6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779402"
---
# <a name="how-to-examine-the-security-context"></a><span data-ttu-id="41996-103">방법: 보안 컨텍스트 검사</span><span class="sxs-lookup"><span data-stu-id="41996-103">How to: Examine the Security Context</span></span>

<span data-ttu-id="41996-104">WCF (Windows Communication Foundation) 서비스를 프로그래밍 하는 경우 서비스 보안 컨텍스트를 사용 하 여 서비스를 인증 하는 데 사용 되는 클라이언트 자격 증명과 클레임에 대 한 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41996-104">When programming Windows Communication Foundation (WCF) services, the service security context enables you to determine details about the client credentials and claims used to authenticate with the service.</span></span> <span data-ttu-id="41996-105"><xref:System.ServiceModel.ServiceSecurityContext> 클래스의 속성을 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41996-105">This is done by using the properties of the <xref:System.ServiceModel.ServiceSecurityContext> class.</span></span>  
  
 <span data-ttu-id="41996-106">예를 들어 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 또는 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 속성을 사용하여 현재 클라이언트의 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41996-106">For example, you can retrieve the identity of the current client by using the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> or the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property.</span></span> <span data-ttu-id="41996-107">클라이언트가 익명인지 여부를 확인하기 위해 <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-107">To determine whether the client is anonymous, use the <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> property.</span></span>  
  
 <span data-ttu-id="41996-108">또한 <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> 속성에서 클레임 컬렉션을 반복하여 클라이언트 대신 수행된 클레임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41996-108">You can also determine what claims are being made on behalf of the client by iterating through the collection of claims in the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
### <a name="to-get-the-current-security-context"></a><span data-ttu-id="41996-109">현재 보안 컨텍스트를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="41996-109">To get the current security context</span></span>  
  
- <span data-ttu-id="41996-110">정적 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 속성에 액세스하여 현재 보안 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41996-110">Access the static property <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> to get the current security context.</span></span> <span data-ttu-id="41996-111">참조에서 현재 컨텍스트의 모든 속성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-111">Examine any of the properties of the current context from the reference.</span></span>  
  
### <a name="to-determine-the-identity-of-the-caller"></a><span data-ttu-id="41996-112">호출자의 ID를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="41996-112">To determine the identity of the caller</span></span>  
  
1. <span data-ttu-id="41996-113"><xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 및 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 속성의 값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-113">Print the value of the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> properties.</span></span>  
  
### <a name="to-parse-the-claims-of-a-caller"></a><span data-ttu-id="41996-114">호출자의 클레임을 구문 분석하려면</span><span class="sxs-lookup"><span data-stu-id="41996-114">To parse the claims of a caller</span></span>  
  
1. <span data-ttu-id="41996-115">현재 <xref:System.IdentityModel.Policy.AuthorizationContext> 클래스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-115">Return the current <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span> <span data-ttu-id="41996-116"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 속성을 사용하여 현재 서비스 보안 컨텍스트를 반환한 다음 `AuthorizationContext` 속성을 사용하여 <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-116">Use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to return the current service security context, then return the `AuthorizationContext` using the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
2. <span data-ttu-id="41996-117"><xref:System.IdentityModel.Claims.ClaimSet> 클래스의 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> 속성에서 반환된 <xref:System.IdentityModel.Policy.AuthorizationContext> 개체의 컬렉션을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-117">Parse the collection of <xref:System.IdentityModel.Claims.ClaimSet> objects returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41996-118">예제</span><span class="sxs-lookup"><span data-stu-id="41996-118">Example</span></span>  

 <span data-ttu-id="41996-119">다음 예제에서는 현재 보안 컨텍스트의 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 및 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 속성에 대한 값, <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> 속성, 클레임의 리소스 값 및 현재 보안 컨텍스트의 모든 클레임에 대한 <xref:System.IdentityModel.Claims.Claim.Right%2A> 속성을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-119">The following example prints the values of the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> properties of the current security context and the <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> property, the resource value of the claim, and the <xref:System.IdentityModel.Claims.Claim.Right%2A> property of every claim in the current security context.</span></span>  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41996-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="41996-120">Compiling the Code</span></span>  

 <span data-ttu-id="41996-121">코드는 다음 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41996-121">The code uses the following namespaces:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a><span data-ttu-id="41996-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41996-122">See also</span></span>

- [<span data-ttu-id="41996-123">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="41996-123">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="41996-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="41996-124">Service Identity and Authentication</span></span>](./feature-details/service-identity-and-authentication.md)
