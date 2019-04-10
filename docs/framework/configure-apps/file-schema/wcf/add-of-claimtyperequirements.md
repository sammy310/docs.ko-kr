---
title: <add> / <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 97d3ecca369aeffb7b2e8464f385eeae13bd470f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168852"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="be125-102">\<추가 >의 \<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="be125-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="be125-103">페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="be125-104">예를 들어, 서비스는 특정 집합의 클레임 형식이어야 하는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="be125-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="be125-105">\<system.serviceModel></span></span>  
<span data-ttu-id="be125-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="be125-106">\<bindings></span></span>  
<span data-ttu-id="be125-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="be125-107">\<customBinding></span></span>  
<span data-ttu-id="be125-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="be125-108">\<binding></span></span>  
<span data-ttu-id="be125-109">\<security></span><span class="sxs-lookup"><span data-stu-id="be125-109">\<security></span></span>  
<span data-ttu-id="be125-110">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="be125-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="be125-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="be125-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be125-112">구문</span><span class="sxs-lookup"><span data-stu-id="be125-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be125-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="be125-113">Attributes and Elements</span></span>  
 <span data-ttu-id="be125-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be125-115">특성</span><span class="sxs-lookup"><span data-stu-id="be125-115">Attributes</span></span>  
  
|<span data-ttu-id="be125-116">특성</span><span class="sxs-lookup"><span data-stu-id="be125-116">Attribute</span></span>|<span data-ttu-id="be125-117">설명</span><span class="sxs-lookup"><span data-stu-id="be125-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be125-118">claimType</span><span class="sxs-lookup"><span data-stu-id="be125-118">claimType</span></span>|<span data-ttu-id="be125-119">클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="be125-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="be125-120">예를 들어 웹 사이트에서 제품을 구매하려면 사용자는 신용 한도가 충분한 유효한 신용 카드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="be125-121">이 경우 클레임 형식은 신용 카드 URI가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be125-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="be125-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="be125-122">isOptional</span></span>|<span data-ttu-id="be125-123">클레임이 선택적 요소인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="be125-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="be125-124">필수 클레임인 경우 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="be125-125">서비스가 특정 정보를 요청하지만 이 정보가 필수 요소가 아닌 경우 이 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be125-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="be125-126">예를 들어, 사용자가 성, 이름 및 주소를 입력해야 하지만 전화 번호는 선택적인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="be125-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be125-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="be125-127">Child Elements</span></span>  
 <span data-ttu-id="be125-128">없음</span><span class="sxs-lookup"><span data-stu-id="be125-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be125-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="be125-129">Parent Elements</span></span>  
  
|<span data-ttu-id="be125-130">요소</span><span class="sxs-lookup"><span data-stu-id="be125-130">Element</span></span>|<span data-ttu-id="be125-131">설명</span><span class="sxs-lookup"><span data-stu-id="be125-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be125-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="be125-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="be125-133">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="be125-134">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="be125-135">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="be125-136">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be125-137">설명</span><span class="sxs-lookup"><span data-stu-id="be125-137">Remarks</span></span>  
 <span data-ttu-id="be125-138">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="be125-139">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="be125-140">이 요구 사항은 보안 정책에 명시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be125-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="be125-141">클라이언트가 페더레이션 서비스에서 CardSpace와 같은 자격 증명을 요청하면 요구 사항을 토큰 요청(RequestSecurityToken)으로 가져가서 페더레이션 서비스가 요구 사항을 충족시키는 자격 증명을 발급할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be125-142">예제</span><span class="sxs-lookup"><span data-stu-id="be125-142">Example</span></span>  
 <span data-ttu-id="be125-143">다음 구성은 두 개의 클레임 형식 요구 사항을 보안 바인딩에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="be125-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be125-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="be125-144">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="be125-145">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="be125-145">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)
- [<span data-ttu-id="be125-146">바인딩</span><span class="sxs-lookup"><span data-stu-id="be125-146">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="be125-147">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="be125-147">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="be125-148">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="be125-148">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="be125-149">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="be125-149">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="be125-150">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="be125-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="be125-151">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="be125-151">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
