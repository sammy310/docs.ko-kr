---
description: '자세한 정보: Windows Identity Foundation 구성 스키마'
title: Windows Identity Foundation 구성 스키마
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 926b2dbe25359ebc789c95f75a59090c7e5a52e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725339"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="96228-103">Windows Identity Foundation 구성 스키마</span><span class="sxs-lookup"><span data-stu-id="96228-103">Windows Identity Foundation Configuration Schema</span></span>

<span data-ttu-id="96228-104">이 섹션의 항목에서는 WIF(Windows Identity Foundation) 구성 스키마에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96228-104">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="96228-105">프레임 워크에서 노출 하는 클래스를 통해 WIF를 사용 하도록 응용 프로그램을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96228-105">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="96228-106">이러한 클래스는 스키마의 관련 요소를 다루는 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96228-106">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="96228-107">다음은 WIF 구성 스키마에 의해 노출된 기본 XML 태그 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96228-107">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="96228-108">특성은 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="96228-108">Attributes are omitted.</span></span> <span data-ttu-id="96228-109">강조 표시된 주석은 스키마의 주요 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96228-109">Highlighted comments indicate major components of the schema.</span></span>  
  
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
  
## <a name="in-this-section"></a><span data-ttu-id="96228-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="96228-110">In This Section</span></span>  

<span data-ttu-id="96228-111">[\<system.identityModel>](system-identitymodel.md) 응용 프로그램에서 WIF 옵션을 사용 하기 위한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96228-111">[\<system.identityModel>](system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
<span data-ttu-id="96228-112">[\<system.identityModel.services>](system-identitymodel-services.md) WIF를 사용 하 여 수동 페더레이션을 위한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96228-112">[\<system.identityModel.services>](system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="96228-113">SAM(Session Authentication Module) 및 WSFAM(Federated Authentication Module)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="96228-113">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>
