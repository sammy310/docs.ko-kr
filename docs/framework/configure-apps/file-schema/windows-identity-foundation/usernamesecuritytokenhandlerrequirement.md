---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944262"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="c9204-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="c9204-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="c9204-102"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9204-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="c9204-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c9204-103">\<system.identityModel></span></span>  
<span data-ttu-id="c9204-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c9204-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c9204-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c9204-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c9204-106">\<add></span><span class="sxs-lookup"><span data-stu-id="c9204-106">\<add></span></span>  
<span data-ttu-id="c9204-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="c9204-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9204-108">구문</span><span class="sxs-lookup"><span data-stu-id="c9204-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9204-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c9204-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c9204-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9204-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9204-111">특성</span><span class="sxs-lookup"><span data-stu-id="c9204-111">Attributes</span></span>  
  
|<span data-ttu-id="c9204-112">특성</span><span class="sxs-lookup"><span data-stu-id="c9204-112">Attribute</span></span>|<span data-ttu-id="c9204-113">Description</span><span class="sxs-lookup"><span data-stu-id="c9204-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9204-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="c9204-114">membershipProviderName</span></span>|<span data-ttu-id="c9204-115">보안 토큰 <xref:System.Web.Security.MembershipProvider> 처리기에서 사용 해야 하는를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9204-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9204-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c9204-116">Child Elements</span></span>  
 <span data-ttu-id="c9204-117">없음</span><span class="sxs-lookup"><span data-stu-id="c9204-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9204-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c9204-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c9204-119">요소</span><span class="sxs-lookup"><span data-stu-id="c9204-119">Element</span></span>|<span data-ttu-id="c9204-120">설명</span><span class="sxs-lookup"><span data-stu-id="c9204-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9204-121">\<add></span><span class="sxs-lookup"><span data-stu-id="c9204-121">\<add></span></span>](add.md)|<span data-ttu-id="c9204-122">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9204-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9204-123">설명</span><span class="sxs-lookup"><span data-stu-id="c9204-123">Remarks</span></span>  
 <span data-ttu-id="c9204-124">요소 `<userNameSecurityTokenHandlerRequirement>` 는 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 개체가 구성 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> 에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9204-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9204-125">예제</span><span class="sxs-lookup"><span data-stu-id="c9204-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
