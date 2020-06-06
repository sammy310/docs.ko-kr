---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152751"
---
# \<claimsAuthenticationManager>
<span data-ttu-id="1e219-101">들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-101">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="1e219-102">구문</span><span class="sxs-lookup"><span data-stu-id="1e219-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e219-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e219-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1e219-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e219-105">특성</span><span class="sxs-lookup"><span data-stu-id="1e219-105">Attributes</span></span>  
  
|<span data-ttu-id="1e219-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1e219-106">Attribute</span></span>|<span data-ttu-id="1e219-107">Description</span><span class="sxs-lookup"><span data-stu-id="1e219-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e219-108">type</span><span class="sxs-lookup"><span data-stu-id="1e219-108">type</span></span>|<span data-ttu-id="1e219-109">클래스에서 파생 되는 사용자 지정 형식을 지정 합니다 <xref:System.Security.Claims.ClaimsAuthenticationManager> .</span><span class="sxs-lookup"><span data-stu-id="1e219-109">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="1e219-110">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e219-110">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e219-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e219-111">Child Elements</span></span>  
 <span data-ttu-id="1e219-112">`type`특성이 없거나 특성이 클래스를 참조 하는 경우 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다. 그러나에서 파생 된 클래스는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 자식 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e219-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e219-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1e219-114">요소</span><span class="sxs-lookup"><span data-stu-id="1e219-114">Element</span></span>|<span data-ttu-id="1e219-115">Description</span><span class="sxs-lookup"><span data-stu-id="1e219-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="1e219-116">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e219-117">설명</span><span class="sxs-lookup"><span data-stu-id="1e219-117">Remarks</span></span>  
 <span data-ttu-id="1e219-118">클래스를 통해 제공 되는 기본 동작은 <xref:System.Security.Claims.ClaimsAuthenticationManager> 들어오는 클레임을 에코 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="1e219-119">특성을 `type` 지정 하지 않거나 특성에서 클래스를 지정 하는 경우 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="1e219-120">특성을 지정 `type` 하 여 클래스에서 파생 된 형식을 등록 하 고 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="1e219-121">파생 클래스 `<claimsAuthenticationManager>` 는 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하도록 메서드를 재정의 하 여 요소의 자식 요소를 통해 구성을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-121">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="1e219-122">자식 요소에 대해 정의 된 스키마는 클래스의 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="1e219-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="1e219-123">`<claimsAuthenticationManager>`요소는 속성을 설정 합니다 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1e219-123">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e219-124">예제</span><span class="sxs-lookup"><span data-stu-id="1e219-124">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
