---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667329"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="0c4c3-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="0c4c3-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="0c4c3-102">들어오는 클레임에 대 한 클레임 인증 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="0c4c3-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0c4c3-103">\<system.identityModel></span></span>  
<span data-ttu-id="0c4c3-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0c4c3-104">\<identityConfiguration></span></span>  
<span data-ttu-id="0c4c3-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="0c4c3-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4c3-106">구문</span><span class="sxs-lookup"><span data-stu-id="0c4c3-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c4c3-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c4c3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0c4c3-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c4c3-109">특성</span><span class="sxs-lookup"><span data-stu-id="0c4c3-109">Attributes</span></span>  
  
|<span data-ttu-id="0c4c3-110">특성</span><span class="sxs-lookup"><span data-stu-id="0c4c3-110">Attribute</span></span>|<span data-ttu-id="0c4c3-111">설명</span><span class="sxs-lookup"><span data-stu-id="0c4c3-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c4c3-112">type</span><span class="sxs-lookup"><span data-stu-id="0c4c3-112">type</span></span>|<span data-ttu-id="0c4c3-113">파생 되는 사용자 지정 형식 지정을 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="0c4c3-114">지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c4c3-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c4c3-115">Child Elements</span></span>  
 <span data-ttu-id="0c4c3-116">없는 경우 없습니다 `type` 특성을 또는 경우에는 `type` 특성 참조를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스를 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthenticationManager> 자식 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c4c3-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c4c3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0c4c3-118">요소</span><span class="sxs-lookup"><span data-stu-id="0c4c3-118">Element</span></span>|<span data-ttu-id="0c4c3-119">설명</span><span class="sxs-lookup"><span data-stu-id="0c4c3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c4c3-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0c4c3-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="0c4c3-121">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c4c3-122">설명</span><span class="sxs-lookup"><span data-stu-id="0c4c3-122">Remarks</span></span>  
 <span data-ttu-id="0c4c3-123">기본 동작을 통해 제공 된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 들어오는 클레임을 에코 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="0c4c3-124">없으면 `type` 특성을 지정 경우는 `type` 특성을 지정 합니다 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="0c4c3-125">지정할 수 있습니다 합니다 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="0c4c3-126">파생된 클래스의 자식 요소를 통해 구성을 지원할 수는 `<claimsAuthenticationManager>` 재정의 하 여 요소를 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="0c4c3-127">자식 요소에 대해 정의 된 스키마 클래스의 디자이너에 게 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="0c4c3-128">합니다 `<claimsAuthenticationManager>` 요소 집합을 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c4c3-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c4c3-129">예제</span><span class="sxs-lookup"><span data-stu-id="0c4c3-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
