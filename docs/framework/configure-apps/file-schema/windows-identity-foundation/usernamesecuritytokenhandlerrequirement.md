---
description: 다음에 대해 자세히 알아보세요. <userNameSecurityTokenHandlerRequirement>
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: c2bca086d06738699517fe140173f321a3233a4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786501"
---
# \<userNameSecurityTokenHandlerRequirement>

<span data-ttu-id="ac68b-102">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac68b-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="ac68b-103">구문</span><span class="sxs-lookup"><span data-stu-id="ac68b-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac68b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ac68b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ac68b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac68b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac68b-106">특성</span><span class="sxs-lookup"><span data-stu-id="ac68b-106">Attributes</span></span>  
  
|<span data-ttu-id="ac68b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="ac68b-107">Attribute</span></span>|<span data-ttu-id="ac68b-108">설명</span><span class="sxs-lookup"><span data-stu-id="ac68b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac68b-109">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="ac68b-109">membershipProviderName</span></span>|<span data-ttu-id="ac68b-110"><xref:System.Web.Security.MembershipProvider>보안 토큰 처리기에서 사용 해야 하는를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac68b-110">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac68b-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac68b-111">Child Elements</span></span>  

 <span data-ttu-id="ac68b-112">없음</span><span class="sxs-lookup"><span data-stu-id="ac68b-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac68b-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac68b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ac68b-114">요소</span><span class="sxs-lookup"><span data-stu-id="ac68b-114">Element</span></span>|<span data-ttu-id="ac68b-115">설명</span><span class="sxs-lookup"><span data-stu-id="ac68b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="ac68b-116">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac68b-116">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac68b-117">설명</span><span class="sxs-lookup"><span data-stu-id="ac68b-117">Remarks</span></span>  

 <span data-ttu-id="ac68b-118">`<userNameSecurityTokenHandlerRequirement>`요소는 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 개체가 구성에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac68b-118">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac68b-119">예제</span><span class="sxs-lookup"><span data-stu-id="ac68b-119">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
