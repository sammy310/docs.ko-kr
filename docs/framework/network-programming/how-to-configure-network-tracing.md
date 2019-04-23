---
title: '방법: 네트워크 추적 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
ms.openlocfilehash: cc08faba7edede3dd527b7c05fe47f6408e18a04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151556"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="826b9-102">방법: 네트워크 추적 구성</span><span class="sxs-lookup"><span data-stu-id="826b9-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="826b9-103">애플리케이션 또는 컴퓨터 구성 파일은 형식과 네트워크 추적의 내용을 결정하는 설정을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="826b9-104">이 절차를 수행하기 전에 추적이 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="826b9-105">추적을 사용하는 방법에 대한 자세한 내용은 [네트워크 추적 사용](../../../docs/framework/network-programming/enabling-network-tracing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="826b9-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="826b9-106">컴퓨터 구성 파일인 machine.config는 Windows가 설치된 디렉터리의 %Windir%\Microsoft.NET\Framework 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="826b9-107">컴퓨터에 설치된 .NET Framework의 각 버전에 해당하는 %Windir%\Microsoft.NET\Framework 아래의 폴더에는 개별 machine.config 파일이 있습니다(예: C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config 또는 C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config).</span><span class="sxs-lookup"><span data-stu-id="826b9-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="826b9-108">이러한 설정은 컴퓨터 구성 파일보다 우선하는 애플리케이션의 구성 파일에서 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="826b9-109">네트워크 추적을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="826b9-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="826b9-110">알맞은 구성 파일에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="826b9-111">이런 설정을 위한 값과 옵션은 아래 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-111">The values and options for these settings are described in the tables below.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="System.Net" tracemode="includehex" maxdatasize="1024">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Cache">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Http">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Sockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.WebSockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="System.Net" value="Verbose"/>  
          <add name="System.Net.Cache" value="Verbose"/>  
          <add name="System.Net.Http" value="Verbose"/>  
          <add name="System.Net.Sockets" value="Verbose"/>  
          <add name="System.Net.WebSockets" value="Verbose"/>  
        </switches>  
        <sharedListeners>  
          <add name="System.Net"  
            type="System.Diagnostics.TextWriterTraceListener"  
            initializeData="network.log"
            traceOutputOptions="ProcessId, DateTime" 
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="826b9-112">`<switches>` 블록에 이름을 추가할 때, 추적 출력에는 이름과 관련된 일부 메서드에서 가져온 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="826b9-113">다음 표에서는 출력에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="826b9-114">name</span><span class="sxs-lookup"><span data-stu-id="826b9-114">Name</span></span>|<span data-ttu-id="826b9-115">출력되는 위치</span><span class="sxs-lookup"><span data-stu-id="826b9-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="826b9-116"><xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> 및 <xref:System.Net.Dns> 클래스의 일부 공용 메서드</span><span class="sxs-lookup"><span data-stu-id="826b9-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="826b9-117"><xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스의 일부 공용 메서드와 SSL 디버그 정보(잘못된 인증서, 누락된 발급자 목록 및 클라이언트 인증서 오류)</span><span class="sxs-lookup"><span data-stu-id="826b9-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="826b9-118"><xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> 및 <xref:System.Net.HttpListenerResponse> 클래스의 일부 공용 메서드.</span><span class="sxs-lookup"><span data-stu-id="826b9-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="826b9-119">`System.Net.Cache`의 일부 개인 및 내부 메서드</span><span class="sxs-lookup"><span data-stu-id="826b9-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="826b9-120"><xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> 및 <xref:System.Net.Http.WebRequestHandler> 클래스의 일부 공용 메서드.</span><span class="sxs-lookup"><span data-stu-id="826b9-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="826b9-121"><xref:System.Net.WebSockets.ClientWebSocket> 및 <xref:System.Net.WebSockets.WebSocket> 클래스의 일부 공용 메서드.</span><span class="sxs-lookup"><span data-stu-id="826b9-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="826b9-122">다음 표에 나열된 특성이 추적 출력을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="826b9-123">특성 이름</span><span class="sxs-lookup"><span data-stu-id="826b9-123">Attribute name</span></span>|<span data-ttu-id="826b9-124">특성 값</span><span class="sxs-lookup"><span data-stu-id="826b9-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="826b9-125">필수 <xref:System.String> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="826b9-126">출력의 자세한 정도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="826b9-127">올바른 값은 `Critical`, `Error`, `Verbose`, `Warning`, `Information`입니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="826b9-128">예제에 나타낸 것처럼, \<switches> 요소의 \<add name> 요소에 대해 이 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="826b9-129">이 특성이 \<source> 요소에 대해 설정되어 있는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="826b9-130">선택적 <xref:System.Int32> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="826b9-131">각 줄 추적에 포함된 네트워크 데이터의 최대 바이트 수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="826b9-132">기본값은 1024입니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="826b9-133">예제에 나타낸 것처럼, \<source> 요소에 대해 이 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="826b9-134">이 특성이 \<switches> 요소 아래의 요소에 대해 설정되어 있는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="826b9-135">선택적 <xref:System.String> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="826b9-136">16진수 및 텍스트 형식으로 프로토콜 추적을 표시하려면 `includehex`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="826b9-137">텍스트만 표시하려면 `protocolonly`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="826b9-138">기본값은 `includehex`입니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="826b9-139">예제에 나타낸 것처럼, \<switches> 요소에 대해 이 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="826b9-140">이 특성이 \<source> 요소 아래의 요소에 대해 설정되어 있는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="826b9-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="826b9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="826b9-141">See also</span></span>

- [<span data-ttu-id="826b9-142">네트워크 추적 해석</span><span class="sxs-lookup"><span data-stu-id="826b9-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)
- [<span data-ttu-id="826b9-143">.NET Framework의 네트워크 추적</span><span class="sxs-lookup"><span data-stu-id="826b9-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)
- [<span data-ttu-id="826b9-144">네트워크 추적 사용</span><span class="sxs-lookup"><span data-stu-id="826b9-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)
- [<span data-ttu-id="826b9-145">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="826b9-145">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
