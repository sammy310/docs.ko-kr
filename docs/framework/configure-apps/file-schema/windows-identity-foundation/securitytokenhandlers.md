---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: a5af3893ab72d23c2b3814569decfc50431b8e55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793837"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="09253-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="09253-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="09253-102">끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="09253-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="09253-103">\<system.identityModel></span></span>  
<span data-ttu-id="09253-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="09253-104">\<identityConfiguration></span></span>  
<span data-ttu-id="09253-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="09253-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09253-106">구문</span><span class="sxs-lookup"><span data-stu-id="09253-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09253-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="09253-107">Attributes and Elements</span></span>  
 <span data-ttu-id="09253-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09253-109">특성</span><span class="sxs-lookup"><span data-stu-id="09253-109">Attributes</span></span>  
  
|<span data-ttu-id="09253-110">특성</span><span class="sxs-lookup"><span data-stu-id="09253-110">Attribute</span></span>|<span data-ttu-id="09253-111">설명</span><span class="sxs-lookup"><span data-stu-id="09253-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09253-112">name</span><span class="sxs-lookup"><span data-stu-id="09253-112">name</span></span>|<span data-ttu-id="09253-113">토큰 처리기 컬렉션의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="09253-114">프레임 워크에서 인식 유일한 값은 "ActAs" 및 "OnBehalfOf"입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="09253-115">토큰 처리기 컬렉션은 이러한 이름 중 하나를 사용 하 여 지정 된 경우에 각각 토큰 ActAs 또는 OnBehalfOf를 처리 하는 경우 컬렉션 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09253-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09253-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="09253-116">Child Elements</span></span>  
  
|<span data-ttu-id="09253-117">요소</span><span class="sxs-lookup"><span data-stu-id="09253-117">Element</span></span>|<span data-ttu-id="09253-118">설명</span><span class="sxs-lookup"><span data-stu-id="09253-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09253-119">\<add></span><span class="sxs-lookup"><span data-stu-id="09253-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="09253-120">토큰 처리기 컬렉션에는 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="09253-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="09253-121">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="09253-122">토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="09253-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="09253-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="09253-123">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="09253-124">토큰 처리기 컬렉션에서 보안 토큰 처리기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="09253-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="09253-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="09253-126">토큰 처리기 컬렉션에 대 한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09253-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="09253-127">Parent Elements</span></span>  
  
|<span data-ttu-id="09253-128">요소</span><span class="sxs-lookup"><span data-stu-id="09253-128">Element</span></span>|<span data-ttu-id="09253-129">설명</span><span class="sxs-lookup"><span data-stu-id="09253-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09253-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="09253-130">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="09253-131">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09253-132">설명</span><span class="sxs-lookup"><span data-stu-id="09253-132">Remarks</span></span>  
 <span data-ttu-id="09253-133">서비스 구성에서 하나 이상의 명명 된 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09253-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="09253-134">사용 하 여 컬렉션의 이름을 지정할 수 있습니다는 `name` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="09253-135">프레임 워크를 처리 하는 유일한 이름에는 "ActAs" 및 "OnBehalfOf"입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="09253-136">이러한 컬렉션의 처리기가 없는 경우 사용할 보안 토큰 서비스 (STS)에서 기본 처리기를 대신 처리 하는 동안 `ActAs` 고 `OnBehalfOf` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="09253-137">기본적으로 컬렉션 채워집니다 처리기 형식은: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>를 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="09253-138">사용 하 여 컬렉션을 수정할 수는 `<add>`, `<remove>`, 및 `<clear>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="09253-139">특정 형식의 단일 처리기만 컬렉션에 있는지를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="09253-140">예를 들어에서 처리기를 파생 하는 경우는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 하거나 클래스 처리기 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 단일 컬렉션, 하지만 둘 다에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09253-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="09253-141">사용 된 `<securityTokenHandlerConfiguration>` 컬렉션의 처리기에 대 한 구성 설정을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="09253-142">이 요소를 통해 지정 된 설정을 재정의 통해 서비스에 지정 된 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="09253-143">일부 처리기 (몇 가지 기본 제공 처리기 형식을 포함)의 자식 요소를 통해 추가 구성을 지원할 수는 `<add>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09253-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="09253-144">처리기에 지정 된 설정은 컬렉션 또는 서비스에서 지정 된 해당 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="09253-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
