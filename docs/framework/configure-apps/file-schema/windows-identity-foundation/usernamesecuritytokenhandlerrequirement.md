---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: a49b41c04c8f184188b62e04c3b232bd33752fca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185524"
---
# \<userNameSecurityTokenHandlerRequirement>

<span data-ttu-id="404d8-101">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="404d8-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="404d8-102">구문</span><span class="sxs-lookup"><span data-stu-id="404d8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="404d8-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="404d8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="404d8-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404d8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="404d8-105">특성</span><span class="sxs-lookup"><span data-stu-id="404d8-105">Attributes</span></span>  
  
|<span data-ttu-id="404d8-106">attribute</span><span class="sxs-lookup"><span data-stu-id="404d8-106">Attribute</span></span>|<span data-ttu-id="404d8-107">설명</span><span class="sxs-lookup"><span data-stu-id="404d8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="404d8-108">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="404d8-108">membershipProviderName</span></span>|<span data-ttu-id="404d8-109"><xref:System.Web.Security.MembershipProvider>보안 토큰 처리기에서 사용 해야 하는를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="404d8-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="404d8-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="404d8-110">Child Elements</span></span>  

 <span data-ttu-id="404d8-111">없음</span><span class="sxs-lookup"><span data-stu-id="404d8-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="404d8-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="404d8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="404d8-113">요소</span><span class="sxs-lookup"><span data-stu-id="404d8-113">Element</span></span>|<span data-ttu-id="404d8-114">설명</span><span class="sxs-lookup"><span data-stu-id="404d8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="404d8-115">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="404d8-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="404d8-116">설명</span><span class="sxs-lookup"><span data-stu-id="404d8-116">Remarks</span></span>  

 <span data-ttu-id="404d8-117">`<userNameSecurityTokenHandlerRequirement>`요소는 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 개체가 구성에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="404d8-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="404d8-118">예제</span><span class="sxs-lookup"><span data-stu-id="404d8-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
