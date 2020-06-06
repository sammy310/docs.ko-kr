---
title: <proxy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154792"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="c6e31-102">\<proxy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="c6e31-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="c6e31-103">프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-103">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="c6e31-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6e31-104">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6e31-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c6e31-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c6e31-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6e31-107">특성</span><span class="sxs-lookup"><span data-stu-id="c6e31-107">Attributes</span></span>  
  
|<span data-ttu-id="c6e31-108">**특성**</span><span class="sxs-lookup"><span data-stu-id="c6e31-108">**Attribute**</span></span>|<span data-ttu-id="c6e31-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="c6e31-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="c6e31-110">프록시를 자동으로 검색할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-110">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="c6e31-111">기본값은 `unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-111">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="c6e31-112">로컬 리소스에 프록시가 사용되지 않는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-112">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="c6e31-113">로컬 리소스에는 로컬 서버 ( `http://localhost` , `http://loopback` 또는 `http://127.0.0.1` )와 마침표 없는 URI ()가 포함 `http://webserver` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-113">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="c6e31-114">기본값은 `unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-114">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="c6e31-115">사용할 프록시 URI를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-115">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="c6e31-116">구성 스크립트의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-116">Specifies the location of the configuration script.</span></span> <span data-ttu-id="c6e31-117">이 특성에는 특성을 사용 하지 마십시오 `bypassonlocal` .</span><span class="sxs-lookup"><span data-stu-id="c6e31-117">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="c6e31-118">Internet Explorer 프록시 설정을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-118">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="c6e31-119">로 설정 되 면 `true` 후속 특성이 Internet Explorer 프록시 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-119">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="c6e31-120">기본값은 `unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-120">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6e31-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c6e31-121">Child Elements</span></span>  
 <span data-ttu-id="c6e31-122">없음</span><span class="sxs-lookup"><span data-stu-id="c6e31-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6e31-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c6e31-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c6e31-124">**요소**</span><span class="sxs-lookup"><span data-stu-id="c6e31-124">**Element**</span></span>|<span data-ttu-id="c6e31-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="c6e31-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c6e31-126">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c6e31-126">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c6e31-127">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-127">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="c6e31-128">텍스트 값</span><span class="sxs-lookup"><span data-stu-id="c6e31-128">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6e31-129">설명</span><span class="sxs-lookup"><span data-stu-id="c6e31-129">Remarks</span></span>  
 <span data-ttu-id="c6e31-130">`proxy`요소는 응용 프로그램에 대 한 프록시 서버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-130">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="c6e31-131">이 요소가 구성 파일에 없는 경우 .NET Framework는 Internet Explorer의 프록시 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-131">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="c6e31-132">특성 값은 `proxyaddress` 올바른 형식의 URI (Uniform Resource identifier) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-132">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="c6e31-133">`scriptLocation`특성은 프록시 구성 스크립트의 자동 검색을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-133">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="c6e31-134"><xref:System.Net.WebProxy>Internet Explorer에서 **자동 구성 스크립트 사용** 옵션을 선택 하면 클래스는 구성 스크립트 (일반적으로 이름이 지정 된 Wpad .dat)를 찾으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-134">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="c6e31-135">`bypassonlocal`이 값으로 설정 된 경우 `scriptLocation` 는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-135">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="c6e31-136">`usesystemdefault`버전 2.0로 마이그레이션하는 .NET Framework 버전 1.1 응용 프로그램의 경우 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-136">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="c6e31-137">`proxyaddress`특성이 잘못 된 기본 프록시를 지정 하는 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-137">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="c6e31-138">예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-138">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c6e31-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c6e31-139">Configuration Files</span></span>  
 <span data-ttu-id="c6e31-140">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6e31-141">예제</span><span class="sxs-lookup"><span data-stu-id="c6e31-141">Example</span></span>  
 <span data-ttu-id="c6e31-142">다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 고, 프록시 주소를 지정 하 고, 로컬 액세스를 위해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e31-142">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6e31-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6e31-143">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c6e31-144">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c6e31-144">Network Settings Schema</span></span>](index.md)
