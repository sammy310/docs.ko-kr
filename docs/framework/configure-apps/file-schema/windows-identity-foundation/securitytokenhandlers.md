---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: d892fbd802ed366ca7af9b85fbf5c23d4d27e0f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157007"
---
# \<securityTokenHandlers>

<span data-ttu-id="85aa2-101">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-101">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a><span data-ttu-id="85aa2-102">구문</span><span class="sxs-lookup"><span data-stu-id="85aa2-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85aa2-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="85aa2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="85aa2-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85aa2-105">특성</span><span class="sxs-lookup"><span data-stu-id="85aa2-105">Attributes</span></span>  
  
|<span data-ttu-id="85aa2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="85aa2-106">Attribute</span></span>|<span data-ttu-id="85aa2-107">Description</span><span class="sxs-lookup"><span data-stu-id="85aa2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85aa2-108">name</span><span class="sxs-lookup"><span data-stu-id="85aa2-108">name</span></span>|<span data-ttu-id="85aa2-109">토큰 처리기 컬렉션의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-109">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="85aa2-110">프레임 워크에서 인식 되는 값은 "ActAs" 및 "OnBehalfOf" 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-110">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="85aa2-111">이러한 이름 중 하나를 사용 하 여 토큰 처리기 컬렉션을 지정 하면 ActAs 또는 OnBehalfOf 토큰을 각각 처리할 때 컬렉션이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-111">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85aa2-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="85aa2-112">Child Elements</span></span>  
  
|<span data-ttu-id="85aa2-113">요소</span><span class="sxs-lookup"><span data-stu-id="85aa2-113">Element</span></span>|<span data-ttu-id="85aa2-114">설명</span><span class="sxs-lookup"><span data-stu-id="85aa2-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="85aa2-115">토큰 처리기 컬렉션에 보안 토큰 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-115">Adds a security token handler to the token handler collection.</span></span>|  
|[\<clear>](clear.md)|<span data-ttu-id="85aa2-116">토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-116">Clears all security token handlers from the token handler collection.</span></span>|  
|[\<remove>](remove.md)|<span data-ttu-id="85aa2-117">토큰 처리기 컬렉션에서 보안 토큰 처리기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-117">Removes a security token handler from the token handler collection.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="85aa2-118">토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-118">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85aa2-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="85aa2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="85aa2-120">요소</span><span class="sxs-lookup"><span data-stu-id="85aa2-120">Element</span></span>|<span data-ttu-id="85aa2-121">설명</span><span class="sxs-lookup"><span data-stu-id="85aa2-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="85aa2-122">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85aa2-123">설명</span><span class="sxs-lookup"><span data-stu-id="85aa2-123">Remarks</span></span>  

 <span data-ttu-id="85aa2-124">서비스 구성에서 보안 토큰 처리기의 명명 된 컬렉션을 하나 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-124">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="85aa2-125">특성을 사용 하 여 컬렉션의 이름을 지정할 수 있습니다 `name` .</span><span class="sxs-lookup"><span data-stu-id="85aa2-125">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="85aa2-126">프레임 워크를 처리 하는 유일한 이름에는 "ActAs" 및 "OnBehalfOf"입니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-126">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="85aa2-127">이러한 컬렉션에 처리기가 있는 경우 및 토큰을 처리 하는 경우 기본 처리기 대신 STS (보안 토큰 서비스)에서 사용 `ActAs` 됩니다 `OnBehalfOf` .</span><span class="sxs-lookup"><span data-stu-id="85aa2-127">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="85aa2-128">기본적으로 컬렉션은,,,,, 및 처리기 형식으로 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 채워집니다 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="85aa2-128">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="85aa2-129">`<add>`, 및 요소를 사용 하 여 컬렉션을 수정할 수 있습니다 `<remove>` `<clear>` .</span><span class="sxs-lookup"><span data-stu-id="85aa2-129">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="85aa2-130">컬렉션에 특정 형식의 처리기가 하나만 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-130">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="85aa2-131">예를 들어 클래스에서 처리기를 파생 하는 경우 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 처리기 또는는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 단일 컬렉션에서 구성 될 수 있지만 둘 다로 구성 될 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-131">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="85aa2-132">요소를 사용 `<securityTokenHandlerConfiguration>` 하 여 컬렉션의 처리기에 대 한 구성 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-132">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="85aa2-133">이 요소를 통해 지정 된 설정은 요소를 통해 서비스에 지정 된 설정을 재정의 [\<identityConfiguration>](identityconfiguration.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-133">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="85aa2-134">일부 처리기 (몇 가지 기본 제공 처리기 형식 포함)는 요소의 자식 요소를 통해 추가 구성을 지원할 수 있습니다 `<add>` .</span><span class="sxs-lookup"><span data-stu-id="85aa2-134">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="85aa2-135">처리기에 지정 된 설정이 컬렉션 또는 서비스에 지정 된 것과 동일한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85aa2-135">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
