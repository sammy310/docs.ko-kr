---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152506"
---
# \<system.identityModel.services>
<span data-ttu-id="7843a-102">WS-FEDERATION 프로토콜을 사용 하는 인증에 대 한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="7843a-102">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
## <a name="syntax"></a><span data-ttu-id="7843a-103">구문</span><span class="sxs-lookup"><span data-stu-id="7843a-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7843a-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7843a-104">Attributes and Elements</span></span>  
 <span data-ttu-id="7843a-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7843a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7843a-106">특성</span><span class="sxs-lookup"><span data-stu-id="7843a-106">Attributes</span></span>  
 <span data-ttu-id="7843a-107">None</span><span class="sxs-lookup"><span data-stu-id="7843a-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7843a-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7843a-108">Child Elements</span></span>  
  
|<span data-ttu-id="7843a-109">요소</span><span class="sxs-lookup"><span data-stu-id="7843a-109">Element</span></span>|<span data-ttu-id="7843a-110">Description</span><span class="sxs-lookup"><span data-stu-id="7843a-110">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="7843a-111"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP 모듈을 구성 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7843a-111">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7843a-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7843a-112">Parent Elements</span></span>  
 <span data-ttu-id="7843a-113">None</span><span class="sxs-lookup"><span data-stu-id="7843a-113">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7843a-114">설명</span><span class="sxs-lookup"><span data-stu-id="7843a-114">Remarks</span></span>  
 <span data-ttu-id="7843a-115">`<system.identityModel.services>`응용 프로그램의 구성 파일에 섹션을 추가 하 여 SAM 및 WSFAM에 대 한 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7843a-115">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7843a-116">또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 권한 부여를 결정 하는 데 사용 되는 클레임 권한 부여 관리자 ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) 및 정책이 `<identityConfiguration>` `<federationConfiguration>` 이 섹션의 요소에서 암시적으로 또는 명시적으로 참조 되는 요소를 통해 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7843a-116">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="7843a-117">자세한 내용은 요소 아래의 **설명을** 참조 하십시오 [\<federationConfiguration>](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="7843a-117">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="7843a-118">`<system.identityModel.services>`섹션은 클래스로 표현 됩니다 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> .</span><span class="sxs-lookup"><span data-stu-id="7843a-118">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="7843a-119">`<federationConfiguration>`섹션에서 구성 된 자식 요소의 컬렉션은 클래스로 표현 됩니다 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> .</span><span class="sxs-lookup"><span data-stu-id="7843a-119">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7843a-120">예제</span><span class="sxs-lookup"><span data-stu-id="7843a-120">Example</span></span>  
 <span data-ttu-id="7843a-121">다음 XML에서는 `<system.identityModel.services>` 구성 파일에 섹션을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7843a-121">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="7843a-122">섹션 및 섹션에 대 한 섹션 선언을 먼저 추가 해야 합니다 `<system.identityModel.services>` `<system.identityModel>` .</span><span class="sxs-lookup"><span data-stu-id="7843a-122">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="7843a-123">섹션을 추가할 때 `<system.identityModel.services>` `<system.identityModel>` 필요한 경우 런타임에서 기본 섹션을 만들 수 있도록 섹션에 대 한 선언을 추가 해야 `<identityConfiguration>` 합니다. 섹션 선언이 추가 된 후 요소 아래에서 페더레이션 인증 설정을 구성할 수 있습니다 `<system.identityModel.services>` .</span><span class="sxs-lookup"><span data-stu-id="7843a-123">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
