---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252101"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="63082-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="63082-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="63082-102">를 <xref:System.IdentityModel.Services.ChunkedCookieHandler>구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="63082-103">`mode` 요소의 특성이`<cookieHandler>` "Default" 또는 "청크 분할" 인 경우에만이 요소가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63082-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
<span data-ttu-id="63082-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63082-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63082-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="63082-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="63082-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="63082-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="63082-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookieHandler >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="63082-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="63082-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<chunkedCookieHandler >**</span><span class="sxs-lookup"><span data-stu-id="63082-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63082-109">구문</span><span class="sxs-lookup"><span data-stu-id="63082-109">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63082-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="63082-110">Attributes and Elements</span></span>  
 <span data-ttu-id="63082-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63082-112">특성</span><span class="sxs-lookup"><span data-stu-id="63082-112">Attributes</span></span>  
  
|<span data-ttu-id="63082-113">특성</span><span class="sxs-lookup"><span data-stu-id="63082-113">Attribute</span></span>|<span data-ttu-id="63082-114">설명</span><span class="sxs-lookup"><span data-stu-id="63082-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63082-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="63082-115">chunkSize</span></span>|<span data-ttu-id="63082-116">한 HTTP 쿠키에 대 한 HTTP 쿠키 데이터의 최대 크기 (문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="63082-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="63082-117">청크 크기를 조정할 때 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="63082-118">웹 브라우저에는 각 도메인에 허용 되는 쿠키 크기 및 수에 대 한 제한이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="63082-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="63082-119">예를 들어 원래 Netscape 사양은 이러한 제한을 규정 된 합니다. 300 쿠키 합계, 쿠키 헤더 당 4096 바이트 (쿠키 값 뿐만 아니라 메타 데이터 포함) 및 도메인당 20 개의 쿠키</span><span class="sxs-lookup"><span data-stu-id="63082-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="63082-120">기본값은 2000입니다.</span><span class="sxs-lookup"><span data-stu-id="63082-120">The default is 2000.</span></span> <span data-ttu-id="63082-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="63082-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63082-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="63082-122">Child Elements</span></span>  
 <span data-ttu-id="63082-123">없음</span><span class="sxs-lookup"><span data-stu-id="63082-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63082-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="63082-124">Parent Elements</span></span>  
  
|<span data-ttu-id="63082-125">요소</span><span class="sxs-lookup"><span data-stu-id="63082-125">Element</span></span>|<span data-ttu-id="63082-126">설명</span><span class="sxs-lookup"><span data-stu-id="63082-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63082-127">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="63082-127">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="63082-128">(SAM <xref:System.IdentityModel.Services.CookieHandler> )에서 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63082-129">설명</span><span class="sxs-lookup"><span data-stu-id="63082-129">Remarks</span></span>  
 <span data-ttu-id="63082-130">요소의 특성을 "기본" 또는 "청크 분할"으로 <xref:System.IdentityModel.Services.ChunkedCookieHandler> `mode` 설정 하 여을 지정 하는 경우 쿠키 처리기가 `<chunkedCookieHandler>` 자식 요소를 포함 하 여 쿠키를 읽고 쓰는 데 사용 하는 청크 크기를 지정할 수 있습니다. `<cookieHandler>` `chunkSize` 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="63082-131">`<chunkedCookieHandler>` 요소가 없으면 기본 청크 크기인 2000 바이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="63082-132">`mode` 특성이 "Custom"으로 설정 된 경우에는이 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63082-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="63082-133">합니다 `<chunkedCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="63082-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63082-134">예제</span><span class="sxs-lookup"><span data-stu-id="63082-134">Example</span></span>  
 <span data-ttu-id="63082-135">다음 예제에서는 쿠키를 3000 바이트 청크로 쓰는 청크 쿠키 처리기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="63082-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63082-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="63082-136">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
