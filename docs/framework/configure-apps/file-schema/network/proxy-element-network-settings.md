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
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089186"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="ea8ff-102">\<proxy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="ea8ff-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="ea8ff-103">프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-103">Defines a proxy server.</span></span>  

<span data-ttu-id="ea8ff-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea8ff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ea8ff-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="ea8ff-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="ea8ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ea8ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\</span></span>
<span data-ttu-id="ea8ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**프록시 >**</span><span class="sxs-lookup"><span data-stu-id="ea8ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ea8ff-108">구문</span><span class="sxs-lookup"><span data-stu-id="ea8ff-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea8ff-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ea8ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ea8ff-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea8ff-111">특성</span><span class="sxs-lookup"><span data-stu-id="ea8ff-111">Attributes</span></span>  
  
|<span data-ttu-id="ea8ff-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="ea8ff-112">**Attribute**</span></span>|<span data-ttu-id="ea8ff-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="ea8ff-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="ea8ff-114">프록시가 자동으로 검색 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="ea8ff-115">기본값은 `unspecified`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="ea8ff-116">로컬 리소스에 대해 프록시를 바이패스 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="ea8ff-117">로컬 리소스에는 로컬 서버 (`http://localhost`, `http://loopback`또는 `http://127.0.0.1`)와 마침표 없이 URI (`http://webserver`)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="ea8ff-118">기본값은 `unspecified`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="ea8ff-119">사용할 프록시 URI를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="ea8ff-120">구성 스크립트의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="ea8ff-121">이 특성에 `bypassonlocal` 특성을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="ea8ff-122">Internet Explorer 프록시 설정을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="ea8ff-123">`true`로 설정 되 면 후속 특성이 Internet Explorer 프록시 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="ea8ff-124">기본값은 `unspecified`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea8ff-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ea8ff-125">Child Elements</span></span>  
 <span data-ttu-id="ea8ff-126">없음.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea8ff-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ea8ff-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ea8ff-128">**요소**</span><span class="sxs-lookup"><span data-stu-id="ea8ff-128">**Element**</span></span>|<span data-ttu-id="ea8ff-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="ea8ff-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ea8ff-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="ea8ff-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="ea8ff-131">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="ea8ff-132">텍스트 값</span><span class="sxs-lookup"><span data-stu-id="ea8ff-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea8ff-133">주의</span><span class="sxs-lookup"><span data-stu-id="ea8ff-133">Remarks</span></span>  
 <span data-ttu-id="ea8ff-134">`proxy` 요소는 응용 프로그램에 대 한 프록시 서버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="ea8ff-135">이 요소가 구성 파일에 없는 경우 .NET Framework는 Internet Explorer의 프록시 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="ea8ff-136">`proxyaddress` 특성에 대 한 값은 올바른 형식의 URI (Uniform Resource Identifier) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="ea8ff-137">`scriptLocation` 특성은 프록시 구성 스크립트의 자동 검색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="ea8ff-138">Internet Explorer에서 **자동 구성 스크립트 사용** 옵션을 선택 하면 <xref:System.Net.WebProxy> 클래스가 구성 스크립트 (일반적으로 이름이 지정 된 Wpad .dat)를 찾으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="ea8ff-139">`bypassonlocal` 값으로 설정 된 경우 `scriptLocation`는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="ea8ff-140">버전 2.0로 마이그레이션하는 .NET Framework 버전 1.1 응용 프로그램에 `usesystemdefault` 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="ea8ff-141">`proxyaddress` 특성이 잘못 된 기본 프록시를 지정 하는 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="ea8ff-142">예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ea8ff-143">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ea8ff-143">Configuration Files</span></span>  
 <span data-ttu-id="ea8ff-144">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea8ff-145">예제</span><span class="sxs-lookup"><span data-stu-id="ea8ff-145">Example</span></span>  
 <span data-ttu-id="ea8ff-146">다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 고, 프록시 주소를 지정 하 고, 로컬 액세스를 위해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8ff-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea8ff-147">참조</span><span class="sxs-lookup"><span data-stu-id="ea8ff-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ea8ff-148">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ea8ff-148">Network Settings Schema</span></span>](index.md)
