---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: a321c10e04eca2c1a5204929966a1725e918cbdf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158528"
---
# \<chunkedCookieHandler>

<span data-ttu-id="748ab-101">를 구성 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-101">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="748ab-102">`mode` `<cookieHandler>` 요소의 특성이 "Default" 또는 "청크 분할" 인 경우에만이 요소가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="748ab-103">구문</span><span class="sxs-lookup"><span data-stu-id="748ab-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="748ab-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="748ab-104">Attributes and Elements</span></span>  

 <span data-ttu-id="748ab-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="748ab-106">특성</span><span class="sxs-lookup"><span data-stu-id="748ab-106">Attributes</span></span>  
  
|<span data-ttu-id="748ab-107">attribute</span><span class="sxs-lookup"><span data-stu-id="748ab-107">Attribute</span></span>|<span data-ttu-id="748ab-108">설명</span><span class="sxs-lookup"><span data-stu-id="748ab-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="748ab-109">chunkSize</span><span class="sxs-lookup"><span data-stu-id="748ab-109">chunkSize</span></span>|<span data-ttu-id="748ab-110">한 HTTP 쿠키에 대 한 HTTP 쿠키 데이터의 최대 크기 (문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-110">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="748ab-111">청크 크기를 조정할 때 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-111">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="748ab-112">웹 브라우저에는 각 도메인에 허용 되는 쿠키 크기 및 수에 대 한 제한이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-112">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="748ab-113">예를 들어 원래 Netscape 사양은 300 쿠키 합계, 쿠키 헤더 당 4096 바이트 (쿠키 값 뿐만 아니라 메타 데이터 포함) 및 도메인당 20 개의 쿠키를 규정 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-113">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="748ab-114">기본값은 2000입니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-114">The default is 2000.</span></span> <span data-ttu-id="748ab-115">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-115">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="748ab-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="748ab-116">Child Elements</span></span>  

 <span data-ttu-id="748ab-117">없음</span><span class="sxs-lookup"><span data-stu-id="748ab-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="748ab-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="748ab-118">Parent Elements</span></span>  
  
|<span data-ttu-id="748ab-119">요소</span><span class="sxs-lookup"><span data-stu-id="748ab-119">Element</span></span>|<span data-ttu-id="748ab-120">설명</span><span class="sxs-lookup"><span data-stu-id="748ab-120">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="748ab-121"><xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)에서 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-121">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="748ab-122">설명</span><span class="sxs-lookup"><span data-stu-id="748ab-122">Remarks</span></span>  

 <span data-ttu-id="748ab-123"><xref:System.IdentityModel.Services.ChunkedCookieHandler> `mode` 요소의 특성을 "기본" 또는 "청크 분할"으로 설정 하 여을 지정 하는 경우 `<cookieHandler>` 쿠키 처리기가 자식 요소를 포함 하 고 특성을 설정 하 여 쿠키를 읽고 쓰는 데 사용 하는 청크 크기를 지정할 수 있습니다 `<chunkedCookieHandler>` `chunkSize` .</span><span class="sxs-lookup"><span data-stu-id="748ab-123">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="748ab-124">요소가 없으면 `<chunkedCookieHandler>` 기본 청크 크기인 2000 바이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-124">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="748ab-125">`mode`특성이 "Custom"으로 설정 된 경우에는이 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-125">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="748ab-126">합니다 `<chunkedCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-126">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="748ab-127">예제</span><span class="sxs-lookup"><span data-stu-id="748ab-127">Example</span></span>  

 <span data-ttu-id="748ab-128">다음 예제에서는 쿠키를 3000 바이트 청크로 쓰는 청크 쿠키 처리기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="748ab-128">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="748ab-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="748ab-129">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
