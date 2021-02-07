---
description: 다음에 대해 자세히 알아보세요. <customCookieHandler>
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 6b433769c429ed4149efb324d7c4b216d6042705
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664082"
---
# \<customCookieHandler>

<span data-ttu-id="97745-102">사용자 지정 쿠키 처리기 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97745-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="97745-103">이 요소는 `mode` `<cookieHandler>` 요소의 특성이 "Custom" 인 경우에만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97745-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="97745-104">사용자 지정 형식은 클래스에서 파생 되어야 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="97745-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="97745-105">구문</span><span class="sxs-lookup"><span data-stu-id="97745-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97745-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="97745-106">Attributes and Elements</span></span>  

 <span data-ttu-id="97745-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97745-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97745-108">특성</span><span class="sxs-lookup"><span data-stu-id="97745-108">Attributes</span></span>  
  
|<span data-ttu-id="97745-109">attribute</span><span class="sxs-lookup"><span data-stu-id="97745-109">Attribute</span></span>|<span data-ttu-id="97745-110">Description</span><span class="sxs-lookup"><span data-stu-id="97745-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97745-111">type</span><span class="sxs-lookup"><span data-stu-id="97745-111">type</span></span>|<span data-ttu-id="97745-112">클래스에서 파생 되는 사용자 지정 형식을 지정 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="97745-112">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="97745-113">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97745-113">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97745-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="97745-114">Child Elements</span></span>  

 <span data-ttu-id="97745-115">없음</span><span class="sxs-lookup"><span data-stu-id="97745-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97745-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="97745-116">Parent Elements</span></span>  
  
|<span data-ttu-id="97745-117">요소</span><span class="sxs-lookup"><span data-stu-id="97745-117">Element</span></span>|<span data-ttu-id="97745-118">설명</span><span class="sxs-lookup"><span data-stu-id="97745-118">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="97745-119"><xref:System.IdentityModel.Services.CookieHandler>에서 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="97745-119">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97745-120">설명</span><span class="sxs-lookup"><span data-stu-id="97745-120">Remarks</span></span>  

 <span data-ttu-id="97745-121">요소의 특성을 "Custom"으로 설정 하 여 사용자 지정 쿠키 처리기를 지정 하는 경우 `mode` `<cookieHandler>` `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97745-121">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="97745-122">`mode`특성이 "청크 분할" 또는 "기본값"으로 설정 된 경우에는이 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97745-122">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="97745-123">사용자 지정 쿠키 처리기는 클래스에서 파생 되어야 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="97745-123">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="97745-124">합니다 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="97745-124">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97745-125">예제</span><span class="sxs-lookup"><span data-stu-id="97745-125">Example</span></span>  

 <span data-ttu-id="97745-126">다음 예제에서는 구성 형식의 사용자 지정 쿠키 처리기를 사용 하려면 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="97745-126">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="97745-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97745-127">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
