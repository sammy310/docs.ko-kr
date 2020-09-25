---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 5f5b432830a61adab324b2b6cd2ebe6eeccca7f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189840"
---
# \<cookieHandler>

<span data-ttu-id="6ccfa-101"><xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)에서 쿠키를 읽고 쓰는 데 사용 하는를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-101">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="6ccfa-102">구문</span><span class="sxs-lookup"><span data-stu-id="6ccfa-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ccfa-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6ccfa-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6ccfa-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ccfa-105">특성</span><span class="sxs-lookup"><span data-stu-id="6ccfa-105">Attributes</span></span>  
  
|<span data-ttu-id="6ccfa-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6ccfa-106">Attribute</span></span>|<span data-ttu-id="6ccfa-107">Description</span><span class="sxs-lookup"><span data-stu-id="6ccfa-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ccfa-108">name</span><span class="sxs-lookup"><span data-stu-id="6ccfa-108">name</span></span>|<span data-ttu-id="6ccfa-109">작성 된 모든 쿠키의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-109">Specifies the base name for any cookies written.</span></span> <span data-ttu-id="6ccfa-110">기본값은 "FedAuth"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-110">The default is "FedAuth".</span></span>|  
|<span data-ttu-id="6ccfa-111">path</span><span class="sxs-lookup"><span data-stu-id="6ccfa-111">path</span></span>|<span data-ttu-id="6ccfa-112">작성 된 모든 쿠키에 대 한 경로 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-112">Specifies the path value for any cookies written.</span></span> <span data-ttu-id="6ccfa-113">기본값은 "HttpRuntime. AppDomainAppVirtualPath"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-113">The default is "HttpRuntime.AppDomainAppVirtualPath".</span></span>|  
|<span data-ttu-id="6ccfa-114">mode</span><span class="sxs-lookup"><span data-stu-id="6ccfa-114">mode</span></span>|<span data-ttu-id="6ccfa-115"><xref:System.IdentityModel.Services.CookieHandlerMode>SAM에서 사용 하는 쿠키 처리기의 종류를 지정 하는 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-115">One of the <xref:System.IdentityModel.Services.CookieHandlerMode> values that specifies the kind of cookie handler used by the SAM.</span></span> <span data-ttu-id="6ccfa-116">다음 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-116">The following values may be used:</span></span><br /><br /> <span data-ttu-id="6ccfa-117">-"Default"-"청크 분할"과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-117">-   "Default" — The same as "Chunked".</span></span><br /><span data-ttu-id="6ccfa-118">-"청크 분할"-클래스의 인스턴스를 사용 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-118">-   "Chunked" — Uses an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class.</span></span> <span data-ttu-id="6ccfa-119">이 쿠키 처리기는 개별 쿠키가 설정 된 최대 크기를 초과 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-119">This cookie handler ensures that individual cookies do not exceed a set maximum size.</span></span> <span data-ttu-id="6ccfa-120">이는 잠재적으로 논리 쿠키 하나를 실시간으로 많은 쿠키에 "청크" 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-120">It accomplishes this by potentially "chunking" one logical cookie into a number of cookies on-the-wire.</span></span><br /><span data-ttu-id="6ccfa-121">-"Custom" —에서 파생 된 사용자 지정 클래스의 인스턴스를 사용 <xref:System.IdentityModel.Services.CookieHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-121">-   "Custom" — Uses an instance of a custom class derived from <xref:System.IdentityModel.Services.CookieHandler>.</span></span> <span data-ttu-id="6ccfa-122">파생 된 클래스는 자식 요소에서 참조 됩니다 `<customCookieHandler>` .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-122">The derived class is referenced by the `<customCookieHandler>` child element.</span></span><br /><br /> <span data-ttu-id="6ccfa-123">기본값은 "Default"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-123">The default is "Default".</span></span>|  
|<span data-ttu-id="6ccfa-124">persistentSessionLifetime</span><span class="sxs-lookup"><span data-stu-id="6ccfa-124">persistentSessionLifetime</span></span>|<span data-ttu-id="6ccfa-125">영구적 세션의 수명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-125">Specifies the lifetime of persistent sessions.</span></span> <span data-ttu-id="6ccfa-126">0이면 임시 세션이 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-126">If zero, transient sessions are always used.</span></span> <span data-ttu-id="6ccfa-127">기본값은 임시 세션을 지정 하는 "0:0:0"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-127">The default value is "0:0:0", which specifies a transient session.</span></span> <span data-ttu-id="6ccfa-128">최대값은 365 일의 세션을 지정 하는 "365:0:0"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-128">The maximum value is "365:0:0", which specifies a session of 365 days.</span></span> <span data-ttu-id="6ccfa-129">값은 다음 제한 사항에 따라 지정 해야 합니다. `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />` 여기서 왼쪽 값은 일을 지정 하 고, 중간 값 (있는 경우)은 시간을 지정 하 고, 가장 오른쪽 값 (있는 경우)은 분을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-129">The value should be specified according to the following restriction: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, where the leftmost value specifies days, the middle value (if present) specifies hours, and the rightmost value (if present) specifies minutes.</span></span>|  
|<span data-ttu-id="6ccfa-130">requireSsl</span><span class="sxs-lookup"><span data-stu-id="6ccfa-130">requireSsl</span></span>|<span data-ttu-id="6ccfa-131">작성 된 모든 쿠키에 대해 "보안" 플래그를 내보낼지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-131">Specifies whether the "Secure" flag is emitted for any cookies written.</span></span> <span data-ttu-id="6ccfa-132">이 값을 설정 하면 로그인 세션 쿠키는 HTTPS를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-132">If this value is set, the sign-in session cookies will only be available over HTTPS.</span></span> <span data-ttu-id="6ccfa-133">기본값은 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-133">The default is "true".</span></span>|  
|<span data-ttu-id="6ccfa-134">hideFromScript</span><span class="sxs-lookup"><span data-stu-id="6ccfa-134">hideFromScript</span></span>|<span data-ttu-id="6ccfa-135">작성 된 쿠키에 대 한 "HttpOnly" 플래그는 내보내집니다 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-135">Controls whether the "HttpOnly" flag is emitted for any cookies written.</span></span> <span data-ttu-id="6ccfa-136">특정 웹 브라우저는 클라이언트 쪽 스크립트가 쿠키 값에 액세스 하지 못하도록 하 여이 플래그를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-136">Certain web browsers honor this flag by keeping client-side script from accessing the cookie value.</span></span> <span data-ttu-id="6ccfa-137">기본값은 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-137">The default is "true".</span></span>|  
|<span data-ttu-id="6ccfa-138">도메인</span><span class="sxs-lookup"><span data-stu-id="6ccfa-138">domain</span></span>|<span data-ttu-id="6ccfa-139">작성 된 모든 쿠키에 대 한 도메인 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-139">The domain value for any cookies written.</span></span> <span data-ttu-id="6ccfa-140">기본값은 ""입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-140">The default is "".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ccfa-141">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6ccfa-141">Child Elements</span></span>  
  
|<span data-ttu-id="6ccfa-142">요소</span><span class="sxs-lookup"><span data-stu-id="6ccfa-142">Element</span></span>|<span data-ttu-id="6ccfa-143">설명</span><span class="sxs-lookup"><span data-stu-id="6ccfa-143">Description</span></span>|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](chunkedcookiehandler.md)|<span data-ttu-id="6ccfa-144">를 구성 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-144">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="6ccfa-145">`mode` `<cookieHandler>` 요소의 특성이 "Default" 또는 "청크 분할" 인 경우에만이 요소가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-145">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>|  
|[\<customCookieHandler>](customcookiehandler.md)|<span data-ttu-id="6ccfa-146">사용자 지정 쿠키 처리기 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-146">Sets the custom cookie handler type.</span></span> <span data-ttu-id="6ccfa-147">`mode` `<cookieHandler>` 요소의 특성이 "Custom" 이면이 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-147">This element must be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="6ccfa-148">특성의 다른 값에 대해서는 사용할 수 없습니다 `mode` .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-148">It cannot be present for any other values of the `mode` attribute.</span></span> <span data-ttu-id="6ccfa-149">사용자 지정 형식은 클래스에서 파생 되어야 합니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-149">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ccfa-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6ccfa-150">Parent Elements</span></span>  
  
|<span data-ttu-id="6ccfa-151">요소</span><span class="sxs-lookup"><span data-stu-id="6ccfa-151">Element</span></span>|<span data-ttu-id="6ccfa-152">설명</span><span class="sxs-lookup"><span data-stu-id="6ccfa-152">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="6ccfa-153"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) 및 (SAM)을 구성 하는 설정을 포함 합니다 <xref:System.IdentityModel.Services.SessionAuthenticationModule> .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-153">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ccfa-154">설명</span><span class="sxs-lookup"><span data-stu-id="6ccfa-154">Remarks</span></span>  

 <span data-ttu-id="6ccfa-155">는 <xref:System.IdentityModel.Services.CookieHandler> HTTP 프로토콜 수준에서 원시 쿠키를 읽고 쓰는 역할을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-155">The <xref:System.IdentityModel.Services.CookieHandler> is responsible for reading and writing raw cookies at the HTTP protocol level.</span></span> <span data-ttu-id="6ccfa-156"><xref:System.IdentityModel.Services.ChunkedCookieHandler>또는 클래스에서 파생 된 사용자 지정 쿠키 처리기를 구성할 수 있습니다 <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-156">You can configure either a <xref:System.IdentityModel.Services.ChunkedCookieHandler> or a custom cookie handler derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="6ccfa-157">청크 분할 된 쿠키 처리기를 구성 하려면 mode 특성을 "청크 분할" 또는 "기본값"으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-157">To configure a chunked cookie handler, set the mode attribute to "Chunked" or "Default".</span></span> <span data-ttu-id="6ccfa-158">기본 청크 크기는 2000 바이트 이지만 선택적으로 자식 요소를 포함 하 여 다른 청크 크기를 지정할 수 있습니다 `<chunkedCookieHandler>` .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-158">The default chunk size is 2000 bytes, but you may optionally specify a different chunk size by including a `<chunkedCookieHandler>` child element.</span></span>  
  
 <span data-ttu-id="6ccfa-159">사용자 지정 쿠키 처리기를 구성 하려면 mode 특성을 "Custom"으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-159">To configure a custom cookie handler, set the mode attribute to "Custom".</span></span> <span data-ttu-id="6ccfa-160">또한 `<customCookieHandler>` 사용자 지정 처리기의 형식을 참조 하는 자식 요소를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-160">You must also specify a `<customCookieHandler>` child element that references the type of your custom handler.</span></span>  
  
 <span data-ttu-id="6ccfa-161">합니다 `<cookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.CookieHandlerElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-161">The `<cookieHandler>` element is represented by the <xref:System.IdentityModel.Services.CookieHandlerElement> class.</span></span> <span data-ttu-id="6ccfa-162">구성에 지정 된 쿠키 처리기는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> 속성에 설정 된 개체의 속성에서 사용할 수 있습니다 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-162">The cookie handler that was specified in configuration is available from the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> property of the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ccfa-163">예제</span><span class="sxs-lookup"><span data-stu-id="6ccfa-163">Example</span></span>  

 <span data-ttu-id="6ccfa-164">다음 XML에서는 요소를 보여 줍니다 `<cookieHandler>` .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-164">The following XML shows a `<cookieHandler>` element.</span></span> <span data-ttu-id="6ccfa-165">이 예제에서는 특성을 지정 하지 않았기 때문에 `mode` SAM에서 기본 쿠키 처리기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-165">In this example, because the `mode` attribute is not specified, the default cookie handler will be used by the SAM.</span></span> <span data-ttu-id="6ccfa-166">클래스의 인스턴스입니다 <xref:System.IdentityModel.Services.ChunkedCookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-166">This is an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class.</span></span> <span data-ttu-id="6ccfa-167">`<chunkedCookieHandler>`자식 요소가 지정 되지 않았기 때문에 기본 청크 크기가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-167">Because the `<chunkedCookieHandler>` child element is not specified, the default chunk size will be used.</span></span> <span data-ttu-id="6ccfa-168">특성이 설정 되었으므로 HTTPS가 필요 하지 않습니다 `requireSsl` `false` .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-168">HTTPS will not be required because the `requireSsl` attribute is set `false`.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="6ccfa-169">이 예제에서는 세션 쿠키를 작성 하는 데 HTTPS가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-169">In this example, HTTPS is not required to write session cookies.</span></span> <span data-ttu-id="6ccfa-170">이는 `requireSsl` 요소의 특성이로 설정 되어 있기 때문입니다 `<cookieHandler>` `false` .</span><span class="sxs-lookup"><span data-stu-id="6ccfa-170">This is because the `requireSsl` attribute on the `<cookieHandler>` element is set to `false`.</span></span> <span data-ttu-id="6ccfa-171">이 설정은 보안 위험을 초래할 수 있으므로 대부분의 프로덕션 환경에는 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccfa-171">This setting is not recommended for most production environments as it may present a security risk.</span></span>  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ccfa-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ccfa-172">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
