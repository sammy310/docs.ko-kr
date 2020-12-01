---
title: 프록시 구성
description: 적응형 및 정적 프록시 서버를 구성하는 방법을 알아봅니다. 프록시 구성에서는 프록시 서버가 클라이언트의 리소스 요청을 처리하는 방법을 제어합니다.
ms.date: 06/18/2018
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
ms.openlocfilehash: 5094a066fe6689a1c0cda227b284accaac49ad54
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263167"
---
# <a name="proxy-configuration"></a><span data-ttu-id="8abe5-104">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="8abe5-104">Proxy Configuration</span></span>

<span data-ttu-id="8abe5-105">프록시 서버는 리소스에 대한 클라이언트 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-105">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="8abe5-106">프록시는 해당 캐시에서 요청한 리소스를 반환하거나 리소스가 있는 서버로 요청을 전달할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="8abe5-106">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="8abe5-107">원격 서버로 전송되는 요청 수를 줄여 네트워크 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-107">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="8abe5-108">프록시를 사용하여 리소스에 대한 액세스를 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-108">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="8abe5-109">적응 프록시</span><span class="sxs-lookup"><span data-stu-id="8abe5-109">Adaptive Proxies</span></span>  

 <span data-ttu-id="8abe5-110">.NET Framework에서 프록시는 적응 및 정적의 두 가지 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-110">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="8abe5-111">적응 프록시는 네트워크 구성이 변경되면 설정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-111">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="8abe5-112">예를 들어 랩톱 사용자가 전화 접속 네트워크 연결을 시작하면 적응 프록시가 해당 변경을 인식하여 새 구성 스크립트를 검색 및 실행하고 설정을 적절하게 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-112">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="8abe5-113">구성 스크립트를 통해 적응 프록시를 구성합니다([자동 프록시 검색](automatic-proxy-detection.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="8abe5-113">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](automatic-proxy-detection.md)).</span></span> <span data-ttu-id="8abe5-114">스크립트는 애플리케이션 프로토콜 집합과 각 프로토콜용 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-114">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="8abe5-115">네트워크 환경이 변경되는 경우에는 시스템에서 새 프록시 집합을 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-115">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="8abe5-116">네트워크 연결이 다운되거나 새 네트워크 연결이 초기화되면 시스템은 새 환경에서 적절한 구성 스크립트 소스를 찾아 새 스크립트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-116">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="8abe5-117">구성 파일에서 [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) 요소의 `usesystemdefault` 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-117">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="8abe5-118">`usesystemdefault` 특성은 정적 프록시 설정(프록시 주소, 바이패스 목록, 로컬에서 바이패스)을 사용자의 Internet Explorer 프록시 설정에서 읽어야 하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-118">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="8abe5-119">이 값을 `true`로 설정하면 Internet Explorer의 정적 프록시 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-119">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="8abe5-120">이 값을 `false`로 설정하거나 설정하지 않으면 구성에서 정적 프록시 설정을 지정할 수 있으며 Internet Explorer 프록시 설정은 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-120">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="8abe5-121">적응 프록시를 사용하도록 설정하려는 경우에도 이 값을 `false`로 설정하거나 설정하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-121">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="8abe5-122">다음 예제에서는 일반적인 적응 프록시 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-122">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="8abe5-123">정적 프록시</span><span class="sxs-lookup"><span data-stu-id="8abe5-123">Static Proxies</span></span>  

 <span data-ttu-id="8abe5-124">정적 프록시는 보통 애플리케이션에 의해 명시적으로 구성되거나 애플리케이션 또는 시스템에서 구성 파일을 호출할 때 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-124">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="8abe5-125">정적 프록시는 회사 네트워크에 연결된 데스크톱 컴퓨터와 같이 토폴로지가 자주 변경되지 않는 네트워크에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-125">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="8abe5-126">정적 프록시 작동 방식은 여러 옵션으로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-126">Several options control how a static proxy operates.</span></span> <span data-ttu-id="8abe5-127">다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-127">You can specify the following:</span></span>  
  
- <span data-ttu-id="8abe5-128">프록시의 주소</span><span class="sxs-lookup"><span data-stu-id="8abe5-128">The address of the proxy.</span></span>  
  
- <span data-ttu-id="8abe5-129">로컬 주소에 대해 프록시를 바이패스해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="8abe5-129">Whether the proxy should be bypassed for local addresses.</span></span>  
  
- <span data-ttu-id="8abe5-130">주소 집합에 대해 프록시를 바이패스해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="8abe5-130">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="8abe5-131">다음 테이블에는 정적 프록시의 구성 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-131">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="8abe5-132">특성, 속성 또는 구성 파일 설정</span><span class="sxs-lookup"><span data-stu-id="8abe5-132">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="8abe5-133">설명</span><span class="sxs-lookup"><span data-stu-id="8abe5-133">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="8abe5-134">`proxyaddress` 또는 <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="8abe5-134">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="8abe5-135">사용할 프록시의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-135">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="8abe5-136">`bypassonlocal` 또는 <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="8abe5-136">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="8abe5-137">로컬 주소에 대해 프록시를 바이패스하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-137">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="8abe5-138">`bypasslist` 또는 <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="8abe5-138">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="8abe5-139">정규식을 사용하여 프록시를 바이패스하는 주소 집합을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-139">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="8abe5-140">정적 프록시 설정(프록시 주소, 바이패스 목록, 로컬에서 바이패스)을 사용자의 Internet Explorer 프록시 설정에서 읽어야 하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-140">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="8abe5-141">이 값을 `true`로 설정하면 Internet Explorer의 정적 프록시 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-141">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="8abe5-142">.NET Framework 2.0에서는 이 값을 `true`로 설정하면 Internet Explorer 프록시 설정이 구성 파일의 다른 프록시 설정으로 재정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-142">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="8abe5-143">.NET Framework 1.1에서는 구성 파일의 다른 프록시 설정으로 Internet Explorer 프록시 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-143">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="8abe5-144">이 값을 `false`로 설정하거나 설정하지 않으면 구성에서 정적 프록시 설정을 지정할 수 있으며 Internet Explorer 프록시 설정은 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-144">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="8abe5-145">적응 프록시를 사용하도록 설정하려는 경우에도 이 값을 `false`로 설정하거나 설정하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-145">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="8abe5-146">다음 예제에서는 일반적인 정적 프록시 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8abe5-146">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="True"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8abe5-147">참조</span><span class="sxs-lookup"><span data-stu-id="8abe5-147">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="8abe5-148">자동 프록시 검색</span><span class="sxs-lookup"><span data-stu-id="8abe5-148">Automatic Proxy Detection</span></span>](automatic-proxy-detection.md)
