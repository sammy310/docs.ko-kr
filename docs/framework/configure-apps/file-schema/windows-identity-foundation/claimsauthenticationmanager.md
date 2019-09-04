---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252099"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="2401e-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="2401e-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="2401e-102">들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="2401e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2401e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2401e-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="2401e-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="2401e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2401e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="2401e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthenticationManager >**</span><span class="sxs-lookup"><span data-stu-id="2401e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2401e-107">구문</span><span class="sxs-lookup"><span data-stu-id="2401e-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2401e-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2401e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2401e-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2401e-110">특성</span><span class="sxs-lookup"><span data-stu-id="2401e-110">Attributes</span></span>  
  
|<span data-ttu-id="2401e-111">특성</span><span class="sxs-lookup"><span data-stu-id="2401e-111">Attribute</span></span>|<span data-ttu-id="2401e-112">Description</span><span class="sxs-lookup"><span data-stu-id="2401e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2401e-113">type</span><span class="sxs-lookup"><span data-stu-id="2401e-113">type</span></span>|<span data-ttu-id="2401e-114"><xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 파생 되는 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="2401e-115">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2401e-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2401e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2401e-116">Child Elements</span></span>  
 <span data-ttu-id="2401e-117"><xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 특성이 없거나 특성이 클래스를 참조 하는 경우 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 <xref:System.Security.Claims.ClaimsAuthenticationManager> 파생 된 클래스는 자식 구성 요소를 정의할 수 있습니다. `type` `type`</span><span class="sxs-lookup"><span data-stu-id="2401e-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2401e-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2401e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2401e-119">요소</span><span class="sxs-lookup"><span data-stu-id="2401e-119">Element</span></span>|<span data-ttu-id="2401e-120">설명</span><span class="sxs-lookup"><span data-stu-id="2401e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2401e-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2401e-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="2401e-122">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2401e-123">설명</span><span class="sxs-lookup"><span data-stu-id="2401e-123">Remarks</span></span>  
 <span data-ttu-id="2401e-124">클래스를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 통해 제공 되는 기본 동작은 들어오는 클레임을 에코 합니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="2401e-125">특성을 `type` 지정 하지 않거나 특성에서 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스를 지정 하는 경우 요소 `<claimsAuthenticationManager>` 는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="2401e-126">특성을 지정 하 `type` 여 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 파생 된 형식을 등록 하 고 사용자 지정 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="2401e-127">파생 클래스는 이러한 요소를 처리 하도록 메서드를 `<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="2401e-128">자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="2401e-129">요소 `<claimsAuthenticationManager>` 는 속성을 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2401e-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2401e-130">예제</span><span class="sxs-lookup"><span data-stu-id="2401e-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
