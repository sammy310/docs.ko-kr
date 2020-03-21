---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152751"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="6a5c2-101">\<클레임인증관리자></span><span class="sxs-lookup"><span data-stu-id="6a5c2-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="6a5c2-102">들어오는 클레임에 대한 클레임 인증 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="6a5c2-103">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6a5c2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6a5c2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="6a5c2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="6a5c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6a5c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="6a5c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<클레임인증관리자>**</span><span class="sxs-lookup"><span data-stu-id="6a5c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5c2-107">구문</span><span class="sxs-lookup"><span data-stu-id="6a5c2-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a5c2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6a5c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6a5c2-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a5c2-110">특성</span><span class="sxs-lookup"><span data-stu-id="6a5c2-110">Attributes</span></span>  
  
|<span data-ttu-id="6a5c2-111">attribute</span><span class="sxs-lookup"><span data-stu-id="6a5c2-111">Attribute</span></span>|<span data-ttu-id="6a5c2-112">Description</span><span class="sxs-lookup"><span data-stu-id="6a5c2-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a5c2-113">type</span><span class="sxs-lookup"><span data-stu-id="6a5c2-113">type</span></span>|<span data-ttu-id="6a5c2-114"><xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 파생되는 사용자 지정 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="6a5c2-115">`type` 특성을 지정하는 방법에 대한 자세한 내용은 [사용자 지정 유형 참조]를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a5c2-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6a5c2-116">Child Elements</span></span>  
 <span data-ttu-id="6a5c2-117">특성이 없거나 `type` 특성이 클래스를 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> 참조하는 경우 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용하지 않습니다. 그러나 파생된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 자식 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a5c2-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6a5c2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6a5c2-119">요소</span><span class="sxs-lookup"><span data-stu-id="6a5c2-119">Element</span></span>|<span data-ttu-id="6a5c2-120">Description</span><span class="sxs-lookup"><span data-stu-id="6a5c2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a5c2-121">\<ID구성></span><span class="sxs-lookup"><span data-stu-id="6a5c2-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="6a5c2-122">서비스 수준 ID 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a5c2-123">설명</span><span class="sxs-lookup"><span data-stu-id="6a5c2-123">Remarks</span></span>  
 <span data-ttu-id="6a5c2-124">클래스를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 통해 제공되는 기본 동작은 들어오는 클레임을 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="6a5c2-125">특성이 `type` 지정되지 않았거나 `type` 특성이 클래스를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 지정하는 `<claimsAuthenticationManager>` 경우 요소는 자식 요소를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="6a5c2-126">사용자 지정 `type` 동작을 구현하기 위해 클래스에서 파생된 형식을 등록하는 특성을 <xref:System.Security.Claims.ClaimsAuthenticationManager> 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="6a5c2-127">파생 클래스는 이러한 요소를 처리하는 `<claimsAuthenticationManager>` 메서드를 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 재정의하여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="6a5c2-128">자식 요소에 대해 정의된 스키마는 클래스의 디자이너에게 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="6a5c2-129">`<claimsAuthenticationManager>` 요소는 속성을 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5c2-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a5c2-130">예제</span><span class="sxs-lookup"><span data-stu-id="6a5c2-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
