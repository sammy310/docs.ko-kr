---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251908"
---
# \<roleClaimType>
<span data-ttu-id="b7ac7-101"><xref:System.Security.Claims.ClaimsIdentity>토큰 처리기의 메서드에서 반환 하는 개체의 컬렉션에서 역할 유형 클레임을 정의 하는 클레임 유형을 지정 합니다 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> .</span><span class="sxs-lookup"><span data-stu-id="b7ac7-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="b7ac7-102">구문</span><span class="sxs-lookup"><span data-stu-id="b7ac7-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7ac7-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b7ac7-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b7ac7-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ac7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7ac7-105">특성</span><span class="sxs-lookup"><span data-stu-id="b7ac7-105">Attributes</span></span>  
  
|<span data-ttu-id="b7ac7-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b7ac7-106">Attribute</span></span>|<span data-ttu-id="b7ac7-107">Description</span><span class="sxs-lookup"><span data-stu-id="b7ac7-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7ac7-108">값</span><span class="sxs-lookup"><span data-stu-id="b7ac7-108">value</span></span>|<span data-ttu-id="b7ac7-109">역할 클레임 유형에 사용할 클레임의 클레임 유형을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ac7-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7ac7-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b7ac7-110">Child Elements</span></span>  
 <span data-ttu-id="b7ac7-111">None</span><span class="sxs-lookup"><span data-stu-id="b7ac7-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7ac7-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b7ac7-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b7ac7-113">요소</span><span class="sxs-lookup"><span data-stu-id="b7ac7-113">Element</span></span>|<span data-ttu-id="b7ac7-114">Description</span><span class="sxs-lookup"><span data-stu-id="b7ac7-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="b7ac7-115"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ac7-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7ac7-116">설명</span><span class="sxs-lookup"><span data-stu-id="b7ac7-116">Remarks</span></span>  
 <span data-ttu-id="b7ac7-117">`<roleClaimType>`요소는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ac7-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7ac7-118">예제</span><span class="sxs-lookup"><span data-stu-id="b7ac7-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7ac7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7ac7-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
