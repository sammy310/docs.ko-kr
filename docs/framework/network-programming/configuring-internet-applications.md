---
title: 인터넷 애플리케이션 구성
description: .NET Framework에서 <system.Net> 요소를 사용하여 인터넷 애플리케이션을 구성하는 방법을 알아봅니다. 이 문서에는 예제 코드가 포함되어 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
ms.openlocfilehash: 760a4ac7cec9abeabfc372c3be5bd3860a6fb03a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502641"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="9aae5-104">인터넷 애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="9aae5-104">Configuring Internet Applications</span></span>
<span data-ttu-id="9aae5-105">[\<system.Net> 요소(네트워크 설정)](../configure-apps/file-schema/network/system-net-element-network-settings.md) 구성 요소에는 애플리케이션에 대한 네트워크 구성 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-105">The [\<system.Net> Element (Network Settings)](../configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="9aae5-106">[\<system.Net> 요소(네트워크 설정)](../configure-apps/file-schema/network/system-net-element-network-settings.md) 요소를 사용하여 프록시 서버를 설정하고, 연결 관리 매개 변수를 설정하고, 애플리케이션에 사용자 지정 인증 및 요청 모듈을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-106">Using the [\<system.Net> Element (Network Settings)](../configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="9aae5-107">[\<defaultProxy> 요소(네트워크 설정)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 요소는 `GlobalProxySelection` 클래스에서 반환된 프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-107">The [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="9aae5-108">자체적인 <xref:System.Net.HttpWebRequest.Proxy%2A> 속성이 특정 값으로 설정되지 않은 <xref:System.Net.HttpWebRequest>는 기본 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-108">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="9aae5-109">프록시 주소를 설정하는 것 이외에 프록시를 사용하지 않을 서버 주소 목록을 만들고 로컬 주소에 프록시를 사용하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-109">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="9aae5-110">Microsoft Internet Explorer 설정은 구성 설정과 결합되고 구성 설정이 우선 적용된다는 점을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-110">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="9aae5-111">다음 예제에서는 기본 프록시 서버 주소를 `http://proxyserver`로 설정하고, 로컬 주소에 프록시를 사용하지 않도록 지정하고, contoso.com 도메인에 있는 서버에 대한 모든 요청이 프록시를 바이패스하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-111">The following example sets the default proxy server address to `http://proxyserver`, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="9aae5-112">[\<connectionManagement> 요소(네트워크 설정)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) 요소를 사용하여 특정 서버 또는 모든 기타 서버에 대해 설정할 수 있는 영구 연결 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-112">Use the [\<connectionManagement> Element (Network Settings)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="9aae5-113">다음 예제에서는 애플리케이션에서 `www.contoso.com`에 대한 영구 연결 2개, IP 주소 192.168.1.2를 사용한 서버에 대한 영구 연결 4개, 모든 기타 서버에 대한 영구 연결 1개를 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-113">The following example configures the application to use two persistent connections to the server `www.contoso.com`, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="9aae5-114">사용자 지정 인증 모듈은 [\<authenticationModules> 요소(네트워크 설정)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) 요소를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-114">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="9aae5-115">사용자 지정 인증 모듈은 <xref:System.Net.IAuthenticationModule> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-115">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="9aae5-116">다음 예제에서는 사용자 지정 인증 모듈을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-116">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="9aae5-117">[\<webRequestModules> 요소(네트워크 설정)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) 요소를 사용하여 애플리케이션에서 프로토콜별 모듈을 통해 인터넷 리소스의 정보를 요청하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-117">You can use the [\<webRequestModules> Element (Network Settings)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="9aae5-118">지정된 모듈은 <xref:System.Net.IWebRequestCreate> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-118">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="9aae5-119">다음 예제와 같이 구성 파일에서 사용자 지정 모듈을 지정하여 기본 HTTP, HTTPS 및 파일 요청 모듈을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aae5-119">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9aae5-120">참조</span><span class="sxs-lookup"><span data-stu-id="9aae5-120">See also</span></span>

- [<span data-ttu-id="9aae5-121">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="9aae5-121">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="9aae5-122">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9aae5-122">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="9aae5-123">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9aae5-123">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
