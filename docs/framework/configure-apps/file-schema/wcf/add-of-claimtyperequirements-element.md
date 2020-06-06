---
title: <add>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153102"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="187e4-102">\<add>of \<claimTypeRequirements> 요소</span><span class="sxs-lookup"><span data-stu-id="187e4-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="187e4-103">페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="187e4-104">예를 들어, 서비스는 특정 집합의 클레임 형식이어야 하는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a><span data-ttu-id="187e4-105">구문</span><span class="sxs-lookup"><span data-stu-id="187e4-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="187e4-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="187e4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="187e4-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="187e4-108">특성</span><span class="sxs-lookup"><span data-stu-id="187e4-108">Attributes</span></span>  
  
|<span data-ttu-id="187e4-109">attribute</span><span class="sxs-lookup"><span data-stu-id="187e4-109">Attribute</span></span>|<span data-ttu-id="187e4-110">Description</span><span class="sxs-lookup"><span data-stu-id="187e4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="187e4-111">claimType</span><span class="sxs-lookup"><span data-stu-id="187e4-111">claimType</span></span>|<span data-ttu-id="187e4-112">클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="187e4-113">예를 들어 웹 사이트에서 제품을 구매하려면 사용자는 신용 한도가 충분한 유효한 신용 카드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="187e4-114">이 경우 클레임 형식은 신용 카드 URI가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="187e4-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="187e4-115">isOptional</span></span>|<span data-ttu-id="187e4-116">클레임이 선택적 요소인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="187e4-117">필수 클레임인 경우 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="187e4-118">서비스가 특정 정보를 요청하지만 이 정보가 필수 요소가 아닌 경우 이 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="187e4-119">예를 들어 사용자에 게 이름, 성 및 주소를 입력 해야 하지만 전화 번호는 선택 사항임을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="187e4-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="187e4-120">Child Elements</span></span>  
 <span data-ttu-id="187e4-121">없음</span><span class="sxs-lookup"><span data-stu-id="187e4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="187e4-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="187e4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="187e4-123">요소</span><span class="sxs-lookup"><span data-stu-id="187e4-123">Element</span></span>|<span data-ttu-id="187e4-124">Description</span><span class="sxs-lookup"><span data-stu-id="187e4-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="187e4-125">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="187e4-126">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="187e4-127">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="187e4-128">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="187e4-129">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="187e4-130">설명</span><span class="sxs-lookup"><span data-stu-id="187e4-130">Remarks</span></span>  
 <span data-ttu-id="187e4-131">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-131">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="187e4-132">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-132">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="187e4-133">이 요구 사항은 보안 정책에 명시됩니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-133">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="187e4-134">클라이언트가 페더레이션 서비스에서 CardSpace와 같은 자격 증명을 요청하면 요구 사항을 토큰 요청(RequestSecurityToken)으로 가져가서 페더레이션 서비스가 요구 사항을 충족시키는 자격 증명을 발급할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-134">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="187e4-135">예제</span><span class="sxs-lookup"><span data-stu-id="187e4-135">Example</span></span>  
 <span data-ttu-id="187e4-136">다음 구성은 두 개의 클레임 형식 요구 사항을 보안 바인딩에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="187e4-136">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="187e4-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="187e4-137">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
