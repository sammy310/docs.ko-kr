---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152506"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="aac83-102">\<system.identityModel.서비스></span><span class="sxs-lookup"><span data-stu-id="aac83-102">\<system.identityModel.services></span></span>
<span data-ttu-id="aac83-103">WS-페더레이션 프로토콜을 사용하여 인증하기 위한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="aac83-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aac83-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aac83-105">&nbsp;&nbsp;**\<system.identityModel.서비스>**</span><span class="sxs-lookup"><span data-stu-id="aac83-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac83-106">구문</span><span class="sxs-lookup"><span data-stu-id="aac83-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aac83-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aac83-107">Attributes and Elements</span></span>  
 <span data-ttu-id="aac83-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aac83-109">특성</span><span class="sxs-lookup"><span data-stu-id="aac83-109">Attributes</span></span>  
 <span data-ttu-id="aac83-110">None</span><span class="sxs-lookup"><span data-stu-id="aac83-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aac83-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aac83-111">Child Elements</span></span>  
  
|<span data-ttu-id="aac83-112">요소</span><span class="sxs-lookup"><span data-stu-id="aac83-112">Element</span></span>|<span data-ttu-id="aac83-113">Description</span><span class="sxs-lookup"><span data-stu-id="aac83-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aac83-114">\<페더레이션구성></span><span class="sxs-lookup"><span data-stu-id="aac83-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="aac83-115">(WSFAM) <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP 모듈을 구성하는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aac83-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aac83-116">Parent Elements</span></span>  
 <span data-ttu-id="aac83-117">None</span><span class="sxs-lookup"><span data-stu-id="aac83-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aac83-118">설명</span><span class="sxs-lookup"><span data-stu-id="aac83-118">Remarks</span></span>  
 <span data-ttu-id="aac83-119">SAM `<system.identityModel.services>` 및 WSFAM에 대한 설정을 제공하기 위해 응용 프로그램의 구성 파일에 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="aac83-120"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 또는 클래스를 사용하여 코드에서 클레임 기반 액세스 제어를 제공하는 경우<xref:System.Security.Claims.ClaimsAuthorizationManager>권한 부여 결정을 내리는 데 사용되는 클레임 권한 `<identityConfiguration>` 부여 관리자() 및 정책은 `<federationConfiguration>` 이 섹션의 요소에서 암시적으로 또는 명시적으로 참조되는 요소를 통해 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="aac83-121">자세한 내용은 [ \<페더레이션구성>](federationconfiguration.md) 요소 아래의 **비고를** 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aac83-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="aac83-122">섹션은 `<system.identityModel.services>` <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="aac83-123">섹션에 구성된 `<federationConfiguration>` 자식 요소의 컬렉션은 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aac83-124">예제</span><span class="sxs-lookup"><span data-stu-id="aac83-124">Example</span></span>  
 <span data-ttu-id="aac83-125">다음 XML에서는 구성 파일에 `<system.identityModel.services>` 섹션을 추가하는 방법을 보여 주며, 섹션을 추가하는 방법을 보여 주시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="aac83-126">먼저 `<system.identityModel.services>` 단면과 단면 모두에 대해 `<system.identityModel>` 단면 선언을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="aac83-127">섹션을 추가할 `<system.identityModel.services>` 때 필요한 경우 런타임으로 기본 `<system.identityModel>` `<identityConfiguration>` 섹션을 만들 수 있도록 섹션에 대한 선언을 추가해야 합니다. 섹션 선언이 추가된 후 요소 아래에 페더레이션 인증 `<system.identityModel.services>` 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac83-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
