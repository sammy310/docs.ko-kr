---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 9728f3caee4dba367e4fc4a3e68213b1055cc3d1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362957"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="91b69-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="91b69-102">\<system.identityModel.services></span></span>
<span data-ttu-id="91b69-103">Ws-federation 프로토콜을 사용 하 여 인증에 대 한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="91b69-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="91b69-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b69-105">구문</span><span class="sxs-lookup"><span data-stu-id="91b69-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91b69-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91b69-106">Attributes and Elements</span></span>  
 <span data-ttu-id="91b69-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91b69-108">특성</span><span class="sxs-lookup"><span data-stu-id="91b69-108">Attributes</span></span>  
 <span data-ttu-id="91b69-109">없음</span><span class="sxs-lookup"><span data-stu-id="91b69-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91b69-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91b69-110">Child Elements</span></span>  
  
|<span data-ttu-id="91b69-111">요소</span><span class="sxs-lookup"><span data-stu-id="91b69-111">Element</span></span>|<span data-ttu-id="91b69-112">설명</span><span class="sxs-lookup"><span data-stu-id="91b69-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91b69-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="91b69-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="91b69-114">구성 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91b69-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91b69-115">Parent Elements</span></span>  
 <span data-ttu-id="91b69-116">없음</span><span class="sxs-lookup"><span data-stu-id="91b69-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91b69-117">설명</span><span class="sxs-lookup"><span data-stu-id="91b69-117">Remarks</span></span>  
 <span data-ttu-id="91b69-118">추가 된 `<system.identityModel.services>` SAM 및 WSFAM에 대 한 설정을 제공 하려면 응용 프로그램의 구성 파일 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91b69-119">사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클레임 인증 관리자 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스 (<xref:System.Security.Claims.ClaimsAuthorizationManager>) 및 권한 부여 결정 하는 데 사용 되는 정책을 통해 구성 됩니다는 `<identityConfiguration>` 암시적 또는 명시적으로 참조 하는 요소는 `<federationConfiguration>` 이 섹션에 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="91b69-120">자세한 내용은 참조 하세요. 합니다 **주의** 아래 합니다 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="91b69-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="91b69-121">`<system.identityModel.services>` 섹션은 표현 된 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="91b69-122">자식 컬렉션인 `<federationConfiguration>` 섹션에 구성 요소에서 표시 됩니다는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b69-123">예제</span><span class="sxs-lookup"><span data-stu-id="91b69-123">Example</span></span>  
 <span data-ttu-id="91b69-124">다음 XML에 추가 하는 방법을 보여 줍니다는 `<system.identityModel.services>` 구성 파일 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="91b69-125">둘 다에 대 한 섹션 선언을 추가 해야 합니다 `<system.identityModel.services>` 섹션 및 `<system.identityModel>` 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="91b69-126">(추가 하는 경우는 `<system.identityModel.services>` 섹션도 추가 해야에 대 한 선언을 합니다 `<system.identityModel>` 기본값 되도록 섹션 `<identityConfiguration>` 필요한 경우 런타임에서 섹션을 만들 수 있습니다.) 선언 섹션에 추가한 후 아래에 있는 페더레이션된 인증 설정을 구성할 수 있습니다는 `<system.identityModel.services>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91b69-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
