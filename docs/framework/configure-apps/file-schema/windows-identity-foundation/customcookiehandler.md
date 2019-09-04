---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252013"
---
# <a name="customcookiehandler"></a><span data-ttu-id="13165-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="13165-101">\<customCookieHandler></span></span>
<span data-ttu-id="13165-102">사용자 지정 쿠키 처리기 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="13165-103">이 요소는 `mode` `<cookieHandler>` 요소의 특성이 "Custom" 인 경우에만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13165-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="13165-104">사용자 지정 형식은 <xref:System.IdentityModel.Services.CookieHandler> 클래스에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="13165-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13165-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="13165-106">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="13165-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="13165-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="13165-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="13165-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookieHandler >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="13165-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="13165-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customCookieHandler >**</span><span class="sxs-lookup"><span data-stu-id="13165-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13165-110">구문</span><span class="sxs-lookup"><span data-stu-id="13165-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13165-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="13165-111">Attributes and Elements</span></span>  
 <span data-ttu-id="13165-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13165-113">특성</span><span class="sxs-lookup"><span data-stu-id="13165-113">Attributes</span></span>  
  
|<span data-ttu-id="13165-114">특성</span><span class="sxs-lookup"><span data-stu-id="13165-114">Attribute</span></span>|<span data-ttu-id="13165-115">Description</span><span class="sxs-lookup"><span data-stu-id="13165-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13165-116">type</span><span class="sxs-lookup"><span data-stu-id="13165-116">type</span></span>|<span data-ttu-id="13165-117"><xref:System.IdentityModel.Services.CookieHandler> 클래스에서 파생 되는 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="13165-118">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13165-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13165-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="13165-119">Child Elements</span></span>  
 <span data-ttu-id="13165-120">없음</span><span class="sxs-lookup"><span data-stu-id="13165-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13165-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="13165-121">Parent Elements</span></span>  
  
|<span data-ttu-id="13165-122">요소</span><span class="sxs-lookup"><span data-stu-id="13165-122">Element</span></span>|<span data-ttu-id="13165-123">Description</span><span class="sxs-lookup"><span data-stu-id="13165-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13165-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="13165-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="13165-125"><xref:System.IdentityModel.Services.CookieHandler> 에서<xref:System.IdentityModel.Services.SessionAuthenticationModule> 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13165-126">설명</span><span class="sxs-lookup"><span data-stu-id="13165-126">Remarks</span></span>  
 <span data-ttu-id="13165-127">요소의 특성을 "custom"으로 설정 `<customCookieHandler>` 하 여 사용자 지정 쿠키 처리기를 지정 하는 경우 쿠키 처리기 형식을 참조 하는 자식 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 합니다. `mode` `<cookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="13165-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="13165-128">`mode` 특성이 "청크 분할" 또는 "기본값"으로 설정 된 경우에는이 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13165-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="13165-129">사용자 지정 쿠키 처리기는 <xref:System.IdentityModel.Services.CookieHandler> 클래스에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="13165-130">합니다 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="13165-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13165-131">예제</span><span class="sxs-lookup"><span data-stu-id="13165-131">Example</span></span>  
 <span data-ttu-id="13165-132">다음 예제에서는 구성 형식의 사용자 지정 쿠키 처리기를 사용 하려면 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="13165-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13165-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="13165-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
