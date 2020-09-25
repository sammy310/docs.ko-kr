---
title: <proxy> 요소(네트워크 설정)
description: <proxy>네트워크 설정 요소는 .NET Framework의 프록시 서버 옵션을 정의 합니다. 이 문서에는 예제가 포함 되어 있습니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 54b324dcd27d5827159bc2d773365e388a367d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190217"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="7a87e-104">\<proxy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="7a87e-104">\<proxy> Element (Network Settings)</span></span>

<span data-ttu-id="7a87e-105">프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="7a87e-106">구문</span><span class="sxs-lookup"><span data-stu-id="7a87e-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a87e-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7a87e-107">Attributes and Elements</span></span>  

 <span data-ttu-id="7a87e-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a87e-109">특성</span><span class="sxs-lookup"><span data-stu-id="7a87e-109">Attributes</span></span>  
  
|<span data-ttu-id="7a87e-110">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="7a87e-110">**Attribute**</span></span>|<span data-ttu-id="7a87e-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="7a87e-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="7a87e-112">프록시를 자동으로 검색할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="7a87e-113">기본값은 `Unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-113">The default value is `Unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="7a87e-114">로컬 리소스에 프록시가 사용되지 않는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="7a87e-115">로컬 리소스에는 로컬 서버 ( `http://localhost` , `http://loopback` 또는 `http://127.0.0.1` )와 마침표 없는 URI ()가 포함 `http://webserver` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="7a87e-116">기본값은 `Unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-116">The default value is `Unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="7a87e-117">사용할 프록시 URI를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="7a87e-118">구성 스크립트의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="7a87e-119">이 특성에는 특성을 사용 하지 마십시오 `bypassonlocal` .</span><span class="sxs-lookup"><span data-stu-id="7a87e-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="7a87e-120">Internet Explorer 프록시 설정을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="7a87e-121">로 설정 되 면 `True` 후속 특성이 Internet Explorer 프록시 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-121">If set to `True`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="7a87e-122">기본값은 `Unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-122">The default value is `Unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a87e-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7a87e-123">Child Elements</span></span>  

 <span data-ttu-id="7a87e-124">없음</span><span class="sxs-lookup"><span data-stu-id="7a87e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a87e-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7a87e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7a87e-126">**요소**</span><span class="sxs-lookup"><span data-stu-id="7a87e-126">**Element**</span></span>|<span data-ttu-id="7a87e-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="7a87e-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7a87e-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="7a87e-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="7a87e-129">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="7a87e-130">텍스트 값</span><span class="sxs-lookup"><span data-stu-id="7a87e-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a87e-131">설명</span><span class="sxs-lookup"><span data-stu-id="7a87e-131">Remarks</span></span>  

 <span data-ttu-id="7a87e-132">`proxy`요소는 응용 프로그램에 대 한 프록시 서버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="7a87e-133">이 요소가 구성 파일에 없는 경우 .NET Framework는 Internet Explorer의 프록시 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="7a87e-134">특성 값은 `proxyaddress` 올바른 형식의 URI (Uniform Resource identifier) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="7a87e-135">`scriptLocation`특성은 프록시 구성 스크립트의 자동 검색을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="7a87e-136"><xref:System.Net.WebProxy>Internet Explorer에서 **자동 구성 스크립트 사용** 옵션을 선택 하면 클래스는 구성 스크립트 (일반적으로 이름이 지정 된 Wpad .dat)를 찾으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="7a87e-137">`bypassonlocal`이 값으로 설정 된 경우 `scriptLocation` 는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="7a87e-138">`usesystemdefault`버전 2.0로 마이그레이션하는 .NET Framework 버전 1.1 응용 프로그램의 경우 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="7a87e-139">`proxyaddress`특성이 잘못 된 기본 프록시를 지정 하는 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="7a87e-140">예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7a87e-141">구성 파일</span><span class="sxs-lookup"><span data-stu-id="7a87e-141">Configuration Files</span></span>  

 <span data-ttu-id="7a87e-142">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a87e-143">예제</span><span class="sxs-lookup"><span data-stu-id="7a87e-143">Example</span></span>  

 <span data-ttu-id="7a87e-144">다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 고, 프록시 주소를 지정 하 고, 로컬 액세스를 위해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a87e-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a87e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a87e-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="7a87e-146">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7a87e-146">Network Settings Schema</span></span>](index.md)
