---
description: 다음에 대해 자세히 알아보세요. <nameClaimType>
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: d5bc2f96c2753febdb61c3495b7067c0e31e52d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664056"
---
# \<nameClaimType>

<span data-ttu-id="8e65e-102">속성을 지정 하는 클레임 유형을 설정 합니다 <xref:System.Security.Principal.IIdentity.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="8e65e-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="8e65e-103">클레임 형식은 <xref:System.Security.Claims.Claim> <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 이 토큰 처리기의 메서드에서 반환 하는 개체의 컬렉션에서를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e65e-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="8e65e-104">그런 다음 일치 하는 클레임의 값 <xref:System.Security.Principal.IIdentity> 이이 토큰 처리기에서 생성 된의 이름으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e65e-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="8e65e-105">구문</span><span class="sxs-lookup"><span data-stu-id="8e65e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e65e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e65e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8e65e-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e65e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e65e-108">특성</span><span class="sxs-lookup"><span data-stu-id="8e65e-108">Attributes</span></span>  
  
|<span data-ttu-id="8e65e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="8e65e-109">Attribute</span></span>|<span data-ttu-id="8e65e-110">Description</span><span class="sxs-lookup"><span data-stu-id="8e65e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e65e-111">값</span><span class="sxs-lookup"><span data-stu-id="8e65e-111">value</span></span>|<span data-ttu-id="8e65e-112">속성에 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다 <xref:System.Security.Principal.IIdentity.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="8e65e-112">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="8e65e-113">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8e65e-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e65e-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e65e-114">Child Elements</span></span>  

 <span data-ttu-id="8e65e-115">없음</span><span class="sxs-lookup"><span data-stu-id="8e65e-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e65e-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e65e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8e65e-117">요소</span><span class="sxs-lookup"><span data-stu-id="8e65e-117">Element</span></span>|<span data-ttu-id="8e65e-118">설명</span><span class="sxs-lookup"><span data-stu-id="8e65e-118">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="8e65e-119"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e65e-119">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e65e-120">설명</span><span class="sxs-lookup"><span data-stu-id="8e65e-120">Remarks</span></span>  

 <span data-ttu-id="8e65e-121">`<nameClaimType>`요소는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e65e-121">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e65e-122">예제</span><span class="sxs-lookup"><span data-stu-id="8e65e-122">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e65e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e65e-123">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
