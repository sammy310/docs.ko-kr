---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251744"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="c4011-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="c4011-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="c4011-102"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4011-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="c4011-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4011-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4011-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c4011-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c4011-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c4011-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c4011-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="c4011-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="c4011-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> 추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="c4011-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="c4011-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userNameSecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="c4011-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4011-109">구문</span><span class="sxs-lookup"><span data-stu-id="c4011-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4011-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c4011-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c4011-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c4011-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4011-112">특성</span><span class="sxs-lookup"><span data-stu-id="c4011-112">Attributes</span></span>  
  
|<span data-ttu-id="c4011-113">특성</span><span class="sxs-lookup"><span data-stu-id="c4011-113">Attribute</span></span>|<span data-ttu-id="c4011-114">Description</span><span class="sxs-lookup"><span data-stu-id="c4011-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4011-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="c4011-115">membershipProviderName</span></span>|<span data-ttu-id="c4011-116">보안 토큰 <xref:System.Web.Security.MembershipProvider> 처리기에서 사용 해야 하는를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4011-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4011-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c4011-117">Child Elements</span></span>  
 <span data-ttu-id="c4011-118">없음</span><span class="sxs-lookup"><span data-stu-id="c4011-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4011-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c4011-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c4011-120">요소</span><span class="sxs-lookup"><span data-stu-id="c4011-120">Element</span></span>|<span data-ttu-id="c4011-121">설명</span><span class="sxs-lookup"><span data-stu-id="c4011-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4011-122">\<add></span><span class="sxs-lookup"><span data-stu-id="c4011-122">\<add></span></span>](add.md)|<span data-ttu-id="c4011-123">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4011-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4011-124">설명</span><span class="sxs-lookup"><span data-stu-id="c4011-124">Remarks</span></span>  
 <span data-ttu-id="c4011-125">요소 `<userNameSecurityTokenHandlerRequirement>` 는 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 개체가 구성 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> 에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4011-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4011-126">예제</span><span class="sxs-lookup"><span data-stu-id="c4011-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
