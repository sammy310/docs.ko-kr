---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 216b4c73e06469d6577c61338ad1af0fdd2dc05e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185576"
---
# \<system.identityModel>

<span data-ttu-id="e77cc-102">응용 프로그램에서 WIF (Windows Identity Foundation) 옵션을 사용 하도록 구성 하는 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-102">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a><span data-ttu-id="e77cc-103">구문</span><span class="sxs-lookup"><span data-stu-id="e77cc-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e77cc-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e77cc-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e77cc-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e77cc-106">특성</span><span class="sxs-lookup"><span data-stu-id="e77cc-106">Attributes</span></span>  

 <span data-ttu-id="e77cc-107">없음</span><span class="sxs-lookup"><span data-stu-id="e77cc-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e77cc-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e77cc-108">Child Elements</span></span>  
  
|<span data-ttu-id="e77cc-109">요소</span><span class="sxs-lookup"><span data-stu-id="e77cc-109">Element</span></span>|<span data-ttu-id="e77cc-110">설명</span><span class="sxs-lookup"><span data-stu-id="e77cc-110">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="e77cc-111">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-111">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e77cc-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e77cc-112">Parent Elements</span></span>  
  
|<span data-ttu-id="e77cc-113">요소</span><span class="sxs-lookup"><span data-stu-id="e77cc-113">Element</span></span>|<span data-ttu-id="e77cc-114">설명</span><span class="sxs-lookup"><span data-stu-id="e77cc-114">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="e77cc-115">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e77cc-116">설명</span><span class="sxs-lookup"><span data-stu-id="e77cc-116">Remarks</span></span>  

 <span data-ttu-id="e77cc-117">`<system.identityModel>`구성 파일에 섹션을 추가 하 여 WIF (Windows Identity Foundation)를 사용 하도록 서비스 또는 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-117">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="e77cc-118">합니다 `<system.identityModel>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-118">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e77cc-119">예제</span><span class="sxs-lookup"><span data-stu-id="e77cc-119">Example</span></span>  

 <span data-ttu-id="e77cc-120">다음 예제에서는 `<system.identityModel>` 구성 파일에 섹션을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-120">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="e77cc-121">먼저 요소 아래에 구성 섹션과 네임 스페이스 선언을 추가 해야 합니다 `<configSections>` .</span><span class="sxs-lookup"><span data-stu-id="e77cc-121">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="e77cc-122">그런 다음 `<system.IdentityModel>` 구성 파일에 요소를 추가 하 여 하나 이상의 id 구성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77cc-122">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e77cc-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e77cc-123">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
