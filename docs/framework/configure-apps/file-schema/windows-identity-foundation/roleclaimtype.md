---
description: 다음에 대해 자세히 알아보세요. <roleClaimType>
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 69b86489b0a970addb7fc7c11dd88be52ac68e95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652681"
---
# \<roleClaimType>

<span data-ttu-id="c9450-102"><xref:System.Security.Claims.ClaimsIdentity>토큰 처리기의 메서드에서 반환 하는 개체의 컬렉션에서 역할 유형 클레임을 정의 하는 클레임 유형을 지정 합니다 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> .</span><span class="sxs-lookup"><span data-stu-id="c9450-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="c9450-103">구문</span><span class="sxs-lookup"><span data-stu-id="c9450-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9450-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c9450-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c9450-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9450-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9450-106">특성</span><span class="sxs-lookup"><span data-stu-id="c9450-106">Attributes</span></span>  
  
|<span data-ttu-id="c9450-107">attribute</span><span class="sxs-lookup"><span data-stu-id="c9450-107">Attribute</span></span>|<span data-ttu-id="c9450-108">Description</span><span class="sxs-lookup"><span data-stu-id="c9450-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9450-109">값</span><span class="sxs-lookup"><span data-stu-id="c9450-109">value</span></span>|<span data-ttu-id="c9450-110">역할 클레임 유형에 사용할 클레임의 클레임 유형을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c9450-110">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9450-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c9450-111">Child Elements</span></span>  

 <span data-ttu-id="c9450-112">없음</span><span class="sxs-lookup"><span data-stu-id="c9450-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9450-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c9450-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c9450-114">요소</span><span class="sxs-lookup"><span data-stu-id="c9450-114">Element</span></span>|<span data-ttu-id="c9450-115">설명</span><span class="sxs-lookup"><span data-stu-id="c9450-115">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="c9450-116"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9450-116">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9450-117">설명</span><span class="sxs-lookup"><span data-stu-id="c9450-117">Remarks</span></span>  

 <span data-ttu-id="c9450-118">`<roleClaimType>`요소는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9450-118">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9450-119">예제</span><span class="sxs-lookup"><span data-stu-id="c9450-119">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9450-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9450-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
