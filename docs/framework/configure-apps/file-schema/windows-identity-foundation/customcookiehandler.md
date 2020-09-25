---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a8ee23ac6facaea18cd7f1820616cb9b16afa336
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189853"
---
# \<customCookieHandler>

<span data-ttu-id="7176d-101">사용자 지정 쿠키 처리기 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-101">Sets the custom cookie handler type.</span></span> <span data-ttu-id="7176d-102">이 요소는 `mode` `<cookieHandler>` 요소의 특성이 "Custom" 인 경우에만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="7176d-103">사용자 지정 형식은 클래스에서 파생 되어야 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="7176d-103">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="7176d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7176d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7176d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7176d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7176d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7176d-107">특성</span><span class="sxs-lookup"><span data-stu-id="7176d-107">Attributes</span></span>  
  
|<span data-ttu-id="7176d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7176d-108">Attribute</span></span>|<span data-ttu-id="7176d-109">Description</span><span class="sxs-lookup"><span data-stu-id="7176d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7176d-110">type</span><span class="sxs-lookup"><span data-stu-id="7176d-110">type</span></span>|<span data-ttu-id="7176d-111">클래스에서 파생 되는 사용자 지정 형식을 지정 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="7176d-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="7176d-112">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7176d-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7176d-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7176d-113">Child Elements</span></span>  

 <span data-ttu-id="7176d-114">없음</span><span class="sxs-lookup"><span data-stu-id="7176d-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7176d-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7176d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7176d-116">요소</span><span class="sxs-lookup"><span data-stu-id="7176d-116">Element</span></span>|<span data-ttu-id="7176d-117">설명</span><span class="sxs-lookup"><span data-stu-id="7176d-117">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="7176d-118"><xref:System.IdentityModel.Services.CookieHandler>에서 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-118">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7176d-119">설명</span><span class="sxs-lookup"><span data-stu-id="7176d-119">Remarks</span></span>  

 <span data-ttu-id="7176d-120">요소의 특성을 "Custom"으로 설정 하 여 사용자 지정 쿠키 처리기를 지정 하는 경우 `mode` `<cookieHandler>` `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-120">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="7176d-121">`mode`특성이 "청크 분할" 또는 "기본값"으로 설정 된 경우에는이 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-121">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="7176d-122">사용자 지정 쿠키 처리기는 클래스에서 파생 되어야 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="7176d-122">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="7176d-123">합니다 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-123">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7176d-124">예제</span><span class="sxs-lookup"><span data-stu-id="7176d-124">Example</span></span>  

 <span data-ttu-id="7176d-125">다음 예제에서는 구성 형식의 사용자 지정 쿠키 처리기를 사용 하려면 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="7176d-125">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7176d-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7176d-126">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
