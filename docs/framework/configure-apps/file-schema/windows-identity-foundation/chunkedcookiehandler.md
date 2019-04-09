---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120785"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="b3eee-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="b3eee-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="b3eee-102">구성 된 <xref:System.IdentityModel.Services.ChunkedCookieHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="b3eee-103">이 요소를 사용할 수만 있습니다 경우는 `mode` 특성을 `<cookieHandler>` 요소는 "Default" 또는 "청크"입니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="b3eee-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="b3eee-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="b3eee-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="b3eee-105">\<federationConfiguration></span></span>  
<span data-ttu-id="b3eee-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="b3eee-106">\<cookieHandler></span></span>  
<span data-ttu-id="b3eee-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="b3eee-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3eee-108">구문</span><span class="sxs-lookup"><span data-stu-id="b3eee-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3eee-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b3eee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b3eee-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3eee-111">특성</span><span class="sxs-lookup"><span data-stu-id="b3eee-111">Attributes</span></span>  
  
|<span data-ttu-id="b3eee-112">특성</span><span class="sxs-lookup"><span data-stu-id="b3eee-112">Attribute</span></span>|<span data-ttu-id="b3eee-113">설명</span><span class="sxs-lookup"><span data-stu-id="b3eee-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3eee-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="b3eee-114">chunkSize</span></span>|<span data-ttu-id="b3eee-115">HTTP 쿠키에 대 한 HTTP 쿠키 데이터의 문자, 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="b3eee-116">청크 크기를 조정할 때 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="b3eee-117">웹 브라우저 쿠키 및 도메인 별로 허용 되는 수의 크기에 서로 다른 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="b3eee-118">예를 들어 원래 Netscape 사양에는 이러한 제한을 규정 된: 4096 바이트로 쿠키 헤더 (메타 데이터를 쿠키 값 뿐 아니라 포함) 및 도메인 별로 20 쿠키 300 쿠키 총입니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="b3eee-119">기본값은 2000입니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-119">The default is 2000.</span></span> <span data-ttu-id="b3eee-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b3eee-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3eee-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b3eee-121">Child Elements</span></span>  
 <span data-ttu-id="b3eee-122">없음</span><span class="sxs-lookup"><span data-stu-id="b3eee-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3eee-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b3eee-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b3eee-124">요소</span><span class="sxs-lookup"><span data-stu-id="b3eee-124">Element</span></span>|<span data-ttu-id="b3eee-125">설명</span><span class="sxs-lookup"><span data-stu-id="b3eee-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3eee-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="b3eee-126">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="b3eee-127">구성 된 <xref:System.IdentityModel.Services.CookieHandler> 는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 읽기 및 쓰기 쿠키를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3eee-128">설명</span><span class="sxs-lookup"><span data-stu-id="b3eee-128">Remarks</span></span>  
 <span data-ttu-id="b3eee-129">지정 하는 경우는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 설정 하 여는 `mode` 특성을 `<cookieHandler>` "Default" 또는 "Chunked" 요소를 포함 하 여 쿠키를 읽고 사용 하는 쿠키 처리기는 청크 크기를 지정할 수 있습니다는 `<chunkedCookieHandler>` 자식 요소 및 설정을 해당 `chunkSize` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="b3eee-130">경우는 `<chunkedCookieHandler>` 요소가 없으면, 2000 바이트의 기본 청크 크기가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="b3eee-131">이 요소가 있을 수 없습니다 될 때 지정 되는 `mode` 특성은 "Custom"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="b3eee-132">합니다 `<chunkedCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3eee-133">예제</span><span class="sxs-lookup"><span data-stu-id="b3eee-133">Example</span></span>  
 <span data-ttu-id="b3eee-134">다음 예제에서는 3000 바이트 청크에서 쿠키를 작성 하는 청크 분할된 쿠키 처리기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eee-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3eee-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3eee-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
