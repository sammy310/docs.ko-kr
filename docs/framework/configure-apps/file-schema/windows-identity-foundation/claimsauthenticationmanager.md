---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 3602a4805e86833ba6070d801cef6758aaee8a5c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941825"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="a805f-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="a805f-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="a805f-102">들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="a805f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a805f-103">\<system.identityModel></span></span>  
<span data-ttu-id="a805f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a805f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a805f-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="a805f-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a805f-106">구문</span><span class="sxs-lookup"><span data-stu-id="a805f-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a805f-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a805f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a805f-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a805f-109">특성</span><span class="sxs-lookup"><span data-stu-id="a805f-109">Attributes</span></span>  
  
|<span data-ttu-id="a805f-110">특성</span><span class="sxs-lookup"><span data-stu-id="a805f-110">Attribute</span></span>|<span data-ttu-id="a805f-111">Description</span><span class="sxs-lookup"><span data-stu-id="a805f-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a805f-112">type</span><span class="sxs-lookup"><span data-stu-id="a805f-112">type</span></span>|<span data-ttu-id="a805f-113"><xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 파생 되는 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="a805f-114">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a805f-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a805f-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a805f-115">Child Elements</span></span>  
 <span data-ttu-id="a805f-116"><xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 특성이 없거나 특성이 클래스를 참조 하는 경우 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 <xref:System.Security.Claims.ClaimsAuthenticationManager> 파생 된 클래스는 자식 구성 요소를 정의할 수 있습니다. `type` `type`</span><span class="sxs-lookup"><span data-stu-id="a805f-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a805f-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a805f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a805f-118">요소</span><span class="sxs-lookup"><span data-stu-id="a805f-118">Element</span></span>|<span data-ttu-id="a805f-119">설명</span><span class="sxs-lookup"><span data-stu-id="a805f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a805f-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a805f-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a805f-121">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a805f-122">설명</span><span class="sxs-lookup"><span data-stu-id="a805f-122">Remarks</span></span>  
 <span data-ttu-id="a805f-123">클래스를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 통해 제공 되는 기본 동작은 들어오는 클레임을 에코 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="a805f-124">특성을 `type` 지정 하지 않거나 특성에서 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스를 지정 하는 경우 요소 `<claimsAuthenticationManager>` 는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="a805f-125">특성을 지정 하 `type` 여 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 파생 된 형식을 등록 하 고 사용자 지정 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="a805f-126">파생 클래스는 이러한 요소를 처리 하도록 메서드를 `<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="a805f-127">자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="a805f-128">요소 `<claimsAuthenticationManager>` 는 속성을 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805f-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a805f-129">예제</span><span class="sxs-lookup"><span data-stu-id="a805f-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
