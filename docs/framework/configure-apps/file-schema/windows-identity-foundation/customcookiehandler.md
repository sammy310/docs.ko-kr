---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 0129c63fe17b63889a77ea1a56c0d7e657def859
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224052"
---
# <a name="customcookiehandler"></a><span data-ttu-id="70e94-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="70e94-101">\<customCookieHandler></span></span>
<span data-ttu-id="70e94-102">사용자 지정 쿠키 처리기 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="70e94-103">이 요소를 사용할 수만 있습니다 경우 합니다 `mode` 특성을 `<cookieHandler>` 요소는 "Custom" 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="70e94-104">사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="70e94-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="70e94-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="70e94-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="70e94-106">\<federationConfiguration></span></span>  
<span data-ttu-id="70e94-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="70e94-107">\<cookieHandler></span></span>  
<span data-ttu-id="70e94-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="70e94-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e94-109">구문</span><span class="sxs-lookup"><span data-stu-id="70e94-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70e94-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="70e94-110">Attributes and Elements</span></span>  
 <span data-ttu-id="70e94-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70e94-112">특성</span><span class="sxs-lookup"><span data-stu-id="70e94-112">Attributes</span></span>  
  
|<span data-ttu-id="70e94-113">특성</span><span class="sxs-lookup"><span data-stu-id="70e94-113">Attribute</span></span>|<span data-ttu-id="70e94-114">설명</span><span class="sxs-lookup"><span data-stu-id="70e94-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70e94-115">type</span><span class="sxs-lookup"><span data-stu-id="70e94-115">type</span></span>|<span data-ttu-id="70e94-116">파생 되는 사용자 지정 형식 지정을 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="70e94-117">지정 하는 방법에 대 한 자세한 내용은 합니다 `type` 특성을 참조 하십시오 [사용자 지정 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70e94-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="70e94-118">Child Elements</span></span>  
 <span data-ttu-id="70e94-119">없음</span><span class="sxs-lookup"><span data-stu-id="70e94-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70e94-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="70e94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="70e94-121">요소</span><span class="sxs-lookup"><span data-stu-id="70e94-121">Element</span></span>|<span data-ttu-id="70e94-122">설명</span><span class="sxs-lookup"><span data-stu-id="70e94-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70e94-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="70e94-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="70e94-124">구성 된 <xref:System.IdentityModel.Services.CookieHandler> 는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 읽기 및 쓰기 쿠키를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70e94-125">설명</span><span class="sxs-lookup"><span data-stu-id="70e94-125">Remarks</span></span>  
 <span data-ttu-id="70e94-126">설정 하 여 사용자 지정 쿠키 처리기를 지정 하면를 `mode` 특성을 `<cookieHandler>` 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 하는 "Custom"으로 `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소.</span><span class="sxs-lookup"><span data-stu-id="70e94-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="70e94-127">이 요소가 있을 수 없습니다 될 때 지정 되는 `mode` 특성은 "이 Chunked" 또는 "Default"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="70e94-128">사용자 지정 쿠키 처리기에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="70e94-129">합니다 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e94-130">예제</span><span class="sxs-lookup"><span data-stu-id="70e94-130">Example</span></span>  
 <span data-ttu-id="70e94-131">다음 예제에서는 구성 형식의 사용자 지정 쿠키 처리기를 사용 하려면 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="70e94-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70e94-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="70e94-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
