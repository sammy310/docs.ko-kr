---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942537"
---
# <a name="roleclaimtype"></a><span data-ttu-id="406a1-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="406a1-101">\<roleClaimType></span></span>
<span data-ttu-id="406a1-102">토큰 처리기의 <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 메서드에서 반환 하는 개체의 컬렉션에서 역할 유형 클레임을 정의 하는 클레임 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="406a1-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="406a1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="406a1-103">\<system.identityModel></span></span>  
<span data-ttu-id="406a1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="406a1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="406a1-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="406a1-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="406a1-106">\<add></span><span class="sxs-lookup"><span data-stu-id="406a1-106">\<add></span></span>  
<span data-ttu-id="406a1-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="406a1-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="406a1-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="406a1-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="406a1-109">구문</span><span class="sxs-lookup"><span data-stu-id="406a1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="406a1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="406a1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="406a1-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="406a1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="406a1-112">특성</span><span class="sxs-lookup"><span data-stu-id="406a1-112">Attributes</span></span>  
  
|<span data-ttu-id="406a1-113">특성</span><span class="sxs-lookup"><span data-stu-id="406a1-113">Attribute</span></span>|<span data-ttu-id="406a1-114">Description</span><span class="sxs-lookup"><span data-stu-id="406a1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="406a1-115">value</span><span class="sxs-lookup"><span data-stu-id="406a1-115">value</span></span>|<span data-ttu-id="406a1-116">역할 클레임 유형에 사용할 클레임의 클레임 유형을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="406a1-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="406a1-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="406a1-117">Child Elements</span></span>  
 <span data-ttu-id="406a1-118">없음</span><span class="sxs-lookup"><span data-stu-id="406a1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="406a1-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="406a1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="406a1-120">요소</span><span class="sxs-lookup"><span data-stu-id="406a1-120">Element</span></span>|<span data-ttu-id="406a1-121">Description</span><span class="sxs-lookup"><span data-stu-id="406a1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="406a1-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="406a1-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="406a1-123"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="406a1-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="406a1-124">설명</span><span class="sxs-lookup"><span data-stu-id="406a1-124">Remarks</span></span>  
 <span data-ttu-id="406a1-125">요소 `<roleClaimType>` 는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> 에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="406a1-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="406a1-126">예제</span><span class="sxs-lookup"><span data-stu-id="406a1-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="406a1-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="406a1-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
