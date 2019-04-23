---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 8c7b7c9b42ac72b878aed4e12298dc3655f1e707
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115598"
---
# <a name="roleclaimtype"></a><span data-ttu-id="19623-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="19623-101">\<roleClaimType></span></span>
<span data-ttu-id="19623-102">컬렉션의 역할 유형 클레임을 정의 하는 클레임 유형을 <xref:System.Security.Claims.ClaimsIdentity> 반환한 개체는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 토큰 처리기의 메서드.</span><span class="sxs-lookup"><span data-stu-id="19623-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="19623-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="19623-103">\<system.identityModel></span></span>  
<span data-ttu-id="19623-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="19623-104">\<identityConfiguration></span></span>  
<span data-ttu-id="19623-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="19623-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="19623-106">\<add></span><span class="sxs-lookup"><span data-stu-id="19623-106">\<add></span></span>  
<span data-ttu-id="19623-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="19623-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="19623-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="19623-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19623-109">구문</span><span class="sxs-lookup"><span data-stu-id="19623-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19623-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19623-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19623-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19623-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19623-112">특성</span><span class="sxs-lookup"><span data-stu-id="19623-112">Attributes</span></span>  
  
|<span data-ttu-id="19623-113">특성</span><span class="sxs-lookup"><span data-stu-id="19623-113">Attribute</span></span>|<span data-ttu-id="19623-114">설명</span><span class="sxs-lookup"><span data-stu-id="19623-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19623-115">값</span><span class="sxs-lookup"><span data-stu-id="19623-115">value</span></span>|<span data-ttu-id="19623-116">역할 클레임 형식에 대해 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="19623-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19623-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19623-117">Child Elements</span></span>  
 <span data-ttu-id="19623-118">없음</span><span class="sxs-lookup"><span data-stu-id="19623-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19623-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19623-119">Parent Elements</span></span>  
  
|<span data-ttu-id="19623-120">요소</span><span class="sxs-lookup"><span data-stu-id="19623-120">Element</span></span>|<span data-ttu-id="19623-121">설명</span><span class="sxs-lookup"><span data-stu-id="19623-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19623-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="19623-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="19623-123">에 대 한 구성을 제공 합니다 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="19623-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19623-124">설명</span><span class="sxs-lookup"><span data-stu-id="19623-124">Remarks</span></span>  
 <span data-ttu-id="19623-125">`<roleClaimType>` 요소 집합을 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> 속성 때를 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체는 구성에서 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19623-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19623-126">예제</span><span class="sxs-lookup"><span data-stu-id="19623-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19623-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="19623-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
