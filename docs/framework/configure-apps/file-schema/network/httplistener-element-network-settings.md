---
title: <httpListener> 요소(네트워크 설정)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3f75096681ab07dd6d4788fbded5ca5c4a024aef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698188"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="55477-102">\<httpListener > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="55477-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="55477-103">@No__t-0 클래스에서 사용 하는 매개 변수를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
[<span data-ttu-id="55477-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="55477-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="55477-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="55477-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="55477-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="55477-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="55477-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<httpListener >**</span><span class="sxs-lookup"><span data-stu-id="55477-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55477-108">구문</span><span class="sxs-lookup"><span data-stu-id="55477-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="55477-109">type</span><span class="sxs-lookup"><span data-stu-id="55477-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55477-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="55477-110">Attributes and Elements</span></span>  
 <span data-ttu-id="55477-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55477-112">특성</span><span class="sxs-lookup"><span data-stu-id="55477-112">Attributes</span></span>  
  
|<span data-ttu-id="55477-113">특성</span><span class="sxs-lookup"><span data-stu-id="55477-113">Attribute</span></span>|<span data-ttu-id="55477-114">설명</span><span class="sxs-lookup"><span data-stu-id="55477-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55477-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="55477-115">unescapeRequestUrl</span></span>|<span data-ttu-id="55477-116">@No__t-0 인스턴스가 변환 된 URI 대신 이스케이프 되지 않은 원시 URI를 사용 하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55477-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="55477-117">Child Elements</span></span>  
 <span data-ttu-id="55477-118">없음</span><span class="sxs-lookup"><span data-stu-id="55477-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55477-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="55477-119">Parent Elements</span></span>  
  
|<span data-ttu-id="55477-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="55477-120">**Element**</span></span>|<span data-ttu-id="55477-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="55477-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="55477-122">settings</span><span class="sxs-lookup"><span data-stu-id="55477-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="55477-123"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55477-124">설명</span><span class="sxs-lookup"><span data-stu-id="55477-124">Remarks</span></span>  
 <span data-ttu-id="55477-125">**UnescapeRequestUrl** 특성은% 인코딩된 값이 변환 되 고 다른 정규화 단계가 수행 되는 경우-1 @no__t 변환 된 uri 대신 이스케이프 되지 않은 원시 uri를 사용 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55477-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="55477-126">경우는 <xref:System.Net.HttpListener> 인스턴스를 통해 요청을 수신 합니다 `http.sys` 제공한 URI 문자열의 인스턴스를 만들고 서비스를 `http.sys`,으로 노출를 <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="55477-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="55477-127">`http.sys` 서비스는 두 요청 URI 문자열을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="55477-128">원시 URI</span><span class="sxs-lookup"><span data-stu-id="55477-128">Raw URI</span></span>  
  
- <span data-ttu-id="55477-129">변환 된 URI</span><span class="sxs-lookup"><span data-stu-id="55477-129">Converted URI</span></span>  
  
 <span data-ttu-id="55477-130">원시 URI가는 <xref:System.Uri?displayProperty=nameWithType> HTTP 요청의 요청 줄에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="55477-131">제공 된 URI의 원시 `http.sys` 위에서 언급 한 요청에 "경로 /"입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="55477-132">이 네트워크를 통해 전송 된 HTTP 동사를 다음 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55477-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="55477-133">`http.sys` 서비스는 HTTP 요청에서에서 제공 하는 URI를 사용 하 여 요청에 제공 된 정보에서 변환된 된 URI를 만듭니다 및 원본 서버에서 요청을 확인 하도록 호스트 헤더를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="55477-134">이 등록 된 URI 접두사를 사용 하 여 요청에서 정보를 비교 하 여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="55477-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="55477-135">HTTP 서버 SDK 설명서는 변환 된이 URI를 HTTP_COOKED_URL 구조체로 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="55477-136">등록 된 URI 접두사를 사용 하 여 요청을 비교할 수 있도록 요청에 일부 정규화를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="55477-137">변환 된 URI 위의 샘플은 다음과 같을 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55477-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="55477-138">합니다 `http.sys` 결합 서비스는 <xref:System.Uri.Host%2A?displayProperty=nameWithType> 속성 값과 문자열을 변환된 된 URI를 만드는 요청 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55477-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="55477-139">또한 `http.sys` 및 <xref:System.Uri?displayProperty=nameWithType> 클래스는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="55477-140">이스케이프 해제 인코딩된 모든 백분율 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="55477-141">Utf-16 문자 표현으로 변환 백분율로 인코딩된 비 ASCII 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="55477-142">유니코드 문자 (유니코드 %uXXXX 형식을 사용 하 여 인코딩) 및 u t F-8과 ANSI/DBCS 문자는 사용할 수는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="55477-143">경로 압축 등의 다른 정규화 단계를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="55477-144">백분율로 인코딩된 값에 사용 되는 인코딩에 대 한 정보가 요청 없으므로 백분율로 인코딩된 값을 구문 분석 하 여 올바른 인코딩을 결정 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55477-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="55477-145">따라서 `http.sys` 프로세스를 수정 하는 것에 대 한 두 개의 레지스트리 키를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="55477-146">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="55477-146">Registry Key</span></span>|<span data-ttu-id="55477-147">기본값</span><span class="sxs-lookup"><span data-stu-id="55477-147">Default Value</span></span>|<span data-ttu-id="55477-148">설명</span><span class="sxs-lookup"><span data-stu-id="55477-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="55477-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="55477-149">EnableNonUTF8</span></span>|<span data-ttu-id="55477-150">1</span><span class="sxs-lookup"><span data-stu-id="55477-150">1</span></span>|<span data-ttu-id="55477-151">0 이면 `http.sys` u t F-8로 인코딩된 Url만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="55477-152">0이 아닌 경우 `http.sys` 도 요청에서 ANSI로 인코딩된 또는 DBCS 인코딩된 Url을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="55477-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="55477-153">FavorUTF8</span></span>|<span data-ttu-id="55477-154">1</span><span class="sxs-lookup"><span data-stu-id="55477-154">1</span></span>|<span data-ttu-id="55477-155">0이 아닌 경우 `http.sys` 디코딩할 URL u t F-8로 먼저 해당 변환에 실패 이며 EnableNonUTF8 0이 아닌 경우 항상 시도 차례로 Http.sys을 ANSI 또는 DBCS 디코딩해야 하는 작업을 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="55477-156">0 (그리고 EnableNonUTF8 0이 아닌 경우) `http.sys` 있는지을 ANSI 또는 DBCS; 디코딩 하려고 성공 하면를 u t F-8로 변환 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="55477-157">때 <xref:System.Net.HttpListener> 요청이 수신에서 변환 된 URI를 사용 하 여 `http.sys` 대 한 입력으로 <xref:System.Net.HttpListenerRequest.Url%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="55477-158">Uri에서 문자 및 숫자 이외의 문자를 지원할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55477-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="55477-159">예로 고객에 대 한 고객 정보를 검색 하는 데 사용 되는 다음 URI를 "1/3812" 번호:</span><span class="sxs-lookup"><span data-stu-id="55477-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="55477-160">Uri (%2F)의 백분율로 인코딩된 슬래시를 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="55477-161">이것이 필요 하므로 경우 슬래시 문자 데이터 및 경로 구분 기호가 아니라입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="55477-162">Uri 생성자에 문자열을 전달에 다음 URI를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="55477-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="55477-163">경로를 세그먼트로 분한 다음 요소에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="55477-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="55477-164">요청을 보낸 사람의 의도 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="55477-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="55477-165">**UnescapeRequestUrl** 특성이 **false**로 설정 된 경우 <xref:System.Net.HttpListener>가 요청을 받으면 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 `http.sys`의 변환 된 uri 대신 원시 uri를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55477-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="55477-166">**UnescapeRequestUrl** 특성의 기본값은 **true**입니다.</span><span class="sxs-lookup"><span data-stu-id="55477-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="55477-167">@No__t-0 속성은 적용 가능한 구성 파일에서 **unescapeRequestUrl** 특성의 현재 값을 가져오는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55477-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55477-168">예제</span><span class="sxs-lookup"><span data-stu-id="55477-168">Example</span></span>  
 <span data-ttu-id="55477-169">다음 예제에서는 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 `http.sys`의 변환 된 URI 대신 원시 URI를 사용 하는 요청을 받을 때 <xref:System.Net.HttpListener> 클래스를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55477-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="55477-170">요소 정보</span><span class="sxs-lookup"><span data-stu-id="55477-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="55477-171">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="55477-171">Namespace</span></span>|<span data-ttu-id="55477-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="55477-172">System.Net</span></span>|  
|<span data-ttu-id="55477-173">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="55477-173">Schema Name</span></span>||  
|<span data-ttu-id="55477-174">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="55477-174">Validation File</span></span>||  
|<span data-ttu-id="55477-175">비워 둘 수 있음</span><span class="sxs-lookup"><span data-stu-id="55477-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="55477-176">참조</span><span class="sxs-lookup"><span data-stu-id="55477-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="55477-177">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="55477-177">Network Settings Schema</span></span>](index.md)
