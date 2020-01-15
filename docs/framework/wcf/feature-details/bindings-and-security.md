---
title: 바인딩 및 보안
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: 63d3888df364d033b17972a5fd3ba3b851e00c42
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964433"
---
# <a name="bindings-and-security"></a><span data-ttu-id="a0576-102">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="a0576-102">Bindings and Security</span></span>

<span data-ttu-id="a0576-103">WCF (Windows Communication Foundation)에 포함 된 시스템 제공 바인딩은 WCF 응용 프로그램을 신속 하 게 프로그래밍할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-103">The system-provided bindings included with Windows Communication Foundation (WCF) offer a quick way to program WCF applications.</span></span> <span data-ttu-id="a0576-104">한 가지 예외를 통해 모든 바인딩의 기본 보안 스키마가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-104">With one exception, all the bindings have a default security scheme enabled.</span></span> <span data-ttu-id="a0576-105">이 항목은 보안 요구 사항에 적합한 바인딩을 선택하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-105">This topic helps you select the right binding for your security needs.</span></span>

<span data-ttu-id="a0576-106">WCF 보안에 대 한 개요는 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-106">For an overview of WCF security, see [Security Overview](../../../../docs/framework/wcf/feature-details/security-overview.md).</span></span> <span data-ttu-id="a0576-107">바인딩을 사용 하 여 WCF를 프로그래밍 하는 방법에 대 한 자세한 내용은 [Wcf 보안 프로그래밍](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-107">For more information about programming WCF using bindings, see [Programming WCF Security](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).</span></span>

<span data-ttu-id="a0576-108">바인딩을 이미 선택한 경우 [보안 동작](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)의 보안과 관련 된 런타임 동작에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-108">If you have already selected a binding, you can find out more about the run-time behaviors that are associated with security in [Security Behaviors](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).</span></span>

<span data-ttu-id="a0576-109">일부 보안 기능은 시스템 제공 바인딩을 사용하여 프로그래밍할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-109">Some security functions are not programmable using the system-provided bindings.</span></span> <span data-ttu-id="a0576-110">사용자 지정 바인딩을 사용 하는 더 많은 제어를 위해 [사용자 지정 바인딩을](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)사용 하는 보안 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-110">For more control using a custom binding, see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).</span></span>

## <a name="security-functions-of-bindings"></a><span data-ttu-id="a0576-111">바인딩의 보안 기능</span><span class="sxs-lookup"><span data-stu-id="a0576-111">Security Functions of Bindings</span></span>

<span data-ttu-id="a0576-112">WCF에는 대부분의 요구를 충족 하는 여러 시스템 제공 바인딩이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-112">WCF includes a number of system-provided bindings that meet most needs.</span></span> <span data-ttu-id="a0576-113">또한 특정 바인딩이 요구 사항을 충족하지 않는 경우, 사용자 지정 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-113">If a particular binding does not suffice, you can also create a custom binding.</span></span> <span data-ttu-id="a0576-114">시스템 제공 바인딩 목록은 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-114">For a list of system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="a0576-115">사용자 지정 바인딩에 대 한 자세한 내용은 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-115">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>

<span data-ttu-id="a0576-116">WCF의 모든 바인딩에는 API와 구성 파일에 사용 되는 XML 요소로 구성 된 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-116">Every binding in WCF has two forms: as an API and as an XML element used in a configuration file.</span></span> <span data-ttu-id="a0576-117">예를 들어 `WSHttpBinding` (API)는 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)에 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-117">For example, the `WSHttpBinding` (API) has a counterpart in the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="a0576-118">다음 단원에서는 각 바인딩에 대한 두 가지 양식을 나열하고 해당 보안 기능에 대해 요약하여 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-118">The following section lists both forms for each binding and summarizes the security features.</span></span>

### <a name="basichttp"></a><span data-ttu-id="a0576-119">BasicHttp</span><span class="sxs-lookup"><span data-stu-id="a0576-119">BasicHttp</span></span>

<span data-ttu-id="a0576-120">코드에서 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용 합니다. 구성에서 [\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-120">In code, use the <xref:System.ServiceModel.BasicHttpBinding> class; in configuration, use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>

<span data-ttu-id="a0576-121">이 바인딩은 다음을 포함하여 일정 범위의 기존 기술을 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-121">This binding is designed for use with a range of existing technologies, including the following:</span></span>

- <span data-ttu-id="a0576-122">ASP.NET 웹 서비스(ASMX), 버전 1</span><span class="sxs-lookup"><span data-stu-id="a0576-122">ASP.NET Web services (ASMX), version 1.</span></span>

- <span data-ttu-id="a0576-123">WSE(Web Service Enhancement) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="a0576-123">Web Service Enhancements (WSE) applications.</span></span>

- <span data-ttu-id="a0576-124">WS (웹 서비스 상호 운용성) 사양 (<https://go.microsoft.com/fwlink/?LinkId=38955>)에 정의 된 기본 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-124">Basic Profile as defined in the Web Services Interoperability (WS-I) specification (<https://go.microsoft.com/fwlink/?LinkId=38955>).</span></span>

- <span data-ttu-id="a0576-125">WS-I에 정의된 기본 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="a0576-125">Basic security profile as defined in WS-I.</span></span>

<span data-ttu-id="a0576-126">기본적으로 이 바인딩은 보안 처리되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-126">By default, this binding is not secure.</span></span> <span data-ttu-id="a0576-127">ASMX 서비스와 상호 운용되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-127">It is designed to interoperate with ASMX services.</span></span> <span data-ttu-id="a0576-128">보안을 사용하는 경우 바인딩은 기본 인증, 다이제스트 및 통합 Windows 보안과 같이 IIS(인터넷 정보 서비스) 보안 메커니즘과 원활한 상호 운용을 위해 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-128">When security is enabled, the binding is designed for seamless interoperation with Internet Information Services (IIS) security mechanisms, such as basic authentication, digest, and integrated Windows security.</span></span> <span data-ttu-id="a0576-129">자세한 내용은 [전송 보안 개요](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-129">For more information, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span> <span data-ttu-id="a0576-130">이 바인딩은 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-130">This binding supports the following:</span></span>

- <span data-ttu-id="a0576-131">HTTPS 전송 보안.</span><span class="sxs-lookup"><span data-stu-id="a0576-131">HTTPS transport security.</span></span>

- <span data-ttu-id="a0576-132">HTTP 기본 인증.</span><span class="sxs-lookup"><span data-stu-id="a0576-132">HTTP basic authentication.</span></span>

- <span data-ttu-id="a0576-133">WS-Security.</span><span class="sxs-lookup"><span data-stu-id="a0576-133">WS-Security.</span></span>

<span data-ttu-id="a0576-134">자세한 내용은 <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> 및 <xref:System.ServiceModel.BasicHttpSecurityMode> 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0576-134">For more information, see <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>, and <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>

### <a name="wshttpbinding"></a><span data-ttu-id="a0576-135">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-135">WSHttpBinding</span></span>

<span data-ttu-id="a0576-136">코드에서 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용 합니다. 구성에서 [wsHttpBinding >\<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-136">In code, use the <xref:System.ServiceModel.WSHttpBinding> class; in configuration, use the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="a0576-137">기본적으로 이 바인딩은 WS-Security 사양을 구현하고 WS-\* 사양을 구현하는 서비스와의 상호 운용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-137">By default, this binding implements the WS-Security specification and provides interoperability with services that implement the WS-\* specifications.</span></span> <span data-ttu-id="a0576-138">다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-138">It supports the following:</span></span>

- <span data-ttu-id="a0576-139">HTTPS 전송 보안.</span><span class="sxs-lookup"><span data-stu-id="a0576-139">HTTPS transport security.</span></span>

- <span data-ttu-id="a0576-140">WS-Security.</span><span class="sxs-lookup"><span data-stu-id="a0576-140">WS-Security.</span></span>

- <span data-ttu-id="a0576-141">호출자를 인증하기 위한 SOAP 메시지 자격 증명 보안을 사용하여 HTTPS 전송 보호.</span><span class="sxs-lookup"><span data-stu-id="a0576-141">HTTPS transport protection with SOAP message credential security for authenticating the caller.</span></span>

<span data-ttu-id="a0576-142">자세한 내용은 <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>및 <xref:System.ServiceModel.HttpProxyCredentialType>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-142">For more information, see <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>, and <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>

### <a name="wsdualhttpbinding"></a><span data-ttu-id="a0576-143">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-143">WSDualHttpBinding</span></span>

<span data-ttu-id="a0576-144">코드에서 <xref:System.ServiceModel.WSDualHttpBinding> 클래스를 사용 합니다. 구성에서 [\<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-144">In code, use the <xref:System.ServiceModel.WSDualHttpBinding> class; in configuration, use the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>

<span data-ttu-id="a0576-145">이 바인딩은 이중 서비스 애플리케이션을 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-145">This binding is designed to enable duplex service applications.</span></span> <span data-ttu-id="a0576-146">이 바인딩은 메시지 기반 전송 보안을 위한 WS-Security 사양을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-146">This binding implements the WS-Security specification for message-based transfer security.</span></span> <span data-ttu-id="a0576-147">전송 보안을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-147">Transport security is not available.</span></span> <span data-ttu-id="a0576-148">기본적으로 다음 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-148">By default, it provides the following features:</span></span>

- <span data-ttu-id="a0576-149">안정성을 위해 WS-Reliable Messaging을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-149">Implements WS-Reliable Messaging for reliability.</span></span>

- <span data-ttu-id="a0576-150">전송 보안 및 인증을 위해 WS-Security를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-150">Implements WS-Security for transfer security and authentication.</span></span>

- <span data-ttu-id="a0576-151">메시지 배달을 위해 HTTP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-151">Uses HTTP for message delivery.</span></span>

- <span data-ttu-id="a0576-152">텍스트/XML 메시지 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-152">Uses text/XML message encoding.</span></span>

 <span data-ttu-id="a0576-153">WS-Security(메시지 계층 보안)를 사용하면 바인딩을 통해 다음 매개 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-153">Using WS-Security (message-layer security), the binding allows you to configure the following parameters:</span></span>

- <span data-ttu-id="a0576-154">암호화 알고리즘을 결정하기 위한 보안 알고리즘 모음.</span><span class="sxs-lookup"><span data-stu-id="a0576-154">The security algorithm suite to determine the cryptographic algorithm.</span></span>

- <span data-ttu-id="a0576-155">다음에 대한 바인딩 옵션.</span><span class="sxs-lookup"><span data-stu-id="a0576-155">Binding options for the following:</span></span>

  - <span data-ttu-id="a0576-156">클라이언트에서 서비스 자격 증명 사용 가능한 out-of-band를 제공하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a0576-156">Providing service credentials available out-of-band at the client.</span></span>

  - <span data-ttu-id="a0576-157">채널 설정의 일부로 서비스에서 협상된 서비스 자격 증명을 제공하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a0576-157">Providing service credentials negotiated from the service as part of channel setup.</span></span>

<span data-ttu-id="a0576-158">자세한 내용은 <xref:System.ServiceModel.WSDualHttpSecurity> 및 <xref:System.ServiceModel.WSDualHttpSecurityMode>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-158">For more information, see <xref:System.ServiceModel.WSDualHttpSecurity> and <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>

### <a name="nettcpbinding"></a><span data-ttu-id="a0576-159">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-159">NetTcpBinding</span></span>

<span data-ttu-id="a0576-160">코드에서 <xref:System.ServiceModel.NetTcpBinding> 클래스를 사용 합니다. 구성에서 [\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-160">In code, use the <xref:System.ServiceModel.NetTcpBinding> class; in configuration, use the [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>

<span data-ttu-id="a0576-161">이 바인딩은 시스템 간 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-161">This binding is optimized for cross-machine communication.</span></span> <span data-ttu-id="a0576-162">기본적으로 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-162">By default, it has the following characteristics:</span></span>

- <span data-ttu-id="a0576-163">전송 계층 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-163">Implements transport-layer security.</span></span>

- <span data-ttu-id="a0576-164">전송 보안 및 인증을 위해 Windows 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-164">Leverages Windows security for transfer security and authentication.</span></span>

- <span data-ttu-id="a0576-165">전송을 위해 TCP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-165">Uses TCP for transport.</span></span>

- <span data-ttu-id="a0576-166">이진 메시지 인코딩을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-166">Implements binary message encoding.</span></span>

- <span data-ttu-id="a0576-167">WS-Reliable Messaging을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-167">Implements WS-Reliable Messaging.</span></span>

<span data-ttu-id="a0576-168">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-168">Options include the following:</span></span>

- <span data-ttu-id="a0576-169">메시지 계층 보안(WS-Security 사용).</span><span class="sxs-lookup"><span data-stu-id="a0576-169">Message-layer security (using WS-Security).</span></span>

- <span data-ttu-id="a0576-170">메시지 자격 증명을 통한 전송 보안—TCP를 통한 TLS(전송 계층 보안)에 의해 제공되는 기밀성과 무결성 및 WS-Security에 의해 제공되는 권한에 대한 자격 증명.</span><span class="sxs-lookup"><span data-stu-id="a0576-170">Transport security with message credential—confidentiality and integrity provided by Transport Layer Security (TLS) over TCP, and credentials for authorization provided by WS-Security.</span></span>

<span data-ttu-id="a0576-171">자세한 내용은 <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>및 <xref:System.ServiceModel.MessageCredentialType>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-171">For more information, see <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>, and <xref:System.ServiceModel.MessageCredentialType>.</span></span>

### <a name="netnamedpipebinding"></a><span data-ttu-id="a0576-172">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-172">NetNamedPipeBinding</span></span>

<span data-ttu-id="a0576-173">코드에서 <xref:System.ServiceModel.NetNamedPipeBinding> 클래스를 사용 합니다. 구성에서 [\<netNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-173">In code, use the <xref:System.ServiceModel.NetNamedPipeBinding> class; in configuration, use the [\<netNamedPipeBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>

<span data-ttu-id="a0576-174">이 바인딩은 일반적으로 동일한 시스템에서의 프로세스 간 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-174">This binding is optimized for cross-process communication (usually on the same machine).</span></span> <span data-ttu-id="a0576-175">기본적으로 이 바인딩에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-175">By default, this binding has the following characteristics:</span></span>

- <span data-ttu-id="a0576-176">메시지 전송 및 인증을 위해 전송 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-176">Uses transport security for message transfer and authentication.</span></span>

- <span data-ttu-id="a0576-177">메시지 배달을 위해 명명된 파이프를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-177">Uses named pipes for message delivery.</span></span>

- <span data-ttu-id="a0576-178">이진 메시지 인코딩을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-178">Implements binary message encoding.</span></span>

- <span data-ttu-id="a0576-179">암호화 및 메시지 서명.</span><span class="sxs-lookup"><span data-stu-id="a0576-179">Encryption and message signing.</span></span>

<span data-ttu-id="a0576-180">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-180">Options include the following:</span></span>

- <span data-ttu-id="a0576-181">Windows 보안을 사용하여 인증.</span><span class="sxs-lookup"><span data-stu-id="a0576-181">Authentication using Windows security.</span></span>

<span data-ttu-id="a0576-182">자세한 내용은 <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> 및 <xref:System.ServiceModel.NamedPipeTransportSecurity>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0576-182">For more information, see <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode>, and <xref:System.ServiceModel.NamedPipeTransportSecurity>.</span></span>

### <a name="msmqintegrationbinding"></a><span data-ttu-id="a0576-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-183">MsmqIntegrationBinding</span></span>

<span data-ttu-id="a0576-184">코드에서 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 클래스를 사용 합니다. 구성에서 [\<msmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-184">In code, use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> class; in configuration, use the [\<msmqIntegrationBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>

<span data-ttu-id="a0576-185">이 바인딩은 wcf (Microsoft Message Queuing)가 아닌 MSMQ (Microsoft Message Queuing) 끝점과 상호 작용 하는 WCF 클라이언트 및 서비스를 만드는 데 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-185">This binding is optimized for creating WCF clients and services that interoperate with non-WCF Microsoft Message Queuing (MSMQ) endpoints.</span></span>

<span data-ttu-id="a0576-186">기본적으로 이 바인딩은 전송 보안을 사용하고 다음과 같은 보안 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-186">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="a0576-187">보안을 사용할 수 없습니다(None).</span><span class="sxs-lookup"><span data-stu-id="a0576-187">Security can be disabled (None).</span></span>

- <span data-ttu-id="a0576-188">MSMQ 전송 보안입니다(Transport).</span><span class="sxs-lookup"><span data-stu-id="a0576-188">MSMQ transport security (Transport).</span></span>

<span data-ttu-id="a0576-189">자세한 내용은 <xref:System.ServiceModel.NetMsmqSecurity> 및 <xref:System.ServiceModel.NetMsmqSecurityMode>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-189">For more information, see <xref:System.ServiceModel.NetMsmqSecurity> and <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>

### <a name="netmsmqbinding"></a><span data-ttu-id="a0576-190">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-190">NetMsmqBinding</span></span>

<span data-ttu-id="a0576-191">코드에서 <xref:System.ServiceModel.NetMsmqBinding> 클래스를 사용 합니다. 구성에서 [\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-191">In code, use the <xref:System.ServiceModel.NetMsmqBinding> class; in configuration, use the [\<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).</span></span>

<span data-ttu-id="a0576-192">이 바인딩은 MSMQ 큐에 대기 중인 메시지를 지원 해야 하는 WCF 서비스를 만들 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-192">This binding is intended for use when creating WCF services that require MSMQ queued message support.</span></span>

<span data-ttu-id="a0576-193">기본적으로 이 바인딩은 전송 보안을 사용하고 다음과 같은 보안 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-193">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="a0576-194">보안을 사용할 수 없습니다(None).</span><span class="sxs-lookup"><span data-stu-id="a0576-194">Security can be disabled (None).</span></span>

- <span data-ttu-id="a0576-195">MSMQ 전송 보안입니다(Transport).</span><span class="sxs-lookup"><span data-stu-id="a0576-195">MSMQ transport security (Transport).</span></span>

- <span data-ttu-id="a0576-196">SOAP 기반 메시지 보안입니다(Message).</span><span class="sxs-lookup"><span data-stu-id="a0576-196">SOAP-based message security (Message).</span></span>

- <span data-ttu-id="a0576-197">동시 전송 및 메시지 보안입니다(Both).</span><span class="sxs-lookup"><span data-stu-id="a0576-197">Simultaneous Transport and Message security (Both).</span></span>

- <span data-ttu-id="a0576-198">지원되는 클라이언트 자격 증명 형식: None, Windows, UserName, Certificate, IssuedToken</span><span class="sxs-lookup"><span data-stu-id="a0576-198">Client Credential Types supported: None, Windows, UserName, Certificate, IssuedToken.</span></span>

<span data-ttu-id="a0576-199"><xref:System.ServiceModel.MessageCredentialType.Certificate> 자격 증명은 보안 모드를 <xref:System.ServiceModel.NetMsmqSecurityMode.Both> 또는 <xref:System.ServiceModel.NetMsmqSecurityMode.Message> 중 하나로 설정하는 경우에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-199">The <xref:System.ServiceModel.MessageCredentialType.Certificate> credential is supported only when the security mode is set to either <xref:System.ServiceModel.NetMsmqSecurityMode.Both> or <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.</span></span>

<span data-ttu-id="a0576-200">자세한 내용은 <xref:System.ServiceModel.MessageSecurityOverMsmq> 및 <xref:System.ServiceModel.MsmqTransportSecurity>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-200">For more information, see <xref:System.ServiceModel.MessageSecurityOverMsmq> and <xref:System.ServiceModel.MsmqTransportSecurity>.</span></span>

### <a name="wsfederationhttpbinding"></a><span data-ttu-id="a0576-201">WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a0576-201">WSFederationHttpBinding</span></span>

<span data-ttu-id="a0576-202">코드에서 <xref:System.ServiceModel.WSFederationHttpBinding> 클래스를 사용 합니다. 구성에서 [\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-202">In code, use the <xref:System.ServiceModel.WSFederationHttpBinding> class; in configuration, use the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

<span data-ttu-id="a0576-203">기본적으로 이 바인딩은 WS-Security(메시지 계층 보안)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-203">By default, this binding uses WS-Security (message-layer security).</span></span>

<span data-ttu-id="a0576-204">자세한 내용은 [페더레이션](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>및 <xref:System.ServiceModel.WSFederationHttpSecurityMode>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-204">For more information, see [Federation](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>, and <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="a0576-205">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="a0576-205">Custom Bindings</span></span>

<span data-ttu-id="a0576-206">시스템 제공 바인딩이 요구 사항을 충족하지 못하는 경우 사용자 지정 보안 바인딩 요소를 사용하여 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-206">If none of the system-provided bindings meets you requirements, you can create a custom binding with a custom security binding element.</span></span> <span data-ttu-id="a0576-207">자세한 내용은 [사용자 지정 바인딩을 사용 하는 보안 기능](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-207">For more information, see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).</span></span>

## <a name="binding-choices"></a><span data-ttu-id="a0576-208">바인딩 선택</span><span class="sxs-lookup"><span data-stu-id="a0576-208">Binding Choices</span></span>

<span data-ttu-id="a0576-209">다음 표에서는 보안 모드 설정에서 제공하는 기능에 대해 요약하여 설명합니다. 즉, 보안 모드를 `Transport`, `Message` 또는 `TransportWithMessageCredential`로 설정한 경우 사용할 수 있는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-209">The following table summarizes the features offered in the security mode setting, that is, it lists the features available when the security mode is set to `Transport`, `Message`, or `TransportWithMessageCredential`.</span></span> <span data-ttu-id="a0576-210">이 표를 사용하면 애플리케이션에서 필요한 보안 기능을 찾는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-210">Use this table to help you find the security features your application requires.</span></span>

|<span data-ttu-id="a0576-211">설정</span><span class="sxs-lookup"><span data-stu-id="a0576-211">Setting</span></span>|<span data-ttu-id="a0576-212">기능</span><span class="sxs-lookup"><span data-stu-id="a0576-212">Features</span></span>|
|-------------|--------------|
|<span data-ttu-id="a0576-213">Transport</span><span class="sxs-lookup"><span data-stu-id="a0576-213">Transport</span></span>|<span data-ttu-id="a0576-214">서버 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-214">Server authentication</span></span><br /><br /> <span data-ttu-id="a0576-215">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-215">Client authentication</span></span><br /><br /> <span data-ttu-id="a0576-216">지점 간 보안</span><span class="sxs-lookup"><span data-stu-id="a0576-216">Point-to-point security</span></span><br /><br /> <span data-ttu-id="a0576-217">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="a0576-217">Interoperability</span></span><br /><br /> <span data-ttu-id="a0576-218">하드웨어 가속</span><span class="sxs-lookup"><span data-stu-id="a0576-218">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="a0576-219">높은 처리량</span><span class="sxs-lookup"><span data-stu-id="a0576-219">High throughput</span></span><br /><br /> <span data-ttu-id="a0576-220">보안 방화벽</span><span class="sxs-lookup"><span data-stu-id="a0576-220">Secure firewall</span></span><br /><br /> <span data-ttu-id="a0576-221">대기 시간이 긴 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="a0576-221">High-latency applications</span></span><br /><br /> <span data-ttu-id="a0576-222">여러 홉을 통해 다시 암호화</span><span class="sxs-lookup"><span data-stu-id="a0576-222">Re-encryption across multiple hops</span></span>|
|<span data-ttu-id="a0576-223">메시지</span><span class="sxs-lookup"><span data-stu-id="a0576-223">Message</span></span>|<span data-ttu-id="a0576-224">서버 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-224">Server authentication</span></span><br /><br /> <span data-ttu-id="a0576-225">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-225">Client authentication</span></span><br /><br /> <span data-ttu-id="a0576-226">엔드투엔드 보안</span><span class="sxs-lookup"><span data-stu-id="a0576-226">End-to-end security</span></span><br /><br /> <span data-ttu-id="a0576-227">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="a0576-227">Interoperability</span></span><br /><br /> <span data-ttu-id="a0576-228">다양한 클레임</span><span class="sxs-lookup"><span data-stu-id="a0576-228">Rich claims</span></span><br /><br /> <span data-ttu-id="a0576-229">페더레이션</span><span class="sxs-lookup"><span data-stu-id="a0576-229">Federation</span></span><br /><br /> <span data-ttu-id="a0576-230">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-230">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="a0576-231">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="a0576-231">Custom tokens</span></span><br /><br /> <span data-ttu-id="a0576-232">공증/타임스탬프 서비스</span><span class="sxs-lookup"><span data-stu-id="a0576-232">Notary/timestamp service</span></span><br /><br /> <span data-ttu-id="a0576-233">대기 시간이 긴 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="a0576-233">High-latency applications</span></span><br /><br /> <span data-ttu-id="a0576-234">메시지 서명 지속성</span><span class="sxs-lookup"><span data-stu-id="a0576-234">Persistence of message signatures</span></span>|
|<span data-ttu-id="a0576-235">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a0576-235">TransportWithMessageCredential</span></span>|<span data-ttu-id="a0576-236">서버 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-236">Server authentication</span></span><br /><br /> <span data-ttu-id="a0576-237">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-237">Client authentication</span></span><br /><br /> <span data-ttu-id="a0576-238">지점 간 보안</span><span class="sxs-lookup"><span data-stu-id="a0576-238">Point-to-point security</span></span><br /><br /> <span data-ttu-id="a0576-239">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="a0576-239">Interoperability</span></span><br /><br /> <span data-ttu-id="a0576-240">하드웨어 가속</span><span class="sxs-lookup"><span data-stu-id="a0576-240">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="a0576-241">높은 처리량</span><span class="sxs-lookup"><span data-stu-id="a0576-241">High throughput</span></span><br /><br /> <span data-ttu-id="a0576-242">다양한 클라이언트 클레임</span><span class="sxs-lookup"><span data-stu-id="a0576-242">Rich client claims</span></span><br /><br /> <span data-ttu-id="a0576-243">페더레이션</span><span class="sxs-lookup"><span data-stu-id="a0576-243">Federation</span></span><br /><br /> <span data-ttu-id="a0576-244">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-244">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="a0576-245">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="a0576-245">Custom tokens</span></span><br /><br /> <span data-ttu-id="a0576-246">보안 방화벽</span><span class="sxs-lookup"><span data-stu-id="a0576-246">Secure firewall</span></span><br /><br /> <span data-ttu-id="a0576-247">대기 시간이 긴 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="a0576-247">High-latency applications</span></span><br /><br /> <span data-ttu-id="a0576-248">여러 홉을 통해 다시 암호화</span><span class="sxs-lookup"><span data-stu-id="a0576-248">Re-encryption across multiple hops</span></span>|

<span data-ttu-id="a0576-249">다음 표에서는 다양한 모드 설정을 지원하는 바인딩을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-249">The following table lists the bindings that support the various mode settings.</span></span> <span data-ttu-id="a0576-250">표에서 서비스 엔드포인트를 만드는 데 사용할 바인딩을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-250">Select a binding from the table to use to create your service endpoint.</span></span>

|<span data-ttu-id="a0576-251">바인딩</span><span class="sxs-lookup"><span data-stu-id="a0576-251">Binding</span></span>|<span data-ttu-id="a0576-252">Transport 모드 지원</span><span class="sxs-lookup"><span data-stu-id="a0576-252">Transport mode support</span></span>|<span data-ttu-id="a0576-253">Message 모드 지원</span><span class="sxs-lookup"><span data-stu-id="a0576-253">Message mode support</span></span>|<span data-ttu-id="a0576-254">TransportWithMessageCredential 지원</span><span class="sxs-lookup"><span data-stu-id="a0576-254">TransportWithMessageCredential support</span></span>|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|<span data-ttu-id="a0576-255">예</span><span class="sxs-lookup"><span data-stu-id="a0576-255">Yes</span></span>|<span data-ttu-id="a0576-256">예</span><span class="sxs-lookup"><span data-stu-id="a0576-256">Yes</span></span>|<span data-ttu-id="a0576-257">예</span><span class="sxs-lookup"><span data-stu-id="a0576-257">Yes</span></span>|
|`WSHttpBinding`|<span data-ttu-id="a0576-258">예</span><span class="sxs-lookup"><span data-stu-id="a0576-258">Yes</span></span>|<span data-ttu-id="a0576-259">예</span><span class="sxs-lookup"><span data-stu-id="a0576-259">Yes</span></span>|<span data-ttu-id="a0576-260">예</span><span class="sxs-lookup"><span data-stu-id="a0576-260">Yes</span></span>|
|`WSDualHttpBinding`|<span data-ttu-id="a0576-261">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-261">No</span></span>|<span data-ttu-id="a0576-262">예</span><span class="sxs-lookup"><span data-stu-id="a0576-262">Yes</span></span>|<span data-ttu-id="a0576-263">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-263">No</span></span>|
|`NetTcpBinding`|<span data-ttu-id="a0576-264">예</span><span class="sxs-lookup"><span data-stu-id="a0576-264">Yes</span></span>|<span data-ttu-id="a0576-265">예</span><span class="sxs-lookup"><span data-stu-id="a0576-265">Yes</span></span>|<span data-ttu-id="a0576-266">예</span><span class="sxs-lookup"><span data-stu-id="a0576-266">Yes</span></span>|
|`NetNamedPipeBinding`|<span data-ttu-id="a0576-267">예</span><span class="sxs-lookup"><span data-stu-id="a0576-267">Yes</span></span>|<span data-ttu-id="a0576-268">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-268">No</span></span>|<span data-ttu-id="a0576-269">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-269">No</span></span>|
|`NetMsmqBinding`|<span data-ttu-id="a0576-270">예</span><span class="sxs-lookup"><span data-stu-id="a0576-270">Yes</span></span>|<span data-ttu-id="a0576-271">예</span><span class="sxs-lookup"><span data-stu-id="a0576-271">Yes</span></span>|<span data-ttu-id="a0576-272">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-272">No</span></span>|
|`MsmqIntegrationBinding`|<span data-ttu-id="a0576-273">예</span><span class="sxs-lookup"><span data-stu-id="a0576-273">Yes</span></span>|<span data-ttu-id="a0576-274">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-274">No</span></span>|<span data-ttu-id="a0576-275">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-275">No</span></span>|
|`wsFederationHttpBinding`|<span data-ttu-id="a0576-276">아니요</span><span class="sxs-lookup"><span data-stu-id="a0576-276">No</span></span>|<span data-ttu-id="a0576-277">예</span><span class="sxs-lookup"><span data-stu-id="a0576-277">Yes</span></span>|<span data-ttu-id="a0576-278">예</span><span class="sxs-lookup"><span data-stu-id="a0576-278">Yes</span></span>|

## <a name="transport-credentials-in-bindings"></a><span data-ttu-id="a0576-279">바인딩의 전송 자격 증명</span><span class="sxs-lookup"><span data-stu-id="a0576-279">Transport Credentials in Bindings</span></span>

<span data-ttu-id="a0576-280">다음 표에서는 전송 보안 모드에서 `BasicHttpBinding` 또는 `WSHttpBinding` 사용 시 사용할 수 있는 클라이언트 자격 증명 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-280">The following table lists the client credential types available when using either `BasicHttpBinding` or `WSHttpBinding` in transport security mode.</span></span>

|<span data-ttu-id="a0576-281">형식</span><span class="sxs-lookup"><span data-stu-id="a0576-281">Type</span></span>|<span data-ttu-id="a0576-282">설명</span><span class="sxs-lookup"><span data-stu-id="a0576-282">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="a0576-283">None</span><span class="sxs-lookup"><span data-stu-id="a0576-283">None</span></span>|<span data-ttu-id="a0576-284">클라이언트가 자격 증명을 제공할 필요가 없음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-284">Specifies that the client does not need to present any credential.</span></span> <span data-ttu-id="a0576-285">익명 클라이언트로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-285">This translates to an anonymous client.</span></span>|
|<span data-ttu-id="a0576-286">Basic</span><span class="sxs-lookup"><span data-stu-id="a0576-286">Basic</span></span>|<span data-ttu-id="a0576-287">기본 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-287">Basic authentication.</span></span> <span data-ttu-id="a0576-288">자세한 내용은 RFC 2617 – HTTP Authentication: <https://go.microsoft.com/fwlink/?LinkId=84023>에서 사용할 수 있는 기본 및 다이제스트 인증을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-288">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="a0576-289">Digest</span><span class="sxs-lookup"><span data-stu-id="a0576-289">Digest</span></span>|<span data-ttu-id="a0576-290">다이제스트 인증</span><span class="sxs-lookup"><span data-stu-id="a0576-290">Digest authentication.</span></span> <span data-ttu-id="a0576-291">자세한 내용은 RFC 2617 – HTTP Authentication: <https://go.microsoft.com/fwlink/?LinkId=84023>에서 사용할 수 있는 기본 및 다이제스트 인증을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-291">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="a0576-292">NTLM</span><span class="sxs-lookup"><span data-stu-id="a0576-292">NTLM</span></span>|<span data-ttu-id="a0576-293">NTLM(NT LAN Manager) 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-293">NT LAN Manager (NTLM) authentication.</span></span>|
|<span data-ttu-id="a0576-294">Windows</span><span class="sxs-lookup"><span data-stu-id="a0576-294">Windows</span></span>|<span data-ttu-id="a0576-295">Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-295">Windows authentication.</span></span>|
|<span data-ttu-id="a0576-296">인증서</span><span class="sxs-lookup"><span data-stu-id="a0576-296">Certificate</span></span>|<span data-ttu-id="a0576-297">인증서를 사용하여 수행되는 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-297">Authentication performed using a certificate.</span></span>|
|<span data-ttu-id="a0576-298">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="a0576-298">IssuedToken</span></span>|<span data-ttu-id="a0576-299">서비스에서 보안 토큰 서비스 또는 CardSpace가 발급 한 토큰을 사용 하 여 클라이언트를 인증 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-299">Allows the service to require that the client be authenticated using a token issued by a security token service or by CardSpace.</span></span> <span data-ttu-id="a0576-300">자세한 내용은 [페더레이션 및 발급 된 토큰](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0576-300">For more information, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>|

### <a name="message-client-credentials-in-bindings"></a><span data-ttu-id="a0576-301">바인딩의 메시지 클라이언트 자격 증명</span><span class="sxs-lookup"><span data-stu-id="a0576-301">Message Client Credentials in Bindings</span></span>

<span data-ttu-id="a0576-302">다음 표에서는 메시지 보안 모드에서 바인딩 사용 시 사용할 수 있는 클라이언트 자격 증명 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-302">The following table lists the client credential types available when using a binding in Message security mode.</span></span>

|<span data-ttu-id="a0576-303">형식</span><span class="sxs-lookup"><span data-stu-id="a0576-303">Type</span></span>|<span data-ttu-id="a0576-304">설명</span><span class="sxs-lookup"><span data-stu-id="a0576-304">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="a0576-305">None</span><span class="sxs-lookup"><span data-stu-id="a0576-305">None</span></span>|<span data-ttu-id="a0576-306">서비스와 익명 클라이언트가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-306">Allows the service to interact with anonymous clients.</span></span>|
|<span data-ttu-id="a0576-307">Windows</span><span class="sxs-lookup"><span data-stu-id="a0576-307">Windows</span></span>|<span data-ttu-id="a0576-308">Windows 자격 증명의 인증된 컨텍스트에서 SOAP 메시지 교환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-308">Allows SOAP message exchanges to be made under the authenticated context of a Windows credential.</span></span>|
|<span data-ttu-id="a0576-309">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="a0576-309">UserName</span></span>|<span data-ttu-id="a0576-310">서비스에서 사용자 이름 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-310">Allows the service to require that the client be authenticated using a user name credential.</span></span> <span data-ttu-id="a0576-311">보안 모드가 `TransportWithMessageCredential`로 설정 된 경우 WCF는 암호 다이제스트를 보내거나 암호를 사용 하 여 키를 파생 하거나 메시지 모드 보안에 이러한 키를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-311">Note that when the security mode is set to `TransportWithMessageCredential`, WCF does not support sending a password digest or deriving keys using password and using such keys for Message mode security.</span></span> <span data-ttu-id="a0576-312">따라서 WCF는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-312">As such, WCF enforces that the transport is secured when using user name credentials.</span></span>|
|<span data-ttu-id="a0576-313">인증서</span><span class="sxs-lookup"><span data-stu-id="a0576-313">Certificate</span></span>|<span data-ttu-id="a0576-314">서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-314">Allows the service to require that the client be authenticated using a certificate.</span></span>|
|<span data-ttu-id="a0576-315">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="a0576-315">IssuedToken</span></span>|<span data-ttu-id="a0576-316">서비스가 보안 토큰 서비스를 사용하여 사용자 지정 토큰을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0576-316">Allows the service to use a security token service to supply a custom token.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a0576-317">참조</span><span class="sxs-lookup"><span data-stu-id="a0576-317">See also</span></span>

- [<span data-ttu-id="a0576-318">보안 개요</span><span class="sxs-lookup"><span data-stu-id="a0576-318">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="a0576-319">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="a0576-319">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a0576-320">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="a0576-320">Selecting a Credential Type</span></span>](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a0576-321">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="a0576-321">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a0576-322">보안 동작</span><span class="sxs-lookup"><span data-stu-id="a0576-322">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- <span data-ttu-id="a0576-323">[Windows Server Fabric 용 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a0576-323">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
