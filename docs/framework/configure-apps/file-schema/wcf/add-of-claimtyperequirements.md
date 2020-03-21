---
title: <claimTypeRequirements>의 <add>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153089"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="dd227-102">\<클레임> \<추가Type요구 사항></span><span class="sxs-lookup"><span data-stu-id="dd227-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="dd227-103">페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="dd227-104">예를 들어, 서비스는 특정 집합의 클레임 형식이어야 하는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="dd227-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dd227-106">&nbsp;&nbsp;[**\<system.service모델>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dd227-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<바인딩>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="dd227-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<사용자 지정 바인딩>**](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="dd227-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<바인딩>**</span><span class="sxs-lookup"><span data-stu-id="dd227-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="dd227-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안>**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="dd227-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<발행토큰매개 변수>**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="dd227-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<클레임유형요구사항>**](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd227-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="dd227-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="dd227-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd227-114">구문</span><span class="sxs-lookup"><span data-stu-id="dd227-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd227-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dd227-115">Attributes and Elements</span></span>  
 <span data-ttu-id="dd227-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd227-117">특성</span><span class="sxs-lookup"><span data-stu-id="dd227-117">Attributes</span></span>  
  
|<span data-ttu-id="dd227-118">attribute</span><span class="sxs-lookup"><span data-stu-id="dd227-118">Attribute</span></span>|<span data-ttu-id="dd227-119">Description</span><span class="sxs-lookup"><span data-stu-id="dd227-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd227-120">claimType</span><span class="sxs-lookup"><span data-stu-id="dd227-120">claimType</span></span>|<span data-ttu-id="dd227-121">클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="dd227-122">예를 들어 웹 사이트에서 제품을 구매하려면 사용자는 신용 한도가 충분한 유효한 신용 카드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="dd227-123">이 경우 클레임 형식은 신용 카드 URI가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="dd227-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="dd227-124">isOptional</span></span>|<span data-ttu-id="dd227-125">클레임이 선택적 요소인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="dd227-126">필수 클레임인 경우 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="dd227-127">서비스가 특정 정보를 요청하지만 이 정보가 필수 요소가 아닌 경우 이 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="dd227-128">예를 들어 사용자가 이름, 성 및 주소를 입력하도록 요구하지만 전화 번호가 선택 사항이라고 결정하는 경우</span><span class="sxs-lookup"><span data-stu-id="dd227-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd227-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dd227-129">Child Elements</span></span>  
 <span data-ttu-id="dd227-130">없음</span><span class="sxs-lookup"><span data-stu-id="dd227-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd227-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dd227-131">Parent Elements</span></span>  
  
|<span data-ttu-id="dd227-132">요소</span><span class="sxs-lookup"><span data-stu-id="dd227-132">Element</span></span>|<span data-ttu-id="dd227-133">Description</span><span class="sxs-lookup"><span data-stu-id="dd227-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd227-134">\<클레임유형요구사항></span><span class="sxs-lookup"><span data-stu-id="dd227-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="dd227-135">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="dd227-136">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="dd227-137">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="dd227-138">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd227-139">설명</span><span class="sxs-lookup"><span data-stu-id="dd227-139">Remarks</span></span>  
 <span data-ttu-id="dd227-140">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="dd227-141">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="dd227-142">이 요구 사항은 보안 정책에 명시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="dd227-143">클라이언트가 페더레이션 서비스에서 CardSpace와 같은 자격 증명을 요청하면 요구 사항을 토큰 요청(RequestSecurityToken)으로 가져가서 페더레이션 서비스가 요구 사항을 충족시키는 자격 증명을 발급할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd227-144">예제</span><span class="sxs-lookup"><span data-stu-id="dd227-144">Example</span></span>  
 <span data-ttu-id="dd227-145">다음 구성은 두 개의 클레임 형식 요구 사항을 보안 바인딩에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd227-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd227-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd227-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dd227-147">\<클레임유형요구사항></span><span class="sxs-lookup"><span data-stu-id="dd227-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="dd227-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="dd227-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dd227-149">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="dd227-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dd227-150">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="dd227-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="dd227-151">\<사용자 지정 바인딩></span><span class="sxs-lookup"><span data-stu-id="dd227-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="dd227-152">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="dd227-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="dd227-153">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="dd227-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
