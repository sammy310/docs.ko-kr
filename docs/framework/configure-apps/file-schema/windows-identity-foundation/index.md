---
title: Windows Identity Foundation 구성 스키마
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 8dc58f3dc68ee226228056e457914c9dfa53cca5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251973"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="91644-102">Windows Identity Foundation 구성 스키마</span><span class="sxs-lookup"><span data-stu-id="91644-102">Windows Identity Foundation Configuration Schema</span></span>

<span data-ttu-id="91644-103">이 섹션의 항목에서는 WIF(Windows Identity Foundation) 구성 스키마에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91644-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="91644-104">프레임 워크에서 노출 하는 클래스를 통해 WIF를 사용 하도록 응용 프로그램을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91644-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="91644-105">이러한 클래스는 스키마의 관련 요소를 다루는 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91644-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="91644-106">다음은 WIF 구성 스키마에 의해 노출된 기본 XML 태그 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91644-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="91644-107">특성은 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="91644-107">Attributes are omitted.</span></span> <span data-ttu-id="91644-108">강조 표시된 주석은 스키마의 주요 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91644-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
<configuration>  
    <system.identityModel>  
        <!-- Service Configuration -->  
        <identityConfiguration>  
            <caches>  
                <sessionSecurityTokenCache />  
                <tokenReplayCache />  
            </caches>  
      
            <certificateValidation>  
                <certificateValidator />   
            </certificateValidation>  
      
            <claimsAuthenticationManager />  
      
            <claimsAuthorizationManager>  
                <optionalConfigurationElement>  
            </claimsAuthorizationManager>  
      
            <claimTypeRequired>  
                <claimType />   
            </claimTypeRequired>  
      
            <tokenReplayDetection />  
      
            <!-- Security Token Handler Collection Configuration -->  
            <securityTokenHandlers>  
                <add>  
                    <!-- Can take an optional configuration element which can be one of  
                         the following or a custom element -->  
                    <samlSecurityTokenHandlerRequirement>  
                        <nameClaimType>  
                        <roleClaimType>   
                    </samlSecurityTokenHandlerRequirement>  
      
                    <sessionSecurityTokenHandlerRequirement />  
                    <x509SecurityTokenHandlerRequirement />  
                    <userNameSecurityTokenHandlerRequirement />  
                </add>  
                <clear />  
                <remove />  
                <securityTokenHandlerConfiguration>  
                    <audienceUris>  
                        <add>  
                        <clear>  
                        <remove>  
                    </audienceUris>  
      
                    <caches>  
                        <sessionSecurityTokenCache />  
                        <tokenReplayCache />  
                    </caches>  
      
                    <certificateValidation>  
                        <certificateValidator>   
                    </certificateValidation>  
      
                    <issuerNameRegistry>  
                        <!-- Can take an optional configuration element which can be   
                             the <trustedIssuers> element to configure a configuration-based  
                             issuer name registry or can be a custom element -->  
                        <trustedIssuers>  
                            <add>  
                            <clear>  
                            <remove>  
                        </trustedIssuers>  
                    </issuerNameRegistry>  
      
                    <issuerTokenResolver />  
                    <serviceTokenResolver />  
                    <tokenReplayDetection />  
                </securityTokenHandlerConfiguration>  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
      
    <system.identityModel.services>  
        <!-- Federation Authentication Configuration -->  
        <federatedAuthentication>  
            <cookieHandler>  
                <chunkedCookieHandler />  
                <customCookieHandler />  
            </cookieHandler>  
      
            <serviceCertificate>  
                <certificateReference>  
            </serviceCertificate>  
      
            <wsFederation />  
        </federatedAuthentication>  
    </system.identityModel.services>  
</configuration>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="91644-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="91644-109">In This Section</span></span>  

<span data-ttu-id="91644-110">[\<system.identityModel&gt;](system-identitymodel.md) 애플리케이션에서 WIF 옵션을 활성화하는 데 필요한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91644-110">[\<system.identityModel>](system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
<span data-ttu-id="91644-111">[\<system.identityModel.services>](system-identitymodel-services.md) WIF를 사용하는 수동 페더레이션에 대한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91644-111">[\<system.identityModel.services>](system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="91644-112">SAM(Session Authentication Module) 및 WSFAM(Federated Authentication Module)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="91644-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>
