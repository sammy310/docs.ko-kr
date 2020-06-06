---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73973809"
---
# \<add>
<span data-ttu-id="5b828-101">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-101">Adds the specified security token handler to the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="5b828-102">구문</span><span class="sxs-lookup"><span data-stu-id="5b828-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b828-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5b828-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5b828-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b828-105">특성</span><span class="sxs-lookup"><span data-stu-id="5b828-105">Attributes</span></span>  
  
|<span data-ttu-id="5b828-106">attribute</span><span class="sxs-lookup"><span data-stu-id="5b828-106">Attribute</span></span>|<span data-ttu-id="5b828-107">Description</span><span class="sxs-lookup"><span data-stu-id="5b828-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b828-108">type</span><span class="sxs-lookup"><span data-stu-id="5b828-108">type</span></span>|<span data-ttu-id="5b828-109">추가할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-109">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="5b828-110">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b828-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b828-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5b828-111">Child Elements</span></span>  
  
|<span data-ttu-id="5b828-112">요소</span><span class="sxs-lookup"><span data-stu-id="5b828-112">Element</span></span>|<span data-ttu-id="5b828-113">Description</span><span class="sxs-lookup"><span data-stu-id="5b828-113">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="5b828-114"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-114">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|<span data-ttu-id="5b828-115">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="5b828-116">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-116">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="5b828-117">클래스 또는 파생 클래스에 대 한 선택적 구성을 제공 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-117">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b828-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5b828-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5b828-119">요소</span><span class="sxs-lookup"><span data-stu-id="5b828-119">Element</span></span>|<span data-ttu-id="5b828-120">Description</span><span class="sxs-lookup"><span data-stu-id="5b828-120">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="5b828-121">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-121">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b828-122">설명</span><span class="sxs-lookup"><span data-stu-id="5b828-122">Remarks</span></span>  
 <span data-ttu-id="5b828-123">`<add>`요소는 토큰 처리기에 대 한 구성을 지정 하는 단일 자식 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-123">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="5b828-124">이는 요소의 특성을 통해 참조 되는 처리기 클래스가 `type` 이 기능을 지원 하는지 여부에 따라 달라 집니다 `<add>` .</span><span class="sxs-lookup"><span data-stu-id="5b828-124">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="5b828-125">이 기능을 제공 하는 토큰 처리기 클래스는 개체를 사용 하는 생성자를 노출 해야 합니다 <xref:System.Xml.XmlElement> .</span><span class="sxs-lookup"><span data-stu-id="5b828-125">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="5b828-126">몇 가지 기본 제공 보안 토큰 처리기 클래스는이 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-126">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="5b828-127">이러한 클래스는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 및 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 입니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-127">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5b828-128">토큰 처리기 컬렉션에는 지정 된 형식의 단일 처리기만 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-128">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="5b828-129">예를 들어, 클래스에서 파생 된 처리기를 컬렉션에 추가 하려는 경우 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 먼저 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 컬렉션에서 기본적으로 제공 되는을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-129">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="5b828-130">요소를 사용 하 여 [\<remove>](remove.md) 컬렉션에서 단일 처리기를 제거 하거나 요소를 사용 하 여 [\<clear>](clear.md) 컬렉션에서 모든 처리기를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-130">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="5b828-131">처리기에 지정 된 설정은 요소 아래의 토큰 처리기 컬렉션에 지정 된 설정이 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) 며 요소 아래에서 서비스 수준에 지정 된 설정과 동일 하 게 재정의 [\<identityConfiguration>](identityconfiguration.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-131">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b828-132">예제</span><span class="sxs-lookup"><span data-stu-id="5b828-132">Example</span></span>  
 <span data-ttu-id="5b828-133">다음 XML에서는 `<add>` 및 요소를 사용 하 여 `<remove>` 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b828-133">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="5b828-134">XML은 샘플에서 가져옵니다 `ClaimsAwareWebFarm` .</span><span class="sxs-lookup"><span data-stu-id="5b828-134">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
