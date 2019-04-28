---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793811"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="19bc4-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="19bc4-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="19bc4-102">토큰 처리기 컬렉션의 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="19bc4-103">서비스 토큰 확인자는 들어오는 토큰에 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="19bc4-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="19bc4-104">\<system.identityModel></span></span>  
<span data-ttu-id="19bc4-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="19bc4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="19bc4-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="19bc4-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="19bc4-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="19bc4-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="19bc4-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="19bc4-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19bc4-109">구문</span><span class="sxs-lookup"><span data-stu-id="19bc4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19bc4-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19bc4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19bc4-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19bc4-112">특성</span><span class="sxs-lookup"><span data-stu-id="19bc4-112">Attributes</span></span>  
  
|<span data-ttu-id="19bc4-113">특성</span><span class="sxs-lookup"><span data-stu-id="19bc4-113">Attribute</span></span>|<span data-ttu-id="19bc4-114">설명</span><span class="sxs-lookup"><span data-stu-id="19bc4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19bc4-115">type</span><span class="sxs-lookup"><span data-stu-id="19bc4-115">type</span></span>|<span data-ttu-id="19bc4-116">서비스 토큰 확인자 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="19bc4-117">중 하나는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 형식 또는 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="19bc4-118">지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19bc4-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="19bc4-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="19bc4-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19bc4-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19bc4-120">Child Elements</span></span>  
 <span data-ttu-id="19bc4-121">없음</span><span class="sxs-lookup"><span data-stu-id="19bc4-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19bc4-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19bc4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="19bc4-123">요소</span><span class="sxs-lookup"><span data-stu-id="19bc4-123">Element</span></span>|<span data-ttu-id="19bc4-124">설명</span><span class="sxs-lookup"><span data-stu-id="19bc4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19bc4-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="19bc4-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="19bc4-126">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19bc4-127">설명</span><span class="sxs-lookup"><span data-stu-id="19bc4-127">Remarks</span></span>  
 <span data-ttu-id="19bc4-128">들어오는 토큰에 메시지 암호화 토큰을 확인 하려면 서비스 토큰 확인자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="19bc4-129">들어오는 토큰 암호 해독에 사용 해야 하는 키를 검색 하는 것이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="19bc4-130">지정 해야 합니다 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="19bc4-131">지정 된 형식의 일 수 있습니다 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="19bc4-132">일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="19bc4-133">개별 토큰 처리기에 설정 된 보안 토큰 처리기 컬렉션에서 지정 된 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19bc4-134">지정 된 `<serviceTokenResolver>` 의 자식 요소로 요소를 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소에 사용 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="19bc4-135">설정 합니다 `<securityTokenHandlerConfiguration>` 요소에 있는 구성을 재정의 `<identityConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19bc4-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19bc4-136">예제</span><span class="sxs-lookup"><span data-stu-id="19bc4-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
