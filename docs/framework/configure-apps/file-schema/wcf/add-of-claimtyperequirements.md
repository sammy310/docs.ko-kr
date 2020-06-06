---
title: <claimTypeRequirements>의 <add>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153089"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="d2811-102">\<claimTypeRequirements>의 \<add></span><span class="sxs-lookup"><span data-stu-id="d2811-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="d2811-103">페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="d2811-104">예를 들어, 서비스는 특정 집합의 클레임 형식이어야 하는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d2811-105">구문</span><span class="sxs-lookup"><span data-stu-id="d2811-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2811-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d2811-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d2811-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2811-108">특성</span><span class="sxs-lookup"><span data-stu-id="d2811-108">Attributes</span></span>  
  
|<span data-ttu-id="d2811-109">attribute</span><span class="sxs-lookup"><span data-stu-id="d2811-109">Attribute</span></span>|<span data-ttu-id="d2811-110">Description</span><span class="sxs-lookup"><span data-stu-id="d2811-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2811-111">claimType</span><span class="sxs-lookup"><span data-stu-id="d2811-111">claimType</span></span>|<span data-ttu-id="d2811-112">클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="d2811-113">예를 들어 웹 사이트에서 제품을 구매하려면 사용자는 신용 한도가 충분한 유효한 신용 카드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="d2811-114">이 경우 클레임 형식은 신용 카드 URI가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="d2811-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="d2811-115">isOptional</span></span>|<span data-ttu-id="d2811-116">클레임이 선택적 요소인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="d2811-117">필수 클레임인 경우 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="d2811-118">서비스가 특정 정보를 요청하지만 이 정보가 필수 요소가 아닌 경우 이 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="d2811-119">예를 들어 사용자에 게 이름, 성 및 주소를 입력 해야 하지만 전화 번호는 선택 사항임을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2811-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d2811-120">Child Elements</span></span>  
 <span data-ttu-id="d2811-121">없음</span><span class="sxs-lookup"><span data-stu-id="d2811-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2811-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d2811-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d2811-123">요소</span><span class="sxs-lookup"><span data-stu-id="d2811-123">Element</span></span>|<span data-ttu-id="d2811-124">Description</span><span class="sxs-lookup"><span data-stu-id="d2811-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="d2811-125">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-125">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="d2811-126">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-126">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d2811-127">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-127">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d2811-128">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-128">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2811-129">설명</span><span class="sxs-lookup"><span data-stu-id="d2811-129">Remarks</span></span>  
 <span data-ttu-id="d2811-130">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d2811-131">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d2811-132">이 요구 사항은 보안 정책에 명시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-132">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="d2811-133">클라이언트가 페더레이션 서비스에서 CardSpace와 같은 자격 증명을 요청하면 요구 사항을 토큰 요청(RequestSecurityToken)으로 가져가서 페더레이션 서비스가 요구 사항을 충족시키는 자격 증명을 발급할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-133">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2811-134">예제</span><span class="sxs-lookup"><span data-stu-id="d2811-134">Example</span></span>  
 <span data-ttu-id="d2811-135">다음 구성은 두 개의 클레임 형식 요구 사항을 보안 바인딩에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2811-135">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2811-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2811-136">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements>](claimtyperequirements-element.md)
- [<span data-ttu-id="d2811-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="d2811-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d2811-138">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="d2811-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d2811-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d2811-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="d2811-140">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="d2811-140">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d2811-141">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="d2811-141">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
