---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ddbe8a862940272e4192a3f4c0abdc1f9e8b5d48
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252081"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="a9280-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="a9280-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="a9280-102">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
<span data-ttu-id="a9280-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a9280-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a9280-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a9280-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a9280-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a9280-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a9280-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthorizationManager >**</span><span class="sxs-lookup"><span data-stu-id="a9280-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9280-107">구문</span><span class="sxs-lookup"><span data-stu-id="a9280-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9280-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a9280-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9280-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9280-110">특성</span><span class="sxs-lookup"><span data-stu-id="a9280-110">Attributes</span></span>  
  
|<span data-ttu-id="a9280-111">특성</span><span class="sxs-lookup"><span data-stu-id="a9280-111">Attribute</span></span>|<span data-ttu-id="a9280-112">설명</span><span class="sxs-lookup"><span data-stu-id="a9280-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9280-113">type</span><span class="sxs-lookup"><span data-stu-id="a9280-113">type</span></span>|<span data-ttu-id="a9280-114"><xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에서 파생 되는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="a9280-115">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9280-115">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9280-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a9280-116">Child Elements</span></span>  
 <span data-ttu-id="a9280-117"><xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthorizationManager>` 특성이 없거나 특성이 클래스를 참조 하는 경우 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 <xref:System.Security.Claims.ClaimsAuthorizationManager> 파생 된 클래스는 자식 구성 요소를 정의할 수 있습니다. `type` `type`</span><span class="sxs-lookup"><span data-stu-id="a9280-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9280-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a9280-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a9280-119">요소</span><span class="sxs-lookup"><span data-stu-id="a9280-119">Element</span></span>|<span data-ttu-id="a9280-120">설명</span><span class="sxs-lookup"><span data-stu-id="a9280-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9280-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a9280-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a9280-122">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9280-123">설명</span><span class="sxs-lookup"><span data-stu-id="a9280-123">Remarks</span></span>  
 <span data-ttu-id="a9280-124">클래스를 <xref:System.Security.Claims.ClaimsAuthorizationManager> 통해 제공 되는 기본 동작은 항상 들어오는 클레임을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="a9280-125">특성을 `type` 지정 하지 않거나 특성에서 `type` <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스를 지정 하는 경우 요소 `<claimsAuthorizationManager>` 는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="a9280-126">특성을 지정 하 `type` 여 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에서 파생 된 형식을 등록 하 고 사용자 지정 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="a9280-127">파생 클래스는 이러한 요소를 처리 하도록 메서드를 `<claimsAuthorizationManager>` <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="a9280-128">자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9280-129">또는 클래스를 사용 하 여 `<federationConfiguration>` 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소에서 참조 하는 id 구성은 클레임 권한 부여 관리자 및 다음을 수행 하는 데 사용 되는 정책을 구성 합니다. <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 권한 부여 결정.</span><span class="sxs-lookup"><span data-stu-id="a9280-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="a9280-130">이는 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램 등 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="a9280-131">응용 프로그램이 수동 웹 응용 프로그램이 `<claimsAuthorizationManager>` 아닌 경우 참조 되는 id 구성의 요소 및 자식 정책 요소 (있는 경우)만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="a9280-132">다른 모든 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-132">All other settings are ignored.</span></span> <span data-ttu-id="a9280-133">자세한 내용은 [ \<federationConfiguration >](federationconfiguration.md) 요소를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9280-133">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="a9280-134">이 요소는 속성 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> 을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9280-135">예제</span><span class="sxs-lookup"><span data-stu-id="a9280-135">Example</span></span>  
 <span data-ttu-id="a9280-136">다음 XML은 리소스 작업 쌍으로 구성 된 정책을 구현 하는 클레임 권한 부여 관리자에 대 한 구성을 보여 줍니다. 각각은 요청자에 게 리소스에 대 한 작업을 수행 하기 위해 소유 해야 하는 클레임의 부울 조합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="a9280-137">이 정책을 사용할 수 있는 클레임 권한 부여 관리자를 구현 하는 코드는 `ClaimsBasedAuthorization` 샘플에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9280-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
