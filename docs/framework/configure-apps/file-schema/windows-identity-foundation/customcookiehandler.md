---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942788"
---
# <a name="customcookiehandler"></a><span data-ttu-id="ea461-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="ea461-101">\<customCookieHandler></span></span>
<span data-ttu-id="ea461-102">사용자 지정 쿠키 처리기 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="ea461-103">이 요소는 `mode` `<cookieHandler>` 요소의 특성이 "Custom" 인 경우에만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="ea461-104">사용자 지정 형식은 <xref:System.IdentityModel.Services.CookieHandler> 클래스에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="ea461-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="ea461-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="ea461-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="ea461-106">\<federationConfiguration></span></span>  
<span data-ttu-id="ea461-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="ea461-107">\<cookieHandler></span></span>  
<span data-ttu-id="ea461-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="ea461-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea461-109">구문</span><span class="sxs-lookup"><span data-stu-id="ea461-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea461-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ea461-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ea461-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea461-112">특성</span><span class="sxs-lookup"><span data-stu-id="ea461-112">Attributes</span></span>  
  
|<span data-ttu-id="ea461-113">특성</span><span class="sxs-lookup"><span data-stu-id="ea461-113">Attribute</span></span>|<span data-ttu-id="ea461-114">Description</span><span class="sxs-lookup"><span data-stu-id="ea461-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea461-115">type</span><span class="sxs-lookup"><span data-stu-id="ea461-115">type</span></span>|<span data-ttu-id="ea461-116"><xref:System.IdentityModel.Services.CookieHandler> 클래스에서 파생 되는 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="ea461-117">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea461-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea461-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ea461-118">Child Elements</span></span>  
 <span data-ttu-id="ea461-119">없음</span><span class="sxs-lookup"><span data-stu-id="ea461-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea461-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ea461-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ea461-121">요소</span><span class="sxs-lookup"><span data-stu-id="ea461-121">Element</span></span>|<span data-ttu-id="ea461-122">Description</span><span class="sxs-lookup"><span data-stu-id="ea461-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea461-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="ea461-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="ea461-124"><xref:System.IdentityModel.Services.CookieHandler> 에서<xref:System.IdentityModel.Services.SessionAuthenticationModule> 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea461-125">설명</span><span class="sxs-lookup"><span data-stu-id="ea461-125">Remarks</span></span>  
 <span data-ttu-id="ea461-126">요소의 특성을 "custom"으로 설정 `<customCookieHandler>` 하 여 사용자 지정 쿠키 처리기를 지정 하는 경우 쿠키 처리기 형식을 참조 하는 자식 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 합니다. `mode` `<cookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="ea461-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="ea461-127">`mode` 특성이 "청크 분할" 또는 "기본값"으로 설정 된 경우에는이 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="ea461-128">사용자 지정 쿠키 처리기는 <xref:System.IdentityModel.Services.CookieHandler> 클래스에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="ea461-129">합니다 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea461-130">예제</span><span class="sxs-lookup"><span data-stu-id="ea461-130">Example</span></span>  
 <span data-ttu-id="ea461-131">다음 예제에서는 구성 형식의 사용자 지정 쿠키 처리기를 사용 하려면 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea461-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea461-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea461-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
