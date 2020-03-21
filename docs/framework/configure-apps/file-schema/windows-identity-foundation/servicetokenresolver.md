---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152582"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="e1fea-101">\<서비스토큰해결러></span><span class="sxs-lookup"><span data-stu-id="e1fea-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="e1fea-102">토큰 처리기 컬렉션의 처리기에서 사용되는 서비스 토큰 확인자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e1fea-103">서비스 토큰 확인기는 들어오는 토큰 및 메시지에서 암호화 토큰을 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="e1fea-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1fea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1fea-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e1fea-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e1fea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e1fea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e1fea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e1fea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e1fea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기구성>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e1fea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="e1fea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<서비스토큰 해결사>**</span><span class="sxs-lookup"><span data-stu-id="e1fea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fea-110">구문</span><span class="sxs-lookup"><span data-stu-id="e1fea-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1fea-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e1fea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e1fea-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1fea-113">특성</span><span class="sxs-lookup"><span data-stu-id="e1fea-113">Attributes</span></span>  
  
|<span data-ttu-id="e1fea-114">attribute</span><span class="sxs-lookup"><span data-stu-id="e1fea-114">Attribute</span></span>|<span data-ttu-id="e1fea-115">Description</span><span class="sxs-lookup"><span data-stu-id="e1fea-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1fea-116">type</span><span class="sxs-lookup"><span data-stu-id="e1fea-116">type</span></span>|<span data-ttu-id="e1fea-117">서비스 토큰 확인자의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="e1fea-118"><xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생되는 형식 또는 형식입니다. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="e1fea-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="e1fea-119">`type` 특성을 지정하는 방법에 대한 자세한 내용은 [사용자 지정 유형 참조]를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1fea-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="e1fea-120">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1fea-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e1fea-121">Child Elements</span></span>  
 <span data-ttu-id="e1fea-122">None</span><span class="sxs-lookup"><span data-stu-id="e1fea-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1fea-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e1fea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e1fea-124">요소</span><span class="sxs-lookup"><span data-stu-id="e1fea-124">Element</span></span>|<span data-ttu-id="e1fea-125">Description</span><span class="sxs-lookup"><span data-stu-id="e1fea-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1fea-126">\<보안토큰처리기구성></span><span class="sxs-lookup"><span data-stu-id="e1fea-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e1fea-127">보안 토큰 처리기 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1fea-128">설명</span><span class="sxs-lookup"><span data-stu-id="e1fea-128">Remarks</span></span>  
 <span data-ttu-id="e1fea-129">서비스 토큰 확인자를 사용하여 들어오는 토큰 및 메시지에서 암호화 토큰을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="e1fea-130">들어오는 토큰의 암호를 해독하는 데 사용해야 하는 키를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="e1fea-131">특성을 `type` 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="e1fea-132">지정된 형식은 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생되는 사용자 지정 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e1fea-133">일부 토큰 처리기를 사용하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="e1fea-134">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정된 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1fea-135">idConfiguration>요소의 자식 요소로 요소를 지정 하는 데 사용 하지 않습니다. [ \<](identityconfiguration.md) `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="e1fea-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e1fea-136">요소의 `<securityTokenHandlerConfiguration>` 설정은 요소의 `<identityConfiguration>` 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fea-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1fea-137">예제</span><span class="sxs-lookup"><span data-stu-id="e1fea-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
