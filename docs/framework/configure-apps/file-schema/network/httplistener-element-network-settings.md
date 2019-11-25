---
title: <httpListener> 요소(네트워크 설정)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088384"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="ee9af-102">\<httpListener > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="ee9af-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="ee9af-103"><xref:System.Net.HttpListener> 클래스에서 사용 하는 매개 변수를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

<span data-ttu-id="ee9af-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ee9af-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ee9af-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="ee9af-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="ee9af-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<설정**](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="ee9af-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="ee9af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpListener >**</span><span class="sxs-lookup"><span data-stu-id="ee9af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ee9af-108">구문</span><span class="sxs-lookup"><span data-stu-id="ee9af-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="ee9af-109">Type</span><span class="sxs-lookup"><span data-stu-id="ee9af-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee9af-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ee9af-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ee9af-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee9af-112">특성</span><span class="sxs-lookup"><span data-stu-id="ee9af-112">Attributes</span></span>  
  
|<span data-ttu-id="ee9af-113">특성</span><span class="sxs-lookup"><span data-stu-id="ee9af-113">Attribute</span></span>|<span data-ttu-id="ee9af-114">설명</span><span class="sxs-lookup"><span data-stu-id="ee9af-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee9af-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="ee9af-115">unescapeRequestUrl</span></span>|<span data-ttu-id="ee9af-116"><xref:System.Net.HttpListener> 인스턴스가 변환 된 URI 대신 이스케이프 되지 않은 원시 URI를 사용 하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee9af-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ee9af-117">Child Elements</span></span>  
 <span data-ttu-id="ee9af-118">없음.</span><span class="sxs-lookup"><span data-stu-id="ee9af-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee9af-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ee9af-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ee9af-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="ee9af-120">**Element**</span></span>|<span data-ttu-id="ee9af-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="ee9af-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ee9af-122">설정</span><span class="sxs-lookup"><span data-stu-id="ee9af-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="ee9af-123"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee9af-124">주의</span><span class="sxs-lookup"><span data-stu-id="ee9af-124">Remarks</span></span>  
 <span data-ttu-id="ee9af-125">**UnescapeRequestUrl** 특성 은% 인코딩된 값이 변환 되 고 다른 정규화 단계를 수행 하는 변환 된 uri 대신 이스케이프 되지 않은 원시 uri를 사용 <xref:System.Net.HttpListener> 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="ee9af-126"><xref:System.Net.HttpListener> 인스턴스가 `http.sys` 서비스를 통해 요청을 받으면 `http.sys`에서 제공 하는 URI 문자열의 인스턴스를 만들고 <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> 속성으로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ee9af-127">`http.sys` 서비스는 두 개의 요청 URI 문자열을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="ee9af-128">원시 URI</span><span class="sxs-lookup"><span data-stu-id="ee9af-128">Raw URI</span></span>  
  
- <span data-ttu-id="ee9af-129">변환 된 URI</span><span class="sxs-lookup"><span data-stu-id="ee9af-129">Converted URI</span></span>  
  
 <span data-ttu-id="ee9af-130">원시 URI는 HTTP 요청의 요청 줄에 제공 된 <xref:System.Uri?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="ee9af-131">위에서 언급 한 요청에 대해 `http.sys`에서 제공 하는 원시 URI는 "/path/"입니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="ee9af-132">이는 네트워크를 통해 전송 된 HTTP 동사 뒤에 나오는 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="ee9af-133">`http.sys` 서비스는 HTTP 요청 줄에 제공 된 URI와 호스트 헤더를 사용 하 여 요청에 제공 된 정보 로부터 변환 된 URI를 만들어 요청을 전달 해야 하는 원본 서버를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="ee9af-134">요청의 정보를 등록 된 URI 접두사 집합과 비교 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="ee9af-135">HTTP 서버 SDK 설명서는 HTTP_COOKED_URL 구조체로 변환 된이 URI를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="ee9af-136">요청을 등록 된 URI 접두사와 비교할 수 있으려면 요청에 대 한 일부 정규화를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="ee9af-137">위의 샘플에서 변환 된 URI는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="ee9af-138">`http.sys` 서비스는 <xref:System.Uri.Host%2A?displayProperty=nameWithType> 속성 값과 요청 줄의 문자열을 결합 하 여 변환 된 URI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="ee9af-139">또한 `http.sys` 및 <xref:System.Uri?displayProperty=nameWithType> 클래스는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="ee9af-140">모든% 인코딩된 값을 이스케이프 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="ee9af-141">백분율 인코딩된 ASCII가 아닌 문자를 UTF-16 문자 표현으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="ee9af-142">UTF-8 및 ANSI/DBCS 문자는 유니코드 문자 (% uXXXX 형식을 사용 하는 유니코드 인코딩)와도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="ee9af-143">경로 압축과 같은 다른 정규화 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="ee9af-144">요청은 백분율 인코딩 값에 사용 된 인코딩에 대 한 정보를 포함 하지 않으므로 백분율 인코딩된 값을 구문 분석 하 여 올바른 인코딩을 결정 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="ee9af-145">따라서 `http.sys`는 프로세스를 수정 하기 위한 두 개의 레지스트리 키를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="ee9af-146">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="ee9af-146">Registry Key</span></span>|<span data-ttu-id="ee9af-147">기본값</span><span class="sxs-lookup"><span data-stu-id="ee9af-147">Default Value</span></span>|<span data-ttu-id="ee9af-148">설명</span><span class="sxs-lookup"><span data-stu-id="ee9af-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="ee9af-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="ee9af-149">EnableNonUTF8</span></span>|<span data-ttu-id="ee9af-150">1</span><span class="sxs-lookup"><span data-stu-id="ee9af-150">1</span></span>|<span data-ttu-id="ee9af-151">0 인 경우 u t f-8로 인코딩된 Url만 허용 `http.sys`.</span><span class="sxs-lookup"><span data-stu-id="ee9af-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="ee9af-152">0이 아닌 경우, `http.sys`는 요청에서 ANSI 인코딩 또는 DBCS 인코딩된 Url도 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="ee9af-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="ee9af-153">FavorUTF8</span></span>|<span data-ttu-id="ee9af-154">1</span><span class="sxs-lookup"><span data-stu-id="ee9af-154">1</span></span>|<span data-ttu-id="ee9af-155">0이 아닌 경우 `http.sys` 항상 URL을 u t f-8로 디코드 하려고 시도 합니다. 이 변환이 실패 하 고 EnableNonUTF8가 0이 아닌 경우 Http.sys는 ANSI 또는 DBCS로 디코드 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="ee9af-156">0 (및 EnableNonUTF8가 0이 아닌 경우)은이를 ANSI 또는 DBCS로 디코드 하려고 시도 `http.sys` 합니다. 성공 하지 못하면 UTF-8 변환을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="ee9af-157"><xref:System.Net.HttpListener>에서 요청을 받으면 `http.sys`의 변환 된 URI를 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="ee9af-158">Uri에서 문자 및 숫자 이외의 문자를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="ee9af-159">예를 들어 다음 URI는 고객 번호 "1/3812"에 대 한 고객 정보를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="ee9af-160">Uri (% 2F)의 백분율 인코딩된 슬래시를 적어둡니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="ee9af-161">이 경우 슬래시 문자는 데이터를 나타내지만 경로 구분 기호는 아니기 때문에이 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="ee9af-162">Uri 생성자에 문자열을 전달 하면 다음 URI가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="ee9af-163">경로를 해당 세그먼트로 분할 하면 다음 요소가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="ee9af-164">이것은 요청을 보낸 사람의 의도가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="ee9af-165">**UnescapeRequestUrl** 특성을 **false**로 설정 하면 <xref:System.Net.HttpListener> 요청을 받을 때 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 `http.sys`에서 변환 된 uri 대신 원시 uri를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="ee9af-166">**UnescapeRequestUrl** 특성의 기본값은 **true**입니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="ee9af-167"><xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> 속성을 사용 하 여 적용 가능한 구성 파일에서 **unescapeRequestUrl** 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee9af-168">예제</span><span class="sxs-lookup"><span data-stu-id="ee9af-168">Example</span></span>  
 <span data-ttu-id="ee9af-169">다음 예제에서는 `http.sys`에서 변환 된 URI 대신 원시 URI를 사용 하 여 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 사용 하는 요청을 받을 때 <xref:System.Net.HttpListener> 클래스를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee9af-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="ee9af-170">요소 정보</span><span class="sxs-lookup"><span data-stu-id="ee9af-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="ee9af-171">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ee9af-171">Namespace</span></span>|<span data-ttu-id="ee9af-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="ee9af-172">System.Net</span></span>|  
|<span data-ttu-id="ee9af-173">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="ee9af-173">Schema Name</span></span>||  
|<span data-ttu-id="ee9af-174">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="ee9af-174">Validation File</span></span>||  
|<span data-ttu-id="ee9af-175">비워 둘 수 있음</span><span class="sxs-lookup"><span data-stu-id="ee9af-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="ee9af-176">참조</span><span class="sxs-lookup"><span data-stu-id="ee9af-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="ee9af-177">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ee9af-177">Network Settings Schema</span></span>](index.md)
