---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942615"
---
# <a name="nameclaimtype"></a><span data-ttu-id="599bb-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="599bb-101">\<nameClaimType></span></span>
<span data-ttu-id="599bb-102">속성을 <xref:System.Security.Principal.IIdentity.Name%2A> 지정 하는 클레임 유형을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="599bb-103">클레임 형식은이 토큰 처리기의 <xref:System.Security.Claims.Claim> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 메서드에서 반환 하는 개체의 <xref:System.Security.Claims.ClaimsIdentity> 컬렉션에서를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="599bb-104">그런 다음 일치 하는 클레임의 값이이 토큰 처리기에서 <xref:System.Security.Principal.IIdentity> 생성 된의 이름으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="599bb-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="599bb-105">\<system.identityModel></span></span>  
<span data-ttu-id="599bb-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="599bb-106">\<identityConfiguration></span></span>  
<span data-ttu-id="599bb-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="599bb-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="599bb-108">\<add></span><span class="sxs-lookup"><span data-stu-id="599bb-108">\<add></span></span>  
<span data-ttu-id="599bb-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="599bb-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="599bb-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="599bb-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="599bb-111">구문</span><span class="sxs-lookup"><span data-stu-id="599bb-111">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="599bb-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="599bb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="599bb-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="599bb-114">특성</span><span class="sxs-lookup"><span data-stu-id="599bb-114">Attributes</span></span>  
  
|<span data-ttu-id="599bb-115">특성</span><span class="sxs-lookup"><span data-stu-id="599bb-115">Attribute</span></span>|<span data-ttu-id="599bb-116">설명</span><span class="sxs-lookup"><span data-stu-id="599bb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="599bb-117">value</span><span class="sxs-lookup"><span data-stu-id="599bb-117">value</span></span>|<span data-ttu-id="599bb-118"><xref:System.Security.Principal.IIdentity.Name%2A> 속성에 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="599bb-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="599bb-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="599bb-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="599bb-120">Child Elements</span></span>  
 <span data-ttu-id="599bb-121">없음</span><span class="sxs-lookup"><span data-stu-id="599bb-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="599bb-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="599bb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="599bb-123">요소</span><span class="sxs-lookup"><span data-stu-id="599bb-123">Element</span></span>|<span data-ttu-id="599bb-124">Description</span><span class="sxs-lookup"><span data-stu-id="599bb-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="599bb-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="599bb-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="599bb-126"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="599bb-127">설명</span><span class="sxs-lookup"><span data-stu-id="599bb-127">Remarks</span></span>  
 <span data-ttu-id="599bb-128">요소 `<nameClaimType>` 는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> 에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="599bb-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="599bb-129">예제</span><span class="sxs-lookup"><span data-stu-id="599bb-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="599bb-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="599bb-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
