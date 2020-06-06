---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152582"
---
# \<serviceTokenResolver>
<span data-ttu-id="491dd-101">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-101">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="491dd-102">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-102">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="491dd-103">구문</span><span class="sxs-lookup"><span data-stu-id="491dd-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="491dd-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="491dd-104">Attributes and Elements</span></span>  
 <span data-ttu-id="491dd-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="491dd-106">특성</span><span class="sxs-lookup"><span data-stu-id="491dd-106">Attributes</span></span>  
  
|<span data-ttu-id="491dd-107">attribute</span><span class="sxs-lookup"><span data-stu-id="491dd-107">Attribute</span></span>|<span data-ttu-id="491dd-108">Description</span><span class="sxs-lookup"><span data-stu-id="491dd-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="491dd-109">type</span><span class="sxs-lookup"><span data-stu-id="491dd-109">type</span></span>|<span data-ttu-id="491dd-110">서비스 토큰 확인자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-110">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="491dd-111"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>형식 또는 클래스에서 파생 되는 형식 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 입니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-111">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="491dd-112">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="491dd-112">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="491dd-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="491dd-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="491dd-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="491dd-114">Child Elements</span></span>  
 <span data-ttu-id="491dd-115">None</span><span class="sxs-lookup"><span data-stu-id="491dd-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="491dd-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="491dd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="491dd-117">요소</span><span class="sxs-lookup"><span data-stu-id="491dd-117">Element</span></span>|<span data-ttu-id="491dd-118">Description</span><span class="sxs-lookup"><span data-stu-id="491dd-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="491dd-119">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="491dd-120">설명</span><span class="sxs-lookup"><span data-stu-id="491dd-120">Remarks</span></span>  
 <span data-ttu-id="491dd-121">서비스 토큰 확인자를 사용 하 여 들어오는 토큰과 메시지의 암호화 토큰을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-121">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="491dd-122">들어오는 토큰의 암호를 해독 하는 데 사용 되는 키를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-122">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="491dd-123">특성을 지정 해야 합니다 `type` .</span><span class="sxs-lookup"><span data-stu-id="491dd-123">You must specify the `type` attribute.</span></span> <span data-ttu-id="491dd-124">지정 된 형식은 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 이거나 클래스에서 파생 되는 사용자 지정 형식일 수 있습니다 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="491dd-124">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="491dd-125">일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-125">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="491dd-126">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-126">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="491dd-127">요소를 요소의 자식 요소로 지정 하는 것은 `<serviceTokenResolver>` [\<identityConfiguration>](identityconfiguration.md) 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-127">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="491dd-128">`<securityTokenHandlerConfiguration>`요소의 설정은 요소의 설정을 재정의 `<identityConfiguration>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="491dd-128">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="491dd-129">예제</span><span class="sxs-lookup"><span data-stu-id="491dd-129">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
