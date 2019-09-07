---
title: <add>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 9c56cccd7a6f72a701e4b8652afecc2361e6218a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400683"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="2c7c3-102">\<\<claimTypeRequirements > 요소의 > 추가</span><span class="sxs-lookup"><span data-stu-id="2c7c3-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="2c7c3-103">페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="2c7c3-104">예를 들어, 서비스는 특정 집합의 클레임 형식이어야 하는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="2c7c3-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2c7c3-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2c7c3-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2c7c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2c7c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="2c7c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2c7c3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="2c7c3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메시지 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2c7c3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="2c7c3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="2c7c3-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="2c7c3-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2c7c3-114">구문</span><span class="sxs-lookup"><span data-stu-id="2c7c3-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c7c3-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2c7c3-115">Attributes and Elements</span></span>  
 <span data-ttu-id="2c7c3-116">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c7c3-117">특성</span><span class="sxs-lookup"><span data-stu-id="2c7c3-117">Attributes</span></span>  
  
|<span data-ttu-id="2c7c3-118">특성</span><span class="sxs-lookup"><span data-stu-id="2c7c3-118">Attribute</span></span>|<span data-ttu-id="2c7c3-119">Description</span><span class="sxs-lookup"><span data-stu-id="2c7c3-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c7c3-120">claimType</span><span class="sxs-lookup"><span data-stu-id="2c7c3-120">claimType</span></span>|<span data-ttu-id="2c7c3-121">클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="2c7c3-122">예를 들어 웹 사이트에서 제품을 구매하려면 사용자는 신용 한도가 충분한 유효한 신용 카드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="2c7c3-123">이 경우 클레임 형식은 신용 카드 URI가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="2c7c3-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="2c7c3-124">isOptional</span></span>|<span data-ttu-id="2c7c3-125">클레임이 선택적 요소인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="2c7c3-126">필수 클레임인 경우 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="2c7c3-127">서비스가 특정 정보를 요청하지만 이 정보가 필수 요소가 아닌 경우 이 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="2c7c3-128">예를 들어, 사용자가 성, 이름 및 주소를 입력해야 하지만 전화 번호는 선택적인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c7c3-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2c7c3-129">Child Elements</span></span>  
 <span data-ttu-id="2c7c3-130">없음</span><span class="sxs-lookup"><span data-stu-id="2c7c3-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c7c3-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2c7c3-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2c7c3-132">요소</span><span class="sxs-lookup"><span data-stu-id="2c7c3-132">Element</span></span>|<span data-ttu-id="2c7c3-133">설명</span><span class="sxs-lookup"><span data-stu-id="2c7c3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c7c3-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2c7c3-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="2c7c3-135">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="2c7c3-136">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="2c7c3-137">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2c7c3-138">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2c7c3-139">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c7c3-140">설명</span><span class="sxs-lookup"><span data-stu-id="2c7c3-140">Remarks</span></span>  
 <span data-ttu-id="2c7c3-141">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2c7c3-142">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2c7c3-143">이 요구 사항은 보안 정책에 명시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="2c7c3-144">클라이언트가 페더레이션 서비스에서 CardSpace와 같은 자격 증명을 요청하면 요구 사항을 토큰 요청(RequestSecurityToken)으로 가져가서 페더레이션 서비스가 요구 사항을 충족시키는 자격 증명을 발급할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c7c3-145">예제</span><span class="sxs-lookup"><span data-stu-id="2c7c3-145">Example</span></span>  
 <span data-ttu-id="2c7c3-146">다음 구성은 두 개의 클레임 형식 요구 사항을 보안 바인딩에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7c3-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c7c3-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="2c7c3-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
