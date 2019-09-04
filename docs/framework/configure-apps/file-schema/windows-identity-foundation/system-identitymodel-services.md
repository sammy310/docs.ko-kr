---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251802"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="16bff-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="16bff-102">\<system.identityModel.services></span></span>
<span data-ttu-id="16bff-103">WS-FEDERATION 프로토콜을 사용 하는 인증에 대 한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="16bff-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="16bff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="16bff-105">&nbsp;&nbsp; **\<System.identitymodel >**</span><span class="sxs-lookup"><span data-stu-id="16bff-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16bff-106">구문</span><span class="sxs-lookup"><span data-stu-id="16bff-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16bff-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="16bff-107">Attributes and Elements</span></span>  
 <span data-ttu-id="16bff-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16bff-109">특성</span><span class="sxs-lookup"><span data-stu-id="16bff-109">Attributes</span></span>  
 <span data-ttu-id="16bff-110">없음</span><span class="sxs-lookup"><span data-stu-id="16bff-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16bff-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="16bff-111">Child Elements</span></span>  
  
|<span data-ttu-id="16bff-112">요소</span><span class="sxs-lookup"><span data-stu-id="16bff-112">Element</span></span>|<span data-ttu-id="16bff-113">Description</span><span class="sxs-lookup"><span data-stu-id="16bff-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16bff-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="16bff-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="16bff-115"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (Wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> 및 (SAM) HTTP 모듈을 구성 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16bff-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="16bff-116">Parent Elements</span></span>  
 <span data-ttu-id="16bff-117">없음</span><span class="sxs-lookup"><span data-stu-id="16bff-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16bff-118">설명</span><span class="sxs-lookup"><span data-stu-id="16bff-118">Remarks</span></span>  
 <span data-ttu-id="16bff-119">응용 프로그램 `<system.identityModel.services>` 의 구성 파일에 섹션을 추가 하 여 SAM 및 wsfam에 대 한 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="16bff-120">또는 클래스를 `<identityConfiguration>` 사용 하 여<xref:System.Security.Claims.ClaimsAuthorizationManager>코드에서 클레임 기반 액세스 제어를 제공 하는 경우 권한 부여 결정을 내리는 데 사용 되는 클레임 권한 부여 관리자 () 및 정책이 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 이 섹션의 `<federationConfiguration>` 요소에서 암시적으로 또는 명시적으로 참조 되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="16bff-121">자세한 내용은 [ \<federationConfiguration >](federationconfiguration.md) 요소 아래의 **설명을** 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="16bff-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="16bff-122">섹션은 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스로 표현 됩니다. `<system.identityModel.services>`</span><span class="sxs-lookup"><span data-stu-id="16bff-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="16bff-123">섹션에서 구성 된 `<federationConfiguration>` 자식 요소의 컬렉션은 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16bff-124">예제</span><span class="sxs-lookup"><span data-stu-id="16bff-124">Example</span></span>  
 <span data-ttu-id="16bff-125">다음 XML에서는 구성 파일에 섹션을 `<system.identityModel.services>` 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="16bff-126">`<system.identityModel.services>` 섹션`<system.identityModel>` 및 섹션에 대 한 섹션 선언을 먼저 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="16bff-127">`<system.identityModel.services>` 섹션을 추가할 때 필요한 경우 런타임에서 기본 `<identityConfiguration>` 섹션을 만들 수 있도록 `<system.identityModel>` 섹션에 대 한 선언을 추가 해야 합니다. 섹션 선언이 추가 된 후 `<system.identityModel.services>` 요소 아래에서 페더레이션 인증 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16bff-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
