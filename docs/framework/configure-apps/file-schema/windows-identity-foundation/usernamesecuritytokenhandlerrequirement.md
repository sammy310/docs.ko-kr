---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790457"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="4c5f4-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="4c5f4-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="4c5f4-102">에 대 한 구성을 제공 합니다 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5f4-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="4c5f4-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4c5f4-103">\<system.identityModel></span></span>  
<span data-ttu-id="4c5f4-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4c5f4-104">\<identityConfiguration></span></span>  
<span data-ttu-id="4c5f4-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4c5f4-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4c5f4-106">\<add></span><span class="sxs-lookup"><span data-stu-id="4c5f4-106">\<add></span></span>  
<span data-ttu-id="4c5f4-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="4c5f4-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c5f4-108">구문</span><span class="sxs-lookup"><span data-stu-id="4c5f4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c5f4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4c5f4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c5f4-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5f4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c5f4-111">특성</span><span class="sxs-lookup"><span data-stu-id="4c5f4-111">Attributes</span></span>  
  
|<span data-ttu-id="4c5f4-112">특성</span><span class="sxs-lookup"><span data-stu-id="4c5f4-112">Attribute</span></span>|<span data-ttu-id="4c5f4-113">설명</span><span class="sxs-lookup"><span data-stu-id="4c5f4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c5f4-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="4c5f4-114">membershipProviderName</span></span>|<span data-ttu-id="4c5f4-115">지정 된 <xref:System.Web.Security.MembershipProvider> 는 보안 토큰 처리기를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5f4-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c5f4-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4c5f4-116">Child Elements</span></span>  
 <span data-ttu-id="4c5f4-117">없음</span><span class="sxs-lookup"><span data-stu-id="4c5f4-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c5f4-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4c5f4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4c5f4-119">요소</span><span class="sxs-lookup"><span data-stu-id="4c5f4-119">Element</span></span>|<span data-ttu-id="4c5f4-120">설명</span><span class="sxs-lookup"><span data-stu-id="4c5f4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c5f4-121">\<add></span><span class="sxs-lookup"><span data-stu-id="4c5f4-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="4c5f4-122">토큰 처리기 컬렉션에 지정 된 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5f4-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c5f4-123">설명</span><span class="sxs-lookup"><span data-stu-id="4c5f4-123">Remarks</span></span>  
 <span data-ttu-id="4c5f4-124">`<userNameSecurityTokenHandlerRequirement>` 요소 집합을 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> 속성 때를 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 개체는 구성에서 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5f4-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c5f4-125">예제</span><span class="sxs-lookup"><span data-stu-id="4c5f4-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
