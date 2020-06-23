---
title: 바인딩 및 보안
description: 보안 요구 사항에 적합 한 바인딩을 선택 하는 방법을 알아보세요. WCF에 포함 된 시스템 제공 바인딩은 WCF 응용 프로그램을 신속 하 게 프로그래밍 하는 방법을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: e012ec9ad340c74f5bc776cfc6d8b88326210fec
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245337"
---
# <a name="bindings-and-security"></a><span data-ttu-id="846a3-104">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="846a3-104">Bindings and Security</span></span>

<span data-ttu-id="846a3-105">WCF (Windows Communication Foundation)에 포함 된 시스템 제공 바인딩은 WCF 응용 프로그램을 신속 하 게 프로그래밍할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-105">The system-provided bindings included with Windows Communication Foundation (WCF) offer a quick way to program WCF applications.</span></span> <span data-ttu-id="846a3-106">한 가지 예외를 통해 모든 바인딩의 기본 보안 스키마가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-106">With one exception, all the bindings have a default security scheme enabled.</span></span> <span data-ttu-id="846a3-107">이 항목은 보안 요구 사항에 적합한 바인딩을 선택하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-107">This topic helps you select the right binding for your security needs.</span></span>

<span data-ttu-id="846a3-108">WCF 보안에 대 한 개요는 [보안 개요](security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-108">For an overview of WCF security, see [Security Overview](security-overview.md).</span></span> <span data-ttu-id="846a3-109">바인딩을 사용 하 여 WCF를 프로그래밍 하는 방법에 대 한 자세한 내용은 [Wcf 보안 프로그래밍](programming-wcf-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-109">For more information about programming WCF using bindings, see [Programming WCF Security](programming-wcf-security.md).</span></span>

<span data-ttu-id="846a3-110">바인딩을 이미 선택한 경우 [보안 동작](security-behaviors-in-wcf.md)의 보안과 관련 된 런타임 동작에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-110">If you have already selected a binding, you can find out more about the run-time behaviors that are associated with security in [Security Behaviors](security-behaviors-in-wcf.md).</span></span>

<span data-ttu-id="846a3-111">일부 보안 기능은 시스템 제공 바인딩을 사용하여 프로그래밍할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-111">Some security functions are not programmable using the system-provided bindings.</span></span> <span data-ttu-id="846a3-112">사용자 지정 바인딩을 사용 하는 더 많은 제어를 위해 [사용자 지정 바인딩을](security-capabilities-with-custom-bindings.md)사용 하는 보안 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-112">For more control using a custom binding, see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md).</span></span>

## <a name="security-functions-of-bindings"></a><span data-ttu-id="846a3-113">바인딩의 보안 기능</span><span class="sxs-lookup"><span data-stu-id="846a3-113">Security Functions of Bindings</span></span>

<span data-ttu-id="846a3-114">WCF에는 대부분의 요구를 충족 하는 여러 시스템 제공 바인딩이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-114">WCF includes a number of system-provided bindings that meet most needs.</span></span> <span data-ttu-id="846a3-115">또한 특정 바인딩이 요구 사항을 충족하지 않는 경우, 사용자 지정 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-115">If a particular binding does not suffice, you can also create a custom binding.</span></span> <span data-ttu-id="846a3-116">시스템 제공 바인딩 목록은 [시스템 제공 바인딩](../system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-116">For a list of system-provided bindings, see [System-Provided Bindings](../system-provided-bindings.md).</span></span> <span data-ttu-id="846a3-117">사용자 지정 바인딩에 대 한 자세한 내용은 [사용자 지정 바인딩](../extending/custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-117">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>

<span data-ttu-id="846a3-118">WCF의 모든 바인딩에는 API와 구성 파일에 사용 되는 XML 요소로 구성 된 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-118">Every binding in WCF has two forms: as an API and as an XML element used in a configuration file.</span></span> <span data-ttu-id="846a3-119">예를 들어 `WSHttpBinding` (API)에는에 해당 하는이 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-119">For example, the `WSHttpBinding` (API) has a counterpart in the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="846a3-120">다음 단원에서는 각 바인딩에 대한 두 가지 양식을 나열하고 해당 보안 기능에 대해 요약하여 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-120">The following section lists both forms for each binding and summarizes the security features.</span></span>

### <a name="basichttp"></a><span data-ttu-id="846a3-121">BasicHttp</span><span class="sxs-lookup"><span data-stu-id="846a3-121">BasicHttp</span></span>

<span data-ttu-id="846a3-122">코드에서 클래스를 사용 <xref:System.ServiceModel.BasicHttpBinding> 합니다. 구성에서를 사용 [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-122">In code, use the <xref:System.ServiceModel.BasicHttpBinding> class; in configuration, use the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>

<span data-ttu-id="846a3-123">이 바인딩은 다음을 포함하여 일정 범위의 기존 기술을 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-123">This binding is designed for use with a range of existing technologies, including the following:</span></span>

- <span data-ttu-id="846a3-124">ASP.NET 웹 서비스(ASMX), 버전 1</span><span class="sxs-lookup"><span data-stu-id="846a3-124">ASP.NET Web services (ASMX), version 1.</span></span>

- <span data-ttu-id="846a3-125">WSE(Web Service Enhancement) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="846a3-125">Web Service Enhancements (WSE) applications.</span></span>

- <span data-ttu-id="846a3-126">WS (웹 서비스 상호 운용성) 사양 ()에 정의 된 기본 프로필 <https://go.microsoft.com/fwlink/?LinkId=38955> 입니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-126">Basic Profile as defined in the Web Services Interoperability (WS-I) specification (<https://go.microsoft.com/fwlink/?LinkId=38955>).</span></span>

- <span data-ttu-id="846a3-127">WS-I에 정의된 기본 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="846a3-127">Basic security profile as defined in WS-I.</span></span>

<span data-ttu-id="846a3-128">기본적으로 이 바인딩은 보안 처리되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-128">By default, this binding is not secure.</span></span> <span data-ttu-id="846a3-129">ASMX 서비스와 상호 운용되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-129">It is designed to interoperate with ASMX services.</span></span> <span data-ttu-id="846a3-130">보안을 사용하는 경우 바인딩은 기본 인증, 다이제스트 및 통합 Windows 보안과 같이 IIS(인터넷 정보 서비스) 보안 메커니즘과 원활한 상호 운용을 위해 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-130">When security is enabled, the binding is designed for seamless interoperation with Internet Information Services (IIS) security mechanisms, such as basic authentication, digest, and integrated Windows security.</span></span> <span data-ttu-id="846a3-131">자세한 내용은 [전송 보안 개요](transport-security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-131">For more information, see [Transport Security Overview](transport-security-overview.md).</span></span> <span data-ttu-id="846a3-132">이 바인딩은 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-132">This binding supports the following:</span></span>

- <span data-ttu-id="846a3-133">HTTPS 전송 보안.</span><span class="sxs-lookup"><span data-stu-id="846a3-133">HTTPS transport security.</span></span>

- <span data-ttu-id="846a3-134">HTTP 기본 인증.</span><span class="sxs-lookup"><span data-stu-id="846a3-134">HTTP basic authentication.</span></span>

- <span data-ttu-id="846a3-135">WS-Security.</span><span class="sxs-lookup"><span data-stu-id="846a3-135">WS-Security.</span></span>

<span data-ttu-id="846a3-136">자세한 내용은 다음을 참조하세요.<xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> 및 <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="846a3-136">For more information, see <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>, and <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>

### <a name="wshttpbinding"></a><span data-ttu-id="846a3-137">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-137">WSHttpBinding</span></span>

<span data-ttu-id="846a3-138">코드에서 클래스를 사용 <xref:System.ServiceModel.WSHttpBinding> 합니다. 구성에서를 사용 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-138">In code, use the <xref:System.ServiceModel.WSHttpBinding> class; in configuration, use the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="846a3-139">기본적으로 이 바인딩은 WS-Security 사양을 구현하고 WS-\* 사양을 구현하는 서비스와의 상호 운용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-139">By default, this binding implements the WS-Security specification and provides interoperability with services that implement the WS-\* specifications.</span></span> <span data-ttu-id="846a3-140">다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-140">It supports the following:</span></span>

- <span data-ttu-id="846a3-141">HTTPS 전송 보안.</span><span class="sxs-lookup"><span data-stu-id="846a3-141">HTTPS transport security.</span></span>

- <span data-ttu-id="846a3-142">WS-Security.</span><span class="sxs-lookup"><span data-stu-id="846a3-142">WS-Security.</span></span>

- <span data-ttu-id="846a3-143">호출자를 인증하기 위한 SOAP 메시지 자격 증명 보안을 사용하여 HTTPS 전송 보호.</span><span class="sxs-lookup"><span data-stu-id="846a3-143">HTTPS transport protection with SOAP message credential security for authenticating the caller.</span></span>

<span data-ttu-id="846a3-144">자세한 내용은,,,,, 및를 참조 하십시오 <xref:System.ServiceModel.WSHttpSecurity> <xref:System.ServiceModel.MessageSecurityOverHttp> <xref:System.ServiceModel.MessageCredentialType> <xref:System.ServiceModel.SecurityMode> <xref:System.ServiceModel.HttpTransportSecurity> <xref:System.ServiceModel.HttpClientCredentialType> <xref:System.ServiceModel.HttpProxyCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="846a3-144">For more information, see <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>, and <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>

### <a name="wsdualhttpbinding"></a><span data-ttu-id="846a3-145">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-145">WSDualHttpBinding</span></span>

<span data-ttu-id="846a3-146">코드에서 클래스를 사용 <xref:System.ServiceModel.WSDualHttpBinding> 합니다. 구성에서를 사용 [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-146">In code, use the <xref:System.ServiceModel.WSDualHttpBinding> class; in configuration, use the [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>

<span data-ttu-id="846a3-147">이 바인딩은 이중 서비스 애플리케이션을 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-147">This binding is designed to enable duplex service applications.</span></span> <span data-ttu-id="846a3-148">이 바인딩은 메시지 기반 전송 보안을 위한 WS-Security 사양을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-148">This binding implements the WS-Security specification for message-based transfer security.</span></span> <span data-ttu-id="846a3-149">전송 보안을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-149">Transport security is not available.</span></span> <span data-ttu-id="846a3-150">기본적으로 다음 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-150">By default, it provides the following features:</span></span>

- <span data-ttu-id="846a3-151">안정성을 위해 WS-Reliable Messaging을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-151">Implements WS-Reliable Messaging for reliability.</span></span>

- <span data-ttu-id="846a3-152">전송 보안 및 인증을 위해 WS-Security를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-152">Implements WS-Security for transfer security and authentication.</span></span>

- <span data-ttu-id="846a3-153">메시지 배달을 위해 HTTP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-153">Uses HTTP for message delivery.</span></span>

- <span data-ttu-id="846a3-154">텍스트/XML 메시지 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-154">Uses text/XML message encoding.</span></span>

 <span data-ttu-id="846a3-155">WS-Security(메시지 계층 보안)를 사용하면 바인딩을 통해 다음 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-155">Using WS-Security (message-layer security), the binding allows you to configure the following parameters:</span></span>

- <span data-ttu-id="846a3-156">암호화 알고리즘을 결정하기 위한 보안 알고리즘 모음.</span><span class="sxs-lookup"><span data-stu-id="846a3-156">The security algorithm suite to determine the cryptographic algorithm.</span></span>

- <span data-ttu-id="846a3-157">다음에 대한 바인딩 옵션.</span><span class="sxs-lookup"><span data-stu-id="846a3-157">Binding options for the following:</span></span>

  - <span data-ttu-id="846a3-158">클라이언트에서 서비스 자격 증명 사용 가능한 out-of-band를 제공하는 경우.</span><span class="sxs-lookup"><span data-stu-id="846a3-158">Providing service credentials available out-of-band at the client.</span></span>

  - <span data-ttu-id="846a3-159">채널 설정의 일부로 서비스에서 협상된 서비스 자격 증명을 제공하는 경우.</span><span class="sxs-lookup"><span data-stu-id="846a3-159">Providing service credentials negotiated from the service as part of channel setup.</span></span>

<span data-ttu-id="846a3-160">자세한 내용은 <xref:System.ServiceModel.WSDualHttpSecurity> 및 <xref:System.ServiceModel.WSDualHttpSecurityMode>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-160">For more information, see <xref:System.ServiceModel.WSDualHttpSecurity> and <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>

### <a name="nettcpbinding"></a><span data-ttu-id="846a3-161">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-161">NetTcpBinding</span></span>

<span data-ttu-id="846a3-162">코드에서 클래스를 사용 <xref:System.ServiceModel.NetTcpBinding> 합니다. 구성에서를 사용 [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-162">In code, use the <xref:System.ServiceModel.NetTcpBinding> class; in configuration, use the [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>

<span data-ttu-id="846a3-163">이 바인딩은 시스템 간 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-163">This binding is optimized for cross-machine communication.</span></span> <span data-ttu-id="846a3-164">기본적으로 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-164">By default, it has the following characteristics:</span></span>

- <span data-ttu-id="846a3-165">전송 계층 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-165">Implements transport-layer security.</span></span>

- <span data-ttu-id="846a3-166">전송 보안 및 인증을 위해 Windows 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-166">Leverages Windows security for transfer security and authentication.</span></span>

- <span data-ttu-id="846a3-167">전송을 위해 TCP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-167">Uses TCP for transport.</span></span>

- <span data-ttu-id="846a3-168">이진 메시지 인코딩을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-168">Implements binary message encoding.</span></span>

- <span data-ttu-id="846a3-169">WS-Reliable Messaging을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-169">Implements WS-Reliable Messaging.</span></span>

<span data-ttu-id="846a3-170">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-170">Options include the following:</span></span>

- <span data-ttu-id="846a3-171">메시지 계층 보안(WS-Security 사용).</span><span class="sxs-lookup"><span data-stu-id="846a3-171">Message-layer security (using WS-Security).</span></span>

- <span data-ttu-id="846a3-172">메시지 자격 증명을 통한 전송 보안—TCP를 통한 TLS(전송 계층 보안)에 의해 제공되는 기밀성과 무결성 및 WS-Security에 의해 제공되는 권한에 대한 자격 증명.</span><span class="sxs-lookup"><span data-stu-id="846a3-172">Transport security with message credential—confidentiality and integrity provided by Transport Layer Security (TLS) over TCP, and credentials for authorization provided by WS-Security.</span></span>

<span data-ttu-id="846a3-173">자세한 내용은,,, 및를 참조 하십시오 <xref:System.ServiceModel.NetTcpSecurity> <xref:System.ServiceModel.TcpTransportSecurity> <xref:System.ServiceModel.TcpClientCredentialType> <xref:System.ServiceModel.MessageSecurityOverTcp> <xref:System.ServiceModel.MessageCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="846a3-173">For more information, see <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>, and <xref:System.ServiceModel.MessageCredentialType>.</span></span>

### <a name="netnamedpipebinding"></a><span data-ttu-id="846a3-174">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-174">NetNamedPipeBinding</span></span>

<span data-ttu-id="846a3-175">코드에서 클래스를 사용 <xref:System.ServiceModel.NetNamedPipeBinding> 합니다. 구성에서를 사용 [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-175">In code, use the <xref:System.ServiceModel.NetNamedPipeBinding> class; in configuration, use the [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>

<span data-ttu-id="846a3-176">이 바인딩은 일반적으로 동일한 시스템에서의 프로세스 간 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-176">This binding is optimized for cross-process communication (usually on the same machine).</span></span> <span data-ttu-id="846a3-177">기본적으로 이 바인딩에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-177">By default, this binding has the following characteristics:</span></span>

- <span data-ttu-id="846a3-178">메시지 전송 및 인증을 위해 전송 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-178">Uses transport security for message transfer and authentication.</span></span>

- <span data-ttu-id="846a3-179">메시지 배달을 위해 명명된 파이프를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-179">Uses named pipes for message delivery.</span></span>

- <span data-ttu-id="846a3-180">이진 메시지 인코딩을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-180">Implements binary message encoding.</span></span>

- <span data-ttu-id="846a3-181">암호화 및 메시지 서명.</span><span class="sxs-lookup"><span data-stu-id="846a3-181">Encryption and message signing.</span></span>

<span data-ttu-id="846a3-182">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-182">Options include the following:</span></span>

- <span data-ttu-id="846a3-183">Windows 보안을 사용하여 인증.</span><span class="sxs-lookup"><span data-stu-id="846a3-183">Authentication using Windows security.</span></span>

<span data-ttu-id="846a3-184">자세한 내용은 <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> 및 <xref:System.ServiceModel.NamedPipeTransportSecurity>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="846a3-184">For more information, see <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode>, and <xref:System.ServiceModel.NamedPipeTransportSecurity>.</span></span>

### <a name="msmqintegrationbinding"></a><span data-ttu-id="846a3-185">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-185">MsmqIntegrationBinding</span></span>

<span data-ttu-id="846a3-186">코드에서 클래스를 사용 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 합니다. 구성에서를 사용 [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-186">In code, use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> class; in configuration, use the [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>

<span data-ttu-id="846a3-187">이 바인딩은 wcf (Microsoft Message Queuing)가 아닌 MSMQ (Microsoft Message Queuing) 끝점과 상호 작용 하는 WCF 클라이언트 및 서비스를 만드는 데 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-187">This binding is optimized for creating WCF clients and services that interoperate with non-WCF Microsoft Message Queuing (MSMQ) endpoints.</span></span>

<span data-ttu-id="846a3-188">기본적으로 이 바인딩은 전송 보안을 사용하고 다음과 같은 보안 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-188">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="846a3-189">보안을 사용할 수 없습니다(None).</span><span class="sxs-lookup"><span data-stu-id="846a3-189">Security can be disabled (None).</span></span>

- <span data-ttu-id="846a3-190">MSMQ 전송 보안입니다(Transport).</span><span class="sxs-lookup"><span data-stu-id="846a3-190">MSMQ transport security (Transport).</span></span>

<span data-ttu-id="846a3-191">자세한 내용은 <xref:System.ServiceModel.NetMsmqSecurity> 및 <xref:System.ServiceModel.NetMsmqSecurityMode>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-191">For more information, see <xref:System.ServiceModel.NetMsmqSecurity> and <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>

### <a name="netmsmqbinding"></a><span data-ttu-id="846a3-192">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-192">NetMsmqBinding</span></span>

<span data-ttu-id="846a3-193">코드에서 클래스를 사용 <xref:System.ServiceModel.NetMsmqBinding> 합니다. 구성에서를 사용 [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-193">In code, use the <xref:System.ServiceModel.NetMsmqBinding> class; in configuration, use the [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md).</span></span>

<span data-ttu-id="846a3-194">이 바인딩은 MSMQ 큐에 대기 중인 메시지를 지원 해야 하는 WCF 서비스를 만들 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-194">This binding is intended for use when creating WCF services that require MSMQ queued message support.</span></span>

<span data-ttu-id="846a3-195">기본적으로 이 바인딩은 전송 보안을 사용하고 다음과 같은 보안 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-195">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="846a3-196">보안을 사용할 수 없습니다(None).</span><span class="sxs-lookup"><span data-stu-id="846a3-196">Security can be disabled (None).</span></span>

- <span data-ttu-id="846a3-197">MSMQ 전송 보안입니다(Transport).</span><span class="sxs-lookup"><span data-stu-id="846a3-197">MSMQ transport security (Transport).</span></span>

- <span data-ttu-id="846a3-198">SOAP 기반 메시지 보안입니다(Message).</span><span class="sxs-lookup"><span data-stu-id="846a3-198">SOAP-based message security (Message).</span></span>

- <span data-ttu-id="846a3-199">동시 전송 및 메시지 보안입니다(Both).</span><span class="sxs-lookup"><span data-stu-id="846a3-199">Simultaneous Transport and Message security (Both).</span></span>

- <span data-ttu-id="846a3-200">지원되는 클라이언트 자격 증명 형식: None, Windows, UserName, Certificate, IssuedToken</span><span class="sxs-lookup"><span data-stu-id="846a3-200">Client Credential Types supported: None, Windows, UserName, Certificate, IssuedToken.</span></span>

<span data-ttu-id="846a3-201"><xref:System.ServiceModel.MessageCredentialType.Certificate> 자격 증명은 보안 모드를 <xref:System.ServiceModel.NetMsmqSecurityMode.Both> 또는 <xref:System.ServiceModel.NetMsmqSecurityMode.Message> 중 하나로 설정하는 경우에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-201">The <xref:System.ServiceModel.MessageCredentialType.Certificate> credential is supported only when the security mode is set to either <xref:System.ServiceModel.NetMsmqSecurityMode.Both> or <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.</span></span>

<span data-ttu-id="846a3-202">자세한 내용은 <xref:System.ServiceModel.MessageSecurityOverMsmq> 및 <xref:System.ServiceModel.MsmqTransportSecurity>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-202">For more information, see <xref:System.ServiceModel.MessageSecurityOverMsmq> and <xref:System.ServiceModel.MsmqTransportSecurity>.</span></span>

### <a name="wsfederationhttpbinding"></a><span data-ttu-id="846a3-203">WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="846a3-203">WSFederationHttpBinding</span></span>

<span data-ttu-id="846a3-204">코드에서 클래스를 사용 <xref:System.ServiceModel.WSFederationHttpBinding> 합니다. 구성에서를 사용 [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-204">In code, use the <xref:System.ServiceModel.WSFederationHttpBinding> class; in configuration, use the [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

<span data-ttu-id="846a3-205">기본적으로 이 바인딩은 WS-Security(메시지 계층 보안)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-205">By default, this binding uses WS-Security (message-layer security).</span></span>

<span data-ttu-id="846a3-206">자세한 내용은 [페더레이션](federation.md), 및을 참조 하세요 <xref:System.ServiceModel.WSFederationHttpSecurity> <xref:System.ServiceModel.WSFederationHttpSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="846a3-206">For more information, see [Federation](federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>, and <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="846a3-207">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="846a3-207">Custom Bindings</span></span>

<span data-ttu-id="846a3-208">시스템 제공 바인딩이 요구 사항을 충족하지 못하는 경우 사용자 지정 보안 바인딩 요소를 사용하여 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-208">If none of the system-provided bindings meets you requirements, you can create a custom binding with a custom security binding element.</span></span> <span data-ttu-id="846a3-209">자세한 내용은 [사용자 지정 바인딩을 사용 하는 보안 기능](security-capabilities-with-custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-209">For more information, see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md).</span></span>

## <a name="binding-choices"></a><span data-ttu-id="846a3-210">바인딩 선택</span><span class="sxs-lookup"><span data-stu-id="846a3-210">Binding Choices</span></span>

<span data-ttu-id="846a3-211">다음 표에서는 보안 모드 설정에서 제공하는 기능에 대해 요약하여 설명합니다. 즉, 보안 모드를 `Transport`, `Message` 또는 `TransportWithMessageCredential`로 설정한 경우 사용할 수 있는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-211">The following table summarizes the features offered in the security mode setting, that is, it lists the features available when the security mode is set to `Transport`, `Message`, or `TransportWithMessageCredential`.</span></span> <span data-ttu-id="846a3-212">이 표를 사용하면 애플리케이션에서 필요한 보안 기능을 찾는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-212">Use this table to help you find the security features your application requires.</span></span>

|<span data-ttu-id="846a3-213">설정</span><span class="sxs-lookup"><span data-stu-id="846a3-213">Setting</span></span>|<span data-ttu-id="846a3-214">기능</span><span class="sxs-lookup"><span data-stu-id="846a3-214">Features</span></span>|
|-------------|--------------|
|<span data-ttu-id="846a3-215">전송</span><span class="sxs-lookup"><span data-stu-id="846a3-215">Transport</span></span>|<span data-ttu-id="846a3-216">서버 인증</span><span class="sxs-lookup"><span data-stu-id="846a3-216">Server authentication</span></span><br /><br /> <span data-ttu-id="846a3-217">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="846a3-217">Client authentication</span></span><br /><br /> <span data-ttu-id="846a3-218">지점 간 보안</span><span class="sxs-lookup"><span data-stu-id="846a3-218">Point-to-point security</span></span><br /><br /> <span data-ttu-id="846a3-219">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="846a3-219">Interoperability</span></span><br /><br /> <span data-ttu-id="846a3-220">하드웨어 가속</span><span class="sxs-lookup"><span data-stu-id="846a3-220">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="846a3-221">높은 처리량</span><span class="sxs-lookup"><span data-stu-id="846a3-221">High throughput</span></span><br /><br /> <span data-ttu-id="846a3-222">보안 방화벽</span><span class="sxs-lookup"><span data-stu-id="846a3-222">Secure firewall</span></span><br /><br /> <span data-ttu-id="846a3-223">대기 시간이 긴 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="846a3-223">High-latency applications</span></span><br /><br /> <span data-ttu-id="846a3-224">여러 홉을 통해 다시 암호화</span><span class="sxs-lookup"><span data-stu-id="846a3-224">Re-encryption across multiple hops</span></span>|
|<span data-ttu-id="846a3-225">메시지</span><span class="sxs-lookup"><span data-stu-id="846a3-225">Message</span></span>|<span data-ttu-id="846a3-226">서버 인증</span><span class="sxs-lookup"><span data-stu-id="846a3-226">Server authentication</span></span><br /><br /> <span data-ttu-id="846a3-227">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="846a3-227">Client authentication</span></span><br /><br /> <span data-ttu-id="846a3-228">엔드투엔드 보안</span><span class="sxs-lookup"><span data-stu-id="846a3-228">End-to-end security</span></span><br /><br /> <span data-ttu-id="846a3-229">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="846a3-229">Interoperability</span></span><br /><br /> <span data-ttu-id="846a3-230">다양한 클레임</span><span class="sxs-lookup"><span data-stu-id="846a3-230">Rich claims</span></span><br /><br /> <span data-ttu-id="846a3-231">페더레이션</span><span class="sxs-lookup"><span data-stu-id="846a3-231">Federation</span></span><br /><br /> <span data-ttu-id="846a3-232">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="846a3-232">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="846a3-233">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="846a3-233">Custom tokens</span></span><br /><br /> <span data-ttu-id="846a3-234">공증/타임스탬프 서비스</span><span class="sxs-lookup"><span data-stu-id="846a3-234">Notary/timestamp service</span></span><br /><br /> <span data-ttu-id="846a3-235">대기 시간이 긴 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="846a3-235">High-latency applications</span></span><br /><br /> <span data-ttu-id="846a3-236">메시지 서명 지속성</span><span class="sxs-lookup"><span data-stu-id="846a3-236">Persistence of message signatures</span></span>|
|<span data-ttu-id="846a3-237">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="846a3-237">TransportWithMessageCredential</span></span>|<span data-ttu-id="846a3-238">서버 인증</span><span class="sxs-lookup"><span data-stu-id="846a3-238">Server authentication</span></span><br /><br /> <span data-ttu-id="846a3-239">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="846a3-239">Client authentication</span></span><br /><br /> <span data-ttu-id="846a3-240">지점 간 보안</span><span class="sxs-lookup"><span data-stu-id="846a3-240">Point-to-point security</span></span><br /><br /> <span data-ttu-id="846a3-241">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="846a3-241">Interoperability</span></span><br /><br /> <span data-ttu-id="846a3-242">하드웨어 가속</span><span class="sxs-lookup"><span data-stu-id="846a3-242">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="846a3-243">높은 처리량</span><span class="sxs-lookup"><span data-stu-id="846a3-243">High throughput</span></span><br /><br /> <span data-ttu-id="846a3-244">다양한 클라이언트 클레임</span><span class="sxs-lookup"><span data-stu-id="846a3-244">Rich client claims</span></span><br /><br /> <span data-ttu-id="846a3-245">페더레이션</span><span class="sxs-lookup"><span data-stu-id="846a3-245">Federation</span></span><br /><br /> <span data-ttu-id="846a3-246">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="846a3-246">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="846a3-247">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="846a3-247">Custom tokens</span></span><br /><br /> <span data-ttu-id="846a3-248">보안 방화벽</span><span class="sxs-lookup"><span data-stu-id="846a3-248">Secure firewall</span></span><br /><br /> <span data-ttu-id="846a3-249">대기 시간이 긴 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="846a3-249">High-latency applications</span></span><br /><br /> <span data-ttu-id="846a3-250">여러 홉을 통해 다시 암호화</span><span class="sxs-lookup"><span data-stu-id="846a3-250">Re-encryption across multiple hops</span></span>|

<span data-ttu-id="846a3-251">다음 표에서는 다양한 모드 설정을 지원하는 바인딩을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-251">The following table lists the bindings that support the various mode settings.</span></span> <span data-ttu-id="846a3-252">표에서 서비스 엔드포인트를 만드는 데 사용할 바인딩을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-252">Select a binding from the table to use to create your service endpoint.</span></span>

|<span data-ttu-id="846a3-253">바인딩</span><span class="sxs-lookup"><span data-stu-id="846a3-253">Binding</span></span>|<span data-ttu-id="846a3-254">Transport 모드 지원</span><span class="sxs-lookup"><span data-stu-id="846a3-254">Transport mode support</span></span>|<span data-ttu-id="846a3-255">Message 모드 지원</span><span class="sxs-lookup"><span data-stu-id="846a3-255">Message mode support</span></span>|<span data-ttu-id="846a3-256">TransportWithMessageCredential 지원</span><span class="sxs-lookup"><span data-stu-id="846a3-256">TransportWithMessageCredential support</span></span>|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|<span data-ttu-id="846a3-257">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-257">Yes</span></span>|<span data-ttu-id="846a3-258">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-258">Yes</span></span>|<span data-ttu-id="846a3-259">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-259">Yes</span></span>|
|`WSHttpBinding`|<span data-ttu-id="846a3-260">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-260">Yes</span></span>|<span data-ttu-id="846a3-261">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-261">Yes</span></span>|<span data-ttu-id="846a3-262">예</span><span class="sxs-lookup"><span data-stu-id="846a3-262">Yes</span></span>|
|`WSDualHttpBinding`|<span data-ttu-id="846a3-263">예</span><span class="sxs-lookup"><span data-stu-id="846a3-263">No</span></span>|<span data-ttu-id="846a3-264">예</span><span class="sxs-lookup"><span data-stu-id="846a3-264">Yes</span></span>|<span data-ttu-id="846a3-265">예</span><span class="sxs-lookup"><span data-stu-id="846a3-265">No</span></span>|
|`NetTcpBinding`|<span data-ttu-id="846a3-266">예</span><span class="sxs-lookup"><span data-stu-id="846a3-266">Yes</span></span>|<span data-ttu-id="846a3-267">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-267">Yes</span></span>|<span data-ttu-id="846a3-268">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-268">Yes</span></span>|
|`NetNamedPipeBinding`|<span data-ttu-id="846a3-269">예</span><span class="sxs-lookup"><span data-stu-id="846a3-269">Yes</span></span>|<span data-ttu-id="846a3-270">아니요</span><span class="sxs-lookup"><span data-stu-id="846a3-270">No</span></span>|<span data-ttu-id="846a3-271">예</span><span class="sxs-lookup"><span data-stu-id="846a3-271">No</span></span>|
|`NetMsmqBinding`|<span data-ttu-id="846a3-272">예</span><span class="sxs-lookup"><span data-stu-id="846a3-272">Yes</span></span>|<span data-ttu-id="846a3-273">예</span><span class="sxs-lookup"><span data-stu-id="846a3-273">Yes</span></span>|<span data-ttu-id="846a3-274">예</span><span class="sxs-lookup"><span data-stu-id="846a3-274">No</span></span>|
|`MsmqIntegrationBinding`|<span data-ttu-id="846a3-275">예</span><span class="sxs-lookup"><span data-stu-id="846a3-275">Yes</span></span>|<span data-ttu-id="846a3-276">아니요</span><span class="sxs-lookup"><span data-stu-id="846a3-276">No</span></span>|<span data-ttu-id="846a3-277">아니요</span><span class="sxs-lookup"><span data-stu-id="846a3-277">No</span></span>|
|`wsFederationHttpBinding`|<span data-ttu-id="846a3-278">예</span><span class="sxs-lookup"><span data-stu-id="846a3-278">No</span></span>|<span data-ttu-id="846a3-279">예</span><span class="sxs-lookup"><span data-stu-id="846a3-279">Yes</span></span>|<span data-ttu-id="846a3-280">Yes</span><span class="sxs-lookup"><span data-stu-id="846a3-280">Yes</span></span>|

## <a name="transport-credentials-in-bindings"></a><span data-ttu-id="846a3-281">바인딩의 전송 자격 증명</span><span class="sxs-lookup"><span data-stu-id="846a3-281">Transport Credentials in Bindings</span></span>

<span data-ttu-id="846a3-282">다음 표에서는 전송 보안 모드에서 `BasicHttpBinding` 또는 `WSHttpBinding` 사용 시 사용할 수 있는 클라이언트 자격 증명 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-282">The following table lists the client credential types available when using either `BasicHttpBinding` or `WSHttpBinding` in transport security mode.</span></span>

|<span data-ttu-id="846a3-283">Type</span><span class="sxs-lookup"><span data-stu-id="846a3-283">Type</span></span>|<span data-ttu-id="846a3-284">Description</span><span class="sxs-lookup"><span data-stu-id="846a3-284">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="846a3-285">None</span><span class="sxs-lookup"><span data-stu-id="846a3-285">None</span></span>|<span data-ttu-id="846a3-286">클라이언트가 자격 증명을 제공할 필요가 없음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-286">Specifies that the client does not need to present any credential.</span></span> <span data-ttu-id="846a3-287">익명 클라이언트로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-287">This translates to an anonymous client.</span></span>|
|<span data-ttu-id="846a3-288">Basic</span><span class="sxs-lookup"><span data-stu-id="846a3-288">Basic</span></span>|<span data-ttu-id="846a3-289">기본 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-289">Basic authentication.</span></span> <span data-ttu-id="846a3-290">자세한 내용은 RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증 (에서 사용 가능)을 참조 하세요 <https://go.microsoft.com/fwlink/?LinkId=84023> .</span><span class="sxs-lookup"><span data-stu-id="846a3-290">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="846a3-291">다이제스트</span><span class="sxs-lookup"><span data-stu-id="846a3-291">Digest</span></span>|<span data-ttu-id="846a3-292">다이제스트 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-292">Digest authentication.</span></span> <span data-ttu-id="846a3-293">자세한 내용은 RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증 (에서 사용 가능)을 참조 하세요 <https://go.microsoft.com/fwlink/?LinkId=84023> .</span><span class="sxs-lookup"><span data-stu-id="846a3-293">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="846a3-294">NTLM</span><span class="sxs-lookup"><span data-stu-id="846a3-294">NTLM</span></span>|<span data-ttu-id="846a3-295">NTLM(NT LAN Manager) 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-295">NT LAN Manager (NTLM) authentication.</span></span>|
|<span data-ttu-id="846a3-296">Windows</span><span class="sxs-lookup"><span data-stu-id="846a3-296">Windows</span></span>|<span data-ttu-id="846a3-297">Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-297">Windows authentication.</span></span>|
|<span data-ttu-id="846a3-298">인증서</span><span class="sxs-lookup"><span data-stu-id="846a3-298">Certificate</span></span>|<span data-ttu-id="846a3-299">인증서를 사용하여 수행되는 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-299">Authentication performed using a certificate.</span></span>|
|<span data-ttu-id="846a3-300">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="846a3-300">IssuedToken</span></span>|<span data-ttu-id="846a3-301">서비스에서 보안 토큰 서비스 또는 CardSpace가 발급 한 토큰을 사용 하 여 클라이언트를 인증 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-301">Allows the service to require that the client be authenticated using a token issued by a security token service or by CardSpace.</span></span> <span data-ttu-id="846a3-302">자세한 내용은 [페더레이션 및 발급 된 토큰](federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="846a3-302">For more information, see [Federation and Issued Tokens](federation-and-issued-tokens.md).</span></span>|

### <a name="message-client-credentials-in-bindings"></a><span data-ttu-id="846a3-303">바인딩의 메시지 클라이언트 자격 증명</span><span class="sxs-lookup"><span data-stu-id="846a3-303">Message Client Credentials in Bindings</span></span>

<span data-ttu-id="846a3-304">다음 표에서는 메시지 보안 모드에서 바인딩 사용 시 사용할 수 있는 클라이언트 자격 증명 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-304">The following table lists the client credential types available when using a binding in Message security mode.</span></span>

|<span data-ttu-id="846a3-305">Type</span><span class="sxs-lookup"><span data-stu-id="846a3-305">Type</span></span>|<span data-ttu-id="846a3-306">Description</span><span class="sxs-lookup"><span data-stu-id="846a3-306">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="846a3-307">None</span><span class="sxs-lookup"><span data-stu-id="846a3-307">None</span></span>|<span data-ttu-id="846a3-308">서비스와 익명 클라이언트가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-308">Allows the service to interact with anonymous clients.</span></span>|
|<span data-ttu-id="846a3-309">Windows</span><span class="sxs-lookup"><span data-stu-id="846a3-309">Windows</span></span>|<span data-ttu-id="846a3-310">Windows 자격 증명의 인증된 컨텍스트에서 SOAP 메시지 교환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-310">Allows SOAP message exchanges to be made under the authenticated context of a Windows credential.</span></span>|
|<span data-ttu-id="846a3-311">UserName</span><span class="sxs-lookup"><span data-stu-id="846a3-311">UserName</span></span>|<span data-ttu-id="846a3-312">서비스에서 사용자 이름 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-312">Allows the service to require that the client be authenticated using a user name credential.</span></span> <span data-ttu-id="846a3-313">보안 모드가로 설정 된 경우 WCF는 암호 `TransportWithMessageCredential` 다이제스트를 보내거나 암호를 사용 하 여 키를 파생 하 고 메시지 모드 보안에 이러한 키를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-313">Note that when the security mode is set to `TransportWithMessageCredential`, WCF does not support sending a password digest or deriving keys using password and using such keys for Message mode security.</span></span> <span data-ttu-id="846a3-314">따라서 WCF는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-314">As such, WCF enforces that the transport is secured when using user name credentials.</span></span>|
|<span data-ttu-id="846a3-315">인증서</span><span class="sxs-lookup"><span data-stu-id="846a3-315">Certificate</span></span>|<span data-ttu-id="846a3-316">서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-316">Allows the service to require that the client be authenticated using a certificate.</span></span>|
|<span data-ttu-id="846a3-317">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="846a3-317">IssuedToken</span></span>|<span data-ttu-id="846a3-318">서비스가 보안 토큰 서비스를 사용하여 사용자 지정 토큰을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="846a3-318">Allows the service to use a security token service to supply a custom token.</span></span>|

## <a name="see-also"></a><span data-ttu-id="846a3-319">참고 항목</span><span class="sxs-lookup"><span data-stu-id="846a3-319">See also</span></span>

- [<span data-ttu-id="846a3-320">보안 개요</span><span class="sxs-lookup"><span data-stu-id="846a3-320">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="846a3-321">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="846a3-321">Securing Services and Clients</span></span>](securing-services-and-clients.md)
- [<span data-ttu-id="846a3-322">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="846a3-322">Selecting a Credential Type</span></span>](selecting-a-credential-type.md)
- [<span data-ttu-id="846a3-323">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="846a3-323">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="846a3-324">보안 동작</span><span class="sxs-lookup"><span data-stu-id="846a3-324">Security Behaviors</span></span>](security-behaviors-in-wcf.md)
- <span data-ttu-id="846a3-325">[Windows Server AppFabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="846a3-325">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
