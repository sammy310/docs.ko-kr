---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251845"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="5ac96-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="5ac96-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="5ac96-102">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5ac96-103">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="5ac96-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac96-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5ac96-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5ac96-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5ac96-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5ac96-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5ac96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="5ac96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="5ac96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5ac96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="5ac96-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="5ac96-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac96-110">구문</span><span class="sxs-lookup"><span data-stu-id="5ac96-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ac96-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5ac96-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5ac96-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ac96-113">특성</span><span class="sxs-lookup"><span data-stu-id="5ac96-113">Attributes</span></span>  
  
|<span data-ttu-id="5ac96-114">특성</span><span class="sxs-lookup"><span data-stu-id="5ac96-114">Attribute</span></span>|<span data-ttu-id="5ac96-115">Description</span><span class="sxs-lookup"><span data-stu-id="5ac96-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ac96-116">type</span><span class="sxs-lookup"><span data-stu-id="5ac96-116">type</span></span>|<span data-ttu-id="5ac96-117">서비스 토큰 확인자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="5ac96-118">형식 또는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생 되는 형식입니다. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="5ac96-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="5ac96-119">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ac96-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="5ac96-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5ac96-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ac96-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ac96-121">Child Elements</span></span>  
 <span data-ttu-id="5ac96-122">없음</span><span class="sxs-lookup"><span data-stu-id="5ac96-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ac96-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ac96-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5ac96-124">요소</span><span class="sxs-lookup"><span data-stu-id="5ac96-124">Element</span></span>|<span data-ttu-id="5ac96-125">Description</span><span class="sxs-lookup"><span data-stu-id="5ac96-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ac96-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="5ac96-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="5ac96-127">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ac96-128">설명</span><span class="sxs-lookup"><span data-stu-id="5ac96-128">Remarks</span></span>  
 <span data-ttu-id="5ac96-129">서비스 토큰 확인자를 사용 하 여 들어오는 토큰과 메시지의 암호화 토큰을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="5ac96-130">들어오는 토큰의 암호를 해독 하는 데 사용 되는 키를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="5ac96-131">특성을 `type` 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="5ac96-132">지정 된 형식은 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 이거나 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생 되는 사용자 지정 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="5ac96-133">일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="5ac96-134">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ac96-135">IdentityConfiguration > 요소의 자식 요소로 `<serviceTokenResolver>` [요소를 지정 하는 것은 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 \<](identityconfiguration.md) 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ac96-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="5ac96-136">요소의 설정은 `<identityConfiguration>` 요소의 설정을 재정의 합니다. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="5ac96-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ac96-137">예제</span><span class="sxs-lookup"><span data-stu-id="5ac96-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 