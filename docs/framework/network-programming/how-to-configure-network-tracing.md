---
title: '방법: 네트워크 추적 구성'
description: 컴퓨터 구성 파일 또는 애플리케이션 구성 파일에서 네트워크 추적을 구성하는 방법을 알아봅니다. 애플리케이션 구성 파일이 우선적으로 적용됩니다.
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
ms.openlocfilehash: b089746e9838c591ed5ccc9ac9aaeedb217de9a9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502563"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="03ba1-104">방법: 네트워크 추적 구성</span><span class="sxs-lookup"><span data-stu-id="03ba1-104">How to: Configure network tracing</span></span>

<span data-ttu-id="03ba1-105">애플리케이션 또는 컴퓨터 구성 파일은 형식과 네트워크 추적의 내용을 결정하는 설정을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-105">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="03ba1-106">이 절차를 수행하기 전에 추적이 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-106">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="03ba1-107">자세한 내용은 [네트워크 추적 사용](enabling-network-tracing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03ba1-107">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="03ba1-108">컴퓨터 구성 파일인 *machine.config*는 *%windir%\Microsoft.NET\Framework* 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-108">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="03ba1-109">컴퓨터에 설치된 각 .NET Framework 버전에 해당하는 *%windir%\Microsoft.NET\Framework* 아래의 폴더에 개별 *machine.config* 파일이 있습니다. 예:</span><span class="sxs-lookup"><span data-stu-id="03ba1-109">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="03ba1-110">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="03ba1-110">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="03ba1-111">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="03ba1-111">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="03ba1-112">이러한 설정은 컴퓨터 구성 파일보다 우선하는 애플리케이션의 구성 파일에서 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-112">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="03ba1-113">네트워크 추적 구성</span><span class="sxs-lookup"><span data-stu-id="03ba1-113">Configure network tracing</span></span>

<span data-ttu-id="03ba1-114">네트워크 추적을 구성하려면 해당 구성 파일에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-114">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="03ba1-115">이런 설정을 위한 값과 옵션은 아래 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-115">The values and options for these settings are described in the tables below.</span></span>

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

### <a name="trace-output-from-methods"></a><span data-ttu-id="03ba1-116">메서드의 추적 출력</span><span class="sxs-lookup"><span data-stu-id="03ba1-116">Trace output from methods</span></span>

<span data-ttu-id="03ba1-117">`<switches>` 블록에 이름을 추가할 때, 추적 출력에는 이름과 관련된 일부 메서드에서 가져온 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-117">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="03ba1-118">다음 표에서는 출력을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-118">The following table describes the output:</span></span>

|<span data-ttu-id="03ba1-119">이름</span><span class="sxs-lookup"><span data-stu-id="03ba1-119">Name</span></span>|<span data-ttu-id="03ba1-120">출력되는 위치</span><span class="sxs-lookup"><span data-stu-id="03ba1-120">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="03ba1-121"><xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> 및 <xref:System.Net.Dns> 클래스의 일부 퍼블릭 메서드</span><span class="sxs-lookup"><span data-stu-id="03ba1-121">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="03ba1-122"><xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스의 일부 퍼블릭 메서드와 SSL 디버그 정보(잘못된 인증서, 누락된 발급자 목록, 클라이언트 인증서 오류)</span><span class="sxs-lookup"><span data-stu-id="03ba1-122">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="03ba1-123"><xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> 및 <xref:System.Net.HttpListenerResponse> 클래스의 일부 공용 메서드.</span><span class="sxs-lookup"><span data-stu-id="03ba1-123">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="03ba1-124">`System.Net.Cache`의 일부 개인 및 내부 메서드</span><span class="sxs-lookup"><span data-stu-id="03ba1-124">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="03ba1-125"><xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> 및 <xref:System.Net.Http.WebRequestHandler> 클래스의 일부 공용 메서드.</span><span class="sxs-lookup"><span data-stu-id="03ba1-125">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="03ba1-126"><xref:System.Net.WebSockets.ClientWebSocket> 및 <xref:System.Net.WebSockets.WebSocket> 클래스의 일부 공용 메서드.</span><span class="sxs-lookup"><span data-stu-id="03ba1-126">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="03ba1-127">추적 출력 특성</span><span class="sxs-lookup"><span data-stu-id="03ba1-127">Trace output attributes</span></span>

<span data-ttu-id="03ba1-128">다음 표에 나열된 특성은 추적 출력을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-128">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="03ba1-129">특성 이름</span><span class="sxs-lookup"><span data-stu-id="03ba1-129">Attribute name</span></span>|<span data-ttu-id="03ba1-130">특성 값</span><span class="sxs-lookup"><span data-stu-id="03ba1-130">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="03ba1-131">필수 <xref:System.String> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-131">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="03ba1-132">출력의 자세한 정도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-132">Sets the verbosity of the output.</span></span> <span data-ttu-id="03ba1-133">올바른 값은 `Critical`, `Error`, `Verbose`, `Warning`, `Information`입니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-133">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="03ba1-134">**switches** 요소의 **add** 요소에 이 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-134">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="03ba1-135">**source** 요소에 이 특성을 설정하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-135">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="03ba1-136">예: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="03ba1-136">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="03ba1-137">선택적 <xref:System.Int32> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-137">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="03ba1-138">각 줄 추적에 포함된 네트워크 데이터의 최대 바이트 수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-138">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="03ba1-139">기본값은 1024입니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-139">The default value is 1024.</span></span><br /><br /><span data-ttu-id="03ba1-140">**source** 요소에 이 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-140">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="03ba1-141">**switches** 요소 아래에 있는 요소에 이 특성을 설정하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-141">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="03ba1-142">예: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="03ba1-142">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="03ba1-143">선택적 <xref:System.String> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-143">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="03ba1-144">16진수 및 텍스트 형식으로 프로토콜 추적을 표시하려면 `includehex`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-144">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="03ba1-145">텍스트만 표시하려면 `protocolonly`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-145">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="03ba1-146">기본값은 `includehex`입니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-146">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="03ba1-147">**source** 요소에 이 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-147">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="03ba1-148">**switches** 요소 아래에 있는 요소에 이 특성을 설정하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ba1-148">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="03ba1-149">예: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="03ba1-149">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="03ba1-150">참조</span><span class="sxs-lookup"><span data-stu-id="03ba1-150">See also</span></span>

- [<span data-ttu-id="03ba1-151">네트워크 추적 해석</span><span class="sxs-lookup"><span data-stu-id="03ba1-151">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="03ba1-152">.NET Framework의 네트워크 추적</span><span class="sxs-lookup"><span data-stu-id="03ba1-152">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="03ba1-153">네트워크 추적 사용</span><span class="sxs-lookup"><span data-stu-id="03ba1-153">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="03ba1-154">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="03ba1-154">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
