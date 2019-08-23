---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 74ca031f7017d51adaa7a71593f537b64abbeae6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942885"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="bc420-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="bc420-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="bc420-102">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="bc420-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="bc420-103">\<system.identityModel></span></span>  
<span data-ttu-id="bc420-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="bc420-104">\<identityConfiguration></span></span>  
<span data-ttu-id="bc420-105">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="bc420-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc420-106">구문</span><span class="sxs-lookup"><span data-stu-id="bc420-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc420-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bc420-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bc420-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc420-109">특성</span><span class="sxs-lookup"><span data-stu-id="bc420-109">Attributes</span></span>  
  
|<span data-ttu-id="bc420-110">특성</span><span class="sxs-lookup"><span data-stu-id="bc420-110">Attribute</span></span>|<span data-ttu-id="bc420-111">Description</span><span class="sxs-lookup"><span data-stu-id="bc420-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc420-112">type</span><span class="sxs-lookup"><span data-stu-id="bc420-112">type</span></span>|<span data-ttu-id="bc420-113"><xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에서 파생 되는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="bc420-114">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc420-114">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc420-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bc420-115">Child Elements</span></span>  
 <span data-ttu-id="bc420-116"><xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthorizationManager>` 특성이 없거나 특성이 클래스를 참조 하는 경우 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 <xref:System.Security.Claims.ClaimsAuthorizationManager> 파생 된 클래스는 자식 구성 요소를 정의할 수 있습니다. `type` `type`</span><span class="sxs-lookup"><span data-stu-id="bc420-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc420-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bc420-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bc420-118">요소</span><span class="sxs-lookup"><span data-stu-id="bc420-118">Element</span></span>|<span data-ttu-id="bc420-119">설명</span><span class="sxs-lookup"><span data-stu-id="bc420-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc420-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="bc420-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="bc420-121">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc420-122">설명</span><span class="sxs-lookup"><span data-stu-id="bc420-122">Remarks</span></span>  
 <span data-ttu-id="bc420-123">클래스를 <xref:System.Security.Claims.ClaimsAuthorizationManager> 통해 제공 되는 기본 동작은 항상 들어오는 클레임을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="bc420-124">특성을 `type` 지정 하지 않거나 특성에서 `type` <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스를 지정 하는 경우 요소 `<claimsAuthorizationManager>` 는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="bc420-125">특성을 지정 하 `type` 여 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에서 파생 된 형식을 등록 하 고 사용자 지정 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="bc420-126">파생 클래스는 이러한 요소를 처리 하도록 메서드를 `<claimsAuthorizationManager>` <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="bc420-127">자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bc420-128">또는 클래스를 사용 하 여 `<federationConfiguration>` 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소에서 참조 하는 id 구성은 클레임 권한 부여 관리자 및 다음을 수행 하는 데 사용 되는 정책을 구성 합니다. <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 권한 부여 결정.</span><span class="sxs-lookup"><span data-stu-id="bc420-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="bc420-129">이는 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램 등 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="bc420-130">응용 프로그램이 수동 웹 응용 프로그램이 `<claimsAuthorizationManager>` 아닌 경우 참조 되는 id 구성의 요소 및 자식 정책 요소 (있는 경우)만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="bc420-131">다른 모든 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-131">All other settings are ignored.</span></span> <span data-ttu-id="bc420-132">자세한 내용은 [ \<federationConfiguration >](federationconfiguration.md) 요소를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc420-132">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="bc420-133">이 요소는 속성 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> 을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc420-134">예제</span><span class="sxs-lookup"><span data-stu-id="bc420-134">Example</span></span>  
 <span data-ttu-id="bc420-135">다음 XML은 리소스 작업 쌍으로 구성 된 정책을 구현 하는 클레임 권한 부여 관리자에 대 한 구성을 보여 줍니다. 각각은 요청자에 게 리소스에 대 한 작업을 수행 하기 위해 소유 해야 하는 클레임의 부울 조합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="bc420-136">이 정책을 사용할 수 있는 클레임 권한 부여 관리자를 구현 하는 코드는 `ClaimsBasedAuthorization` 샘플에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc420-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
