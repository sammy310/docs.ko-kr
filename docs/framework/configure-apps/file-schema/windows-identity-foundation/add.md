---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 9505970c1fd7fcdfe62d3c6ef58f5d653fab4106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941988"
---
# <a name="add"></a><span data-ttu-id="3a003-101">\<add></span><span class="sxs-lookup"><span data-stu-id="3a003-101">\<add></span></span>
<span data-ttu-id="3a003-102">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="3a003-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3a003-103">\<system.identityModel></span></span>  
<span data-ttu-id="3a003-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a003-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3a003-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3a003-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3a003-106">\<add></span><span class="sxs-lookup"><span data-stu-id="3a003-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a003-107">구문</span><span class="sxs-lookup"><span data-stu-id="3a003-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a003-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3a003-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3a003-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a003-110">특성</span><span class="sxs-lookup"><span data-stu-id="3a003-110">Attributes</span></span>  
  
|<span data-ttu-id="3a003-111">특성</span><span class="sxs-lookup"><span data-stu-id="3a003-111">Attribute</span></span>|<span data-ttu-id="3a003-112">Description</span><span class="sxs-lookup"><span data-stu-id="3a003-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a003-113">type</span><span class="sxs-lookup"><span data-stu-id="3a003-113">type</span></span>|<span data-ttu-id="3a003-114">추가할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="3a003-115">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a003-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a003-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3a003-116">Child Elements</span></span>  
  
|<span data-ttu-id="3a003-117">요소</span><span class="sxs-lookup"><span data-stu-id="3a003-117">Element</span></span>|<span data-ttu-id="3a003-118">Description</span><span class="sxs-lookup"><span data-stu-id="3a003-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a003-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3a003-119">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="3a003-120"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="3a003-121">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3a003-121">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="3a003-122"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="3a003-123">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="3a003-123">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="3a003-124"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="3a003-125">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="3a003-125">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="3a003-126"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 선택적 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a003-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3a003-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3a003-128">요소</span><span class="sxs-lookup"><span data-stu-id="3a003-128">Element</span></span>|<span data-ttu-id="3a003-129">설명</span><span class="sxs-lookup"><span data-stu-id="3a003-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a003-130">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3a003-130">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="3a003-131">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a003-132">설명</span><span class="sxs-lookup"><span data-stu-id="3a003-132">Remarks</span></span>  
 <span data-ttu-id="3a003-133">요소 `<add>` 는 토큰 처리기에 대 한 구성을 지정 하는 단일 자식 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="3a003-134">이는 `type` `<add>` 요소의 특성을 통해 참조 되는 처리기 클래스가이 기능을 지원 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="3a003-135">이 기능을 제공 하는 토큰 처리기 클래스는 <xref:System.Xml.XmlElement> 개체를 사용 하는 생성자를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="3a003-136">몇 가지 기본 제공 보안 토큰 처리기 클래스는이 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="3a003-137">이러한 클래스는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ,<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, 및<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>입니다. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="3a003-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3a003-138">토큰 처리기 컬렉션에는 지정 된 형식의 단일 처리기만 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="3a003-139">예를 들어, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스에서 파생 된 처리기를 컬렉션에 추가 하려는 경우 먼저 컬렉션에서 기본적으로 제공 되는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="3a003-140">[ \<](clear.md) Remove > 요소를 사용 [ \<](remove.md) 하 여 컬렉션에서 단일 처리기를 제거 하거나 clear > 요소를 사용 하 여 컬렉션에서 모든 처리기를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-140">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="3a003-141">처리기에 지정 된 설정은 [ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md) 요소 아래의 토큰 처리기 컬렉션에 지정 된 것과 동일한 설정을 재정의 하 고 다음의 서비스 수준에서 지정 된 [ \< 설정을 재정의 합니다. identityConfiguration >](identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a003-142">예제</span><span class="sxs-lookup"><span data-stu-id="3a003-142">Example</span></span>  
 <span data-ttu-id="3a003-143">다음 XML에서는 `<add>` 및 `<remove>` 요소를 사용 하 여 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="3a003-144">XML은 `ClaimsAwareWebFarm` 샘플에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a003-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
