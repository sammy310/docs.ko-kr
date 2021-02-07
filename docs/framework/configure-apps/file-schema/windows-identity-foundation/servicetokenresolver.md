---
description: 다음에 대해 자세히 알아보세요. <serviceTokenResolver>
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: ab24c92eee43324365adb3bb3a64c8a765017a53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698299"
---
# \<serviceTokenResolver>

<span data-ttu-id="60893-102">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60893-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="60893-103">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60893-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="60893-104">구문</span><span class="sxs-lookup"><span data-stu-id="60893-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60893-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60893-105">Attributes and Elements</span></span>  

 <span data-ttu-id="60893-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60893-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60893-107">특성</span><span class="sxs-lookup"><span data-stu-id="60893-107">Attributes</span></span>  
  
|<span data-ttu-id="60893-108">attribute</span><span class="sxs-lookup"><span data-stu-id="60893-108">Attribute</span></span>|<span data-ttu-id="60893-109">Description</span><span class="sxs-lookup"><span data-stu-id="60893-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60893-110">type</span><span class="sxs-lookup"><span data-stu-id="60893-110">type</span></span>|<span data-ttu-id="60893-111">서비스 토큰 확인자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="60893-111">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="60893-112"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>형식 또는 클래스에서 파생 되는 형식 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 입니다.</span><span class="sxs-lookup"><span data-stu-id="60893-112">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="60893-113">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60893-113">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="60893-114">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="60893-114">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60893-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60893-115">Child Elements</span></span>  

 <span data-ttu-id="60893-116">없음</span><span class="sxs-lookup"><span data-stu-id="60893-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60893-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60893-117">Parent Elements</span></span>  
  
|<span data-ttu-id="60893-118">요소</span><span class="sxs-lookup"><span data-stu-id="60893-118">Element</span></span>|<span data-ttu-id="60893-119">설명</span><span class="sxs-lookup"><span data-stu-id="60893-119">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="60893-120">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="60893-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60893-121">설명</span><span class="sxs-lookup"><span data-stu-id="60893-121">Remarks</span></span>  

 <span data-ttu-id="60893-122">서비스 토큰 확인자를 사용 하 여 들어오는 토큰과 메시지의 암호화 토큰을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60893-122">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="60893-123">들어오는 토큰의 암호를 해독 하는 데 사용 되는 키를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60893-123">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="60893-124">특성을 지정 해야 합니다 `type` .</span><span class="sxs-lookup"><span data-stu-id="60893-124">You must specify the `type` attribute.</span></span> <span data-ttu-id="60893-125">지정 된 형식은 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 이거나 클래스에서 파생 되는 사용자 지정 형식일 수 있습니다 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="60893-125">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="60893-126">일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60893-126">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="60893-127">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="60893-127">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60893-128">요소를 요소의 자식 요소로 지정 하는 것은 `<serviceTokenResolver>` [\<identityConfiguration>](identityconfiguration.md) 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60893-128">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="60893-129">`<securityTokenHandlerConfiguration>`요소의 설정은 요소의 설정을 재정의 `<identityConfiguration>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="60893-129">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60893-130">예제</span><span class="sxs-lookup"><span data-stu-id="60893-130">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
