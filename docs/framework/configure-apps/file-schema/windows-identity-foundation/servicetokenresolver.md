---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923100"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="4d56e-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="4d56e-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="4d56e-102">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="4d56e-103">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="4d56e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4d56e-104">\<system.identityModel></span></span>  
<span data-ttu-id="4d56e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4d56e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="4d56e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4d56e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4d56e-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="4d56e-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="4d56e-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="4d56e-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d56e-109">구문</span><span class="sxs-lookup"><span data-stu-id="4d56e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d56e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4d56e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d56e-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d56e-112">특성</span><span class="sxs-lookup"><span data-stu-id="4d56e-112">Attributes</span></span>  
  
|<span data-ttu-id="4d56e-113">특성</span><span class="sxs-lookup"><span data-stu-id="4d56e-113">Attribute</span></span>|<span data-ttu-id="4d56e-114">Description</span><span class="sxs-lookup"><span data-stu-id="4d56e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d56e-115">type</span><span class="sxs-lookup"><span data-stu-id="4d56e-115">type</span></span>|<span data-ttu-id="4d56e-116">서비스 토큰 확인자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="4d56e-117">형식 또는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생 되는 형식입니다. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="4d56e-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="4d56e-118">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d56e-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="4d56e-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="4d56e-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d56e-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4d56e-120">Child Elements</span></span>  
 <span data-ttu-id="4d56e-121">없음</span><span class="sxs-lookup"><span data-stu-id="4d56e-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d56e-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4d56e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4d56e-123">요소</span><span class="sxs-lookup"><span data-stu-id="4d56e-123">Element</span></span>|<span data-ttu-id="4d56e-124">Description</span><span class="sxs-lookup"><span data-stu-id="4d56e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d56e-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="4d56e-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="4d56e-126">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d56e-127">설명</span><span class="sxs-lookup"><span data-stu-id="4d56e-127">Remarks</span></span>  
 <span data-ttu-id="4d56e-128">서비스 토큰 확인자를 사용 하 여 들어오는 토큰과 메시지의 암호화 토큰을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="4d56e-129">들어오는 토큰의 암호를 해독 하는 데 사용 되는 키를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="4d56e-130">특성을 `type` 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="4d56e-131">지정 된 형식은 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 이거나 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스에서 파생 되는 사용자 지정 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="4d56e-132">일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="4d56e-133">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d56e-134">IdentityConfiguration > 요소의 자식 요소로 `<serviceTokenResolver>` [요소를 지정 하는 것은 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 \<](identityconfiguration.md) 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d56e-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="4d56e-135">요소의 설정은 `<identityConfiguration>` 요소의 설정을 재정의 합니다. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="4d56e-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d56e-136">예제</span><span class="sxs-lookup"><span data-stu-id="4d56e-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
