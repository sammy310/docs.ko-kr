---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251869"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="f6d84-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f6d84-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="f6d84-102">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
<span data-ttu-id="f6d84-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f6d84-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f6d84-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f6d84-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f6d84-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f6d84-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f6d84-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlers >**</span><span class="sxs-lookup"><span data-stu-id="f6d84-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6d84-107">구문</span><span class="sxs-lookup"><span data-stu-id="f6d84-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6d84-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f6d84-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f6d84-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6d84-110">특성</span><span class="sxs-lookup"><span data-stu-id="f6d84-110">Attributes</span></span>  
  
|<span data-ttu-id="f6d84-111">특성</span><span class="sxs-lookup"><span data-stu-id="f6d84-111">Attribute</span></span>|<span data-ttu-id="f6d84-112">설명</span><span class="sxs-lookup"><span data-stu-id="f6d84-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6d84-113">name</span><span class="sxs-lookup"><span data-stu-id="f6d84-113">name</span></span>|<span data-ttu-id="f6d84-114">토큰 처리기 컬렉션의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="f6d84-115">프레임 워크에서 인식 되는 값은 "ActAs" 및 "OnBehalfOf" 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="f6d84-116">이러한 이름 중 하나를 사용 하 여 토큰 처리기 컬렉션을 지정 하면 ActAs 또는 OnBehalfOf 토큰을 각각 처리할 때 컬렉션이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6d84-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f6d84-117">Child Elements</span></span>  
  
|<span data-ttu-id="f6d84-118">요소</span><span class="sxs-lookup"><span data-stu-id="f6d84-118">Element</span></span>|<span data-ttu-id="f6d84-119">설명</span><span class="sxs-lookup"><span data-stu-id="f6d84-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6d84-120">\<add></span><span class="sxs-lookup"><span data-stu-id="f6d84-120">\<add></span></span>](add.md)|<span data-ttu-id="f6d84-121">토큰 처리기 컬렉션에 보안 토큰 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="f6d84-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="f6d84-122">\<clear></span></span>](clear.md)|<span data-ttu-id="f6d84-123">토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="f6d84-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="f6d84-124">\<remove></span></span>](remove.md)|<span data-ttu-id="f6d84-125">토큰 처리기 컬렉션에서 보안 토큰 처리기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="f6d84-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f6d84-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="f6d84-127">토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6d84-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f6d84-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f6d84-129">요소</span><span class="sxs-lookup"><span data-stu-id="f6d84-129">Element</span></span>|<span data-ttu-id="f6d84-130">설명</span><span class="sxs-lookup"><span data-stu-id="f6d84-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6d84-131">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f6d84-131">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="f6d84-132">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6d84-133">설명</span><span class="sxs-lookup"><span data-stu-id="f6d84-133">Remarks</span></span>  
 <span data-ttu-id="f6d84-134">서비스 구성에서 보안 토큰 처리기의 명명 된 컬렉션을 하나 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="f6d84-135">특성을 `name` 사용 하 여 컬렉션의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="f6d84-136">프레임 워크를 처리 하는 유일한 이름에는 "ActAs" 및 "OnBehalfOf"입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="f6d84-137">이러한 컬렉션에 처리기가 있는 경우 및 토큰을 처리 `ActAs` 하 `OnBehalfOf` 는 경우 기본 처리기 대신 STS (보안 토큰 서비스)에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="f6d84-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>기본적으로 컬렉션은 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ,<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> ,,<xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>및 처리기 형식으로 채워집니다. <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="f6d84-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="f6d84-139">`<add>` ,`<remove>`및 요소`<clear>` 를 사용 하 여 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="f6d84-140">컬렉션에 특정 형식의 처리기가 하나만 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="f6d84-141">예를 들어 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스에서 처리기를 파생 하는 경우 처리기 또는는 단일 컬렉션에서 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 구성 될 수 있지만 둘 다로 구성 될 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="f6d84-142">`<securityTokenHandlerConfiguration>` 요소를 사용 하 여 컬렉션의 처리기에 대 한 구성 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="f6d84-143">이 요소를 통해 지정 된 설정은 [ \<identityConfiguration >](identityconfiguration.md) 요소를 통해 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="f6d84-144">일부 처리기 (몇 가지 기본 제공 처리기 형식 포함)는 `<add>` 요소의 자식 요소를 통해 추가 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="f6d84-145">처리기에 지정 된 설정이 컬렉션 또는 서비스에 지정 된 것과 동일한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d84-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
