---
title: WCF 문제 해결 퀵 스타트
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: d1cae7ad2ac0fdf963d11911484b1bd534cbc129
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094737"
---
# <a name="wcf-troubleshooting-quickstart"></a><span data-ttu-id="00683-102">WCF 문제 해결 퀵 스타트</span><span class="sxs-lookup"><span data-stu-id="00683-102">WCF Troubleshooting Quickstart</span></span>
<span data-ttu-id="00683-103">이 항목에서는 WCF 클라이언트 및 서비스를 개발하는 동안 발생하는 몇 가지 알려진 문제점을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-103">This topic lists a number of known issues customers have run into while developing WCF clients and services.</span></span> <span data-ttu-id="00683-104">발생하는 문제가 이 목록에 없는 경우 서비스에 대한 추적을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-104">If the issue you are running into is not in this list, we recommend you configure tracing for your service.</span></span> <span data-ttu-id="00683-105">추적을 구성하면 추적 파일 뷰어로 보고 서비스 내에서 발생하는 예외에 대한 자세한 정보를 얻을 수 있는 추적 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00683-105">This will generate a trace file that you can view with the trace file viewer and get detailed information about exceptions that may be occurring within the service.</span></span> <span data-ttu-id="00683-106">추적을 구성하는 방법에 대한 자세한 내용은 [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00683-106">For more information on configuring tracing, see: [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="00683-107">추적 파일 뷰어에 대한 자세한 내용은 [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00683-107">For more information on the trace file viewer, see: [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span></span>  
  
1. [<span data-ttu-id="00683-108">Windows 7 및 IIS 설치 후 WCF 서비스를 탐색하려고 시도하면 다음 오류 메시지가 표시됩니다: HTTP 오류 404.3 – 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="00683-108">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>](#bkmk_0)  
  
     <span data-ttu-id="00683-109">HTTP 오류 404.3 – 찾을 수 없음. 확장명 구성으로 인해 요청한 페이지를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-109">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="00683-110">페이지가 스크립트인 경우 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-110">If the page is a script, add a handler.</span></span> <span data-ttu-id="00683-111">파일을 다운로드해야 하는 경우 MIME 맵을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-111">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="00683-112">자세한 오류 정보 모듈은 StaticFileModule입니다.</span><span class="sxs-lookup"><span data-stu-id="00683-112">Detailed Error InformationModule StaticFileModule.</span></span>  
  
2. [<span data-ttu-id="00683-113">첫 번째 요청 이후 클라이언트가 잠시 유휴 상태인 경우 두 번째 요청에서 MessageSecurityException를 수신 하는 경우도 있습니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-113">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request. What is happening?</span></span>](#BKMK_q1)  
  
3. [<span data-ttu-id="00683-114">약 10 개의 클라이언트가 상호 작용 하 고 나면 서비스에서 새 클라이언트를 거부 하기 시작 합니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-114">My service starts to reject new clients after about 10 clients are interacting with it. What is happening?</span></span>](#BKMK_q2)  
  
4. [<span data-ttu-id="00683-115">WCF 애플리케이션의 구성 파일이 아닌 다른 위치에서 서비스 구성을 로드할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="00683-115">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>](#BKMK_q3)  
  
5. [<span data-ttu-id="00683-116">서비스와 클라이언트는 잘 작동 하지만 클라이언트가 다른 컴퓨터에 있는 경우에는이 작업을 수행할 수 없습니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-116">My service and client work great, but I can’t get them to work when the client is on another computer? What’s happening?</span></span>](#BKMK_q4)  
  
6. [<span data-ttu-id="00683-117">형식이 예외인 예외 >\<FaultException을 throw 하는 경우 항상 제네릭 형식이 아닌 클라이언트에서 일반 FaultException 형식을 받습니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-117">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type. What’s happening?</span></span>](#BKMK_q5)  
  
7. [<span data-ttu-id="00683-118">회신에 데이터가 포함 되지 않은 경우 단방향 및 요청-회신 작업이 거의 같은 속도로 반환 되는 것 같습니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-118">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data. What's happening?</span></span>](#BKMK_q6)  
  
8. [<span data-ttu-id="00683-119">필자는 서비스에 x.509 인증서를 사용 하 고 있으며 System.security.cryptography.cryptographicexception를 가져옵니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-119">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException. What’s happening?</span></span>](#BKMK_q77)  
  
9. [<span data-ttu-id="00683-120">작업의 첫 번째 매개 변수를 대문자에서 소문자로 변경 했습니다. 이제 클라이언트에서 예외를 throw 합니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-120">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception. What's happening?</span></span>](#BKMK_q88)  
  
10. [<span data-ttu-id="00683-121">필자는 추적 도구 중 하나를 사용 하 여 System.servicemodel.endpointnotfoundexception을 가져옵니다. 무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="00683-121">I’m using one of my tracing tools and I get an EndpointNotFoundException. What’s happening?</span></span>](#BKMK_q99)  
  
11. [<span data-ttu-id="00683-122">WCF SOAP 애플리케이션에서 WCF 웹 HTTP 애플리케이션을 호출하면 서비스에서 다음 오류를 반환합니다: 405 메서드가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-122">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>](#BK_MK99)  
  
 [<span data-ttu-id="00683-123">기본 주소는 무엇 인가요? 끝점 주소와 어떤 관계가 있나요?</span><span class="sxs-lookup"><span data-stu-id="00683-123">What is the base address? How does it relate to an endpoint address?</span></span>](#BKMK_q10)  
  
<a name="bkmk_0"></a>   
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a><span data-ttu-id="00683-124">Windows 7 및 IIS 설치 후 WCF 서비스를 탐색하려고 시도하면 다음 오류 메시지가 표시됩니다: HTTP 오류 404.3 – 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="00683-124">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>  
 <span data-ttu-id="00683-125">전체 오류 메시지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-125">The full error message is:</span></span>  
  
 <span data-ttu-id="00683-126">HTTP 오류 404.3 – 찾을 수 없음. 확장명 구성으로 인해 요청한 페이지를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-126">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="00683-127">페이지가 스크립트인 경우 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-127">If the page is a script, add a handler.</span></span> <span data-ttu-id="00683-128">파일을 다운로드해야 하는 경우 MIME 맵을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-128">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="00683-129">자세한 오류 정보 모듈은 StaticFileModule입니다.</span><span class="sxs-lookup"><span data-stu-id="00683-129">Detailed Error InformationModule StaticFileModule.</span></span>  
  
 <span data-ttu-id="00683-130">이 오류 메시지는 제어판에서 "Windows Communication Foundation HTTP 활성화"가 명시적으로 설정 되지 않은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-130">This error message occurs when "Windows Communication Foundation HTTP Activation" is not explicitly set in the Control Panel.</span></span> <span data-ttu-id="00683-131">이를 설정 하려면 제어판의 왼쪽 아래 모서리에서 프로그램을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-131">To set this go to the Control Panel, click Programs in the lower left-hand corner of the window.</span></span> <span data-ttu-id="00683-132">Windows 기능 사용/사용 안 함을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-132">Click Turn Windows features on or off.</span></span> <span data-ttu-id="00683-133">Microsoft .NET Framework 3.5.1을 확장하고 Windows Communication Foundation HTTP 활성화를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-133">Expand Microsoft .NET Framework 3.5.1 and select Windows Communication Foundation HTTP Activation.</span></span>  
  
<a name="BKMK_q1"></a>   
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a><span data-ttu-id="00683-134">첫 번째 요청 이후 클라이언트가 잠시 유휴 상태일 때 가끔씩 두 번째 요청에서 MessageSecurityException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-134">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request.</span></span> <span data-ttu-id="00683-135">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-135">What is happening?</span></span>  
 <span data-ttu-id="00683-136">두 번째 요청은 주로 (1) 세션 시간 제한이 초과되었거나 (2) 서비스를 호스팅하는 웹 서버가 재활용되는 경우와 같은 두 가지 이유로 인해 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-136">The second request can fail primarily for two reasons: (1) the session has timed out or (2) the Web server that is hosting the service is recycled.</span></span> <span data-ttu-id="00683-137">첫 번째 경우에는 서비스가 시간 초과 될 때까지 세션이 유효 합니다. 서비스에서 서비스의 바인딩 (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>)에 지정 된 기간 내에 클라이언트의 요청을 받지 못하면 서비스는 보안 세션을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-137">In the first case, the session is valid until the service times out. When the service does not receive a request from the client within the period of time specified in the service's binding (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), the service terminates the security session.</span></span> <span data-ttu-id="00683-138">이후로 클라이언트 메시지가 전송되면 <xref:System.ServiceModel.Security.MessageSecurityException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-138">Subsequent client messages result in the <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="00683-139">클라이언트는 이후로 메시지를 보내거나 상태 저장 보안 컨텍스트 토큰을 사용하려면 서비스와의 보안 세션을 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-139">The client must re-establish a secure session with the service to send future messages or use a stateful security context token.</span></span> <span data-ttu-id="00683-140">상태 저장 보안 컨텍스트 토큰을 사용하여 웹 서버가 재생되는 동안 보안 세션이 유지되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-140">Stateful security context tokens also allow a secure session to survive a Web server being recycled.</span></span> <span data-ttu-id="00683-141">보안 세션에서 상태 저장 보안 컨텍스트 토큰을 사용 하는 방법에 대 한 자세한 내용은 [방법: 보안 세션에 대 한 보안 컨텍스트 토큰 만들기](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00683-141">For more information about using stateful secure context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span> <span data-ttu-id="00683-142">또는 보안 세션을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-142">Alternatively, you can disable secure sessions.</span></span> <span data-ttu-id="00683-143">[\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) 바인딩을 사용 하는 경우 `establishSecurityContext` 속성을 `false`로 설정 하 여 보안 세션을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-143">When you use the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) binding, you can set the `establishSecurityContext` property to `false` to disable secure sessions.</span></span> <span data-ttu-id="00683-144">다른 바인딩의 보안 세션을 사용하지 않도록 설정하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-144">To disable secure sessions for other bindings, you must create a custom binding.</span></span> <span data-ttu-id="00683-145">사용자 지정 바인딩을 만드는 방법에 대한 자세한 내용은 [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00683-145">For details about creating a custom binding, see [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="00683-146">이러한 옵션을 적용하기 전에 먼저 애플리케이션의 보안 요구 사항을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-146">Before you apply any of these options, you must understand your application's security requirements.</span></span>  
  
<a name="BKMK_q2"></a>   
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a><span data-ttu-id="00683-147">서비스와 상호 작용하는 클라이언트의 수가 약 10개를 넘으면 서비스가 새 클라이언트를 거부하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-147">My service starts to reject new clients after about 10 clients are interacting with it.</span></span> <span data-ttu-id="00683-148">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-148">What is happening?</span></span>  
 <span data-ttu-id="00683-149">기본적으로 서비스는 10개의 동시 세션만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-149">By default, services can have only 10 concurrent sessions.</span></span> <span data-ttu-id="00683-150">따라서 서비스 바인딩에서 세션을 사용하는 경우 서비스는 이 숫자에 도달할 때까지 새 클라이언트 연결을 수락하고, 그 후에는 현재 세션 중 하나가 끝날 때까지 새 클라이언트 연결을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-150">Therefore, if the service bindings use sessions, the service accepts new client connections until it reaches that number, after which it refuses new client connections until one of the current sessions ends.</span></span> <span data-ttu-id="00683-151">여러 가지 방법을 통해 더 많은 클라이언트를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-151">You can support more clients in a number of ways.</span></span> <span data-ttu-id="00683-152">먼저, 서비스에 세션이 필요하지 않은 경우 세션 바인딩을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-152">If your service does not require sessions, do not use a sessionful binding.</span></span> <span data-ttu-id="00683-153">자세한 내용은 [세션 사용](using-sessions.md)을 참조 하세요. 또 다른 옵션은 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> 속성의 값을 사용자의 상황에 적합 한 숫자로 변경 하 여 세션 제한을 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00683-153">(For more information, see [Using Sessions](using-sessions.md).) Another option is to increase the session limit by changing the value of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> property to the number appropriate to your circumstance.</span></span>  
  
<a name="BKMK_q3"></a>   
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a><span data-ttu-id="00683-154">WCF 애플리케이션의 구성 파일이 아닌 다른 위치에서 서비스 구성을 로드할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="00683-154">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>  
 <span data-ttu-id="00683-155">예. 그러나 <xref:System.ServiceModel.ServiceHost> 메서드를 재정의하는 사용자 지정 <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-155">Yes, however, you have to create a custom <xref:System.ServiceModel.ServiceHost> class that overrides the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method.</span></span> <span data-ttu-id="00683-156">이 메서드 내에서 기본을 호출하여 구성을 먼저 로드할 수 있으며(표준 구성 정보도 함께 로드하려는 경우), 또한 구성 로딩 시스템을 완전히 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-156">Inside that method, you can call the base to load configuration first (if you want to load the standard configuration information as well) but you can also entirely replace the configuration loading system.</span></span> <span data-ttu-id="00683-157">응용 프로그램 구성 파일과 다른 구성 파일에서 구성을 로드 하려는 경우 구성 파일을 직접 구문 분석 하 고 구성을 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-157">If you want to load configuration from a configuration file that is different from the application configuration file, you must parse the configuration file yourself and load the configuration.</span></span>  
  
 <span data-ttu-id="00683-158">다음 코드 예제는 <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> 메서드를 재정의하고 엔드포인트를 직접 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00683-158">The following code example shows how to override the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method and directly configure an endpoint.</span></span>  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)    
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>   
## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a><span data-ttu-id="00683-159">서비스와 클라이언트는 문제없이 작동하는데 클라이언트가 다른 컴퓨터에 있으면 둘 다 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-159">My service and client work great, but I can’t get them to work when the client is on another computer?</span></span> <span data-ttu-id="00683-160">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-160">What’s happening?</span></span>  
 <span data-ttu-id="00683-161">예외에 따라 여러 가지 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-161">Depending upon the exception, there may be several issues:</span></span>  
  
- <span data-ttu-id="00683-162">클라이언트 엔드포인트 주소를 "localhost" 대신 호스트 이름으로 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-162">You might need to change the client endpoint addresses to the host name and not "localhost".</span></span>  
  
- <span data-ttu-id="00683-163">애플리케이션에 연결되는 포트를 열어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-163">You might need to open the port to the application.</span></span> <span data-ttu-id="00683-164">자세한 내용은 SDK 샘플에서 [Firewall Instructions](./samples/firewall-instructions.md) 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00683-164">For details, see [Firewall Instructions](./samples/firewall-instructions.md) from the SDK samples.</span></span>  
  
- <span data-ttu-id="00683-165">가능한 다른 문제는 샘플 항목 [Windows Communication Foundation 샘플 실행](./samples/running-the-samples.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00683-165">For other possible issues, see the samples topic [Running the Windows Communication Foundation Samples](./samples/running-the-samples.md).</span></span>  
  
- <span data-ttu-id="00683-166">클라이언트가 Windows 자격 증명을 사용하고 예외가 <xref:System.ServiceModel.Security.SecurityNegotiationException>인 경우 다음과 같이 Kerberos를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-166">If your client is using Windows credentials and the exception is a <xref:System.ServiceModel.Security.SecurityNegotiationException>, configure Kerberos as follows.</span></span>  
  
    1. <span data-ttu-id="00683-167">클라이언트 App.config 파일의 엔드포인트 요소에 ID 자격 증명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-167">Add the identity credentials to the endpoint element in the client’s App.config file:</span></span>  
  
        ```xml
        <endpoint   
          address="http://MyServer:8000/MyService/"   
          binding="wsHttpBinding"   
          bindingConfiguration="WSHttpBinding_IServiceExample"   
          contract="IServiceExample"   
          behaviorConfiguration="ClientCredBehavior"   
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2. <span data-ttu-id="00683-168">System 또는 NetworkService 계정으로 자체 호스팅 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-168">Run the self-hosted service under the System or NetworkService account.</span></span> <span data-ttu-id="00683-169">다음 명령을 실행하여 System 계정으로 명령 창을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-169">You can run this command to create a command window under the System account:</span></span>  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. <span data-ttu-id="00683-170">기본적으로 SPN(서비스 사용자 이름) 계정을 사용하는 IIS(인터넷 정보 서비스)에서 서비스를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-170">Host the service under Internet Information Services (IIS), which, by default, uses the service principal name (SPN) account.</span></span>  
  
    4. <span data-ttu-id="00683-171">SetSPN을 사용하여 도메인에 새 SPN을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-171">Register a new SPN with the domain using SetSPN.</span></span> <span data-ttu-id="00683-172">이 작업을 수행 하려면 도메인 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-172">You need to be a domain administrator in order to do this.</span></span>  
  
 <span data-ttu-id="00683-173">Kerberos 프로토콜에 대 한 자세한 내용은 WCF 및 [에서 사용 되는 보안 개념](./feature-details/security-concepts-used-in-wcf.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00683-173">For more information about the Kerberos protocol, see [Security Concepts Used in WCF](./feature-details/security-concepts-used-in-wcf.md) and:</span></span>  
  
- [<span data-ttu-id="00683-174">Windows 인증 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="00683-174">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)  
  
- <span data-ttu-id="00683-175">[Http.sys를 사용하여 Kerberos 서비스 보안 주체 이름 등록(영문 페이지일 수 있음)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="00683-175">[Registering Kerberos Service Principal Names by Using Http.sys](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span></span>  
  
- <span data-ttu-id="00683-176">[Kerberos 설명(영문 페이지일 수 있음)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/bb742516(v%3dtechnet.10))</span><span class="sxs-lookup"><span data-stu-id="00683-176">[Kerberos Explained](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/bb742516(v%3dtechnet.10))</span></span>  
  
<a name="BKMK_q5"></a>   
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a><span data-ttu-id="00683-177">형식이 예외인 예외 >\<FaultException을 throw 하는 경우 항상 제네릭 형식이 아닌 클라이언트에서 일반 FaultException 형식을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-177">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type.</span></span> <span data-ttu-id="00683-178">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-178">What’s happening?</span></span>  
 <span data-ttu-id="00683-179">사용자 지정 오류 데이터 형식을 만들고 이 형식을 오류 계약에서 세부 형식으로 선언하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-179">It is highly recommended that you create your own custom error data type and declare that as the detail type in your fault contract.</span></span> <span data-ttu-id="00683-180">시스템 제공 예외 형식을 사용하는 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-180">The reason is that using system-provided exception types:</span></span>  
  
- <span data-ttu-id="00683-181">서비스 지향 애플리케이션의 가장 큰 장점 중 하나를 제거하는 형식 종속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00683-181">Creates a type dependency that removes one of the biggest strengths of service-oriented applications.</span></span>  
  
- <span data-ttu-id="00683-182">표준 방법으로 serialize하는 예외에 의존할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-182">Cannot depend upon exceptions serializing in a standard way.</span></span> <span data-ttu-id="00683-183"><xref:System.Security.SecurityException>과 같이 전혀 serialize할 수 없는 것도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-183">Some—like <xref:System.Security.SecurityException>—may not be serializable at all.</span></span>  
  
- <span data-ttu-id="00683-184">내부 구현 세부 정보를 클라이언트에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-184">Exposes internal implementation details to clients.</span></span> <span data-ttu-id="00683-185">자세한 내용은 [지정 및 계약 및 서비스에서 오류 처리](specifying-and-handling-faults-in-contracts-and-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-185">For more information, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
 <span data-ttu-id="00683-186">그러나 애플리케이션을 디버깅하는 경우에는 <xref:System.ServiceModel.Description.ServiceDebugBehavior> 클래스를 사용하여 예외 정보를 serialize하고 클라이언트에 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-186">If you are debugging an application, however, you can serialize exception information and return it to the client by using the <xref:System.ServiceModel.Description.ServiceDebugBehavior> class.</span></span>  
  
<a name="BKMK_q6"></a>   
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a><span data-ttu-id="00683-187">회신에 데이터가 포함되지 않은 경우 단방향 및 요청-회신 작업이 거의 같은 속도로 반환되는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-187">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data.</span></span> <span data-ttu-id="00683-188">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-188">What's happening?</span></span>  
 <span data-ttu-id="00683-189">작업을 단방향 작업으로 지정한다는 것은 작업 계약이 입력 메시지를 받은 다음 출력 메시지를 반환하지 않는다는 것을 의미할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="00683-189">Specifying that an operation is one way means only that the operation contract accepts an input message and does not return an output message.</span></span> <span data-ttu-id="00683-190">WCF에서 모든 클라이언트 호출은 아웃 바운드 데이터가 네트워크에 기록 되거나 예외가 throw 될 때를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-190">In WCF, all client invocations return when the outbound data has been written to the wire or an exception is thrown.</span></span> <span data-ttu-id="00683-191">단방향 작업도 이와 동일한 방식으로 작동하며, 서비스를 찾을 수 없는 경우 throw되거나 서비스가 네트워크로부터 데이터를 받을 준비가 되지 않은 경우 블로킹될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-191">One-way operations work the same way, and they can throw if the service cannot be located or block if the service is not prepared to accept the data from the network.</span></span> <span data-ttu-id="00683-192">일반적으로 WCF에서는 단방향 호출이 요청-회신 보다 더 빨리 클라이언트에 반환 됩니다. 하지만 네트워크를 통해 아웃 바운드 데이터를 보내는 속도가 느려지는 상황이 발생 하는 경우 요청-회신 작업 뿐만 아니라 단방향 작업이 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="00683-192">Typically in WCF, this results in one-way calls returning to the client more quickly than request-reply; but any condition that slows the sending of the outbound data over the network slows one-way operations as well as request-reply operations.</span></span> <span data-ttu-id="00683-193">자세한 내용은 [WCF 클라이언트를 사용 하 여](./feature-details/accessing-services-using-a-client.md) [단방향 서비스](./feature-details/one-way-services.md) 및 서비스 액세스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00683-193">For more information, see [One-Way Services](./feature-details/one-way-services.md) and [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md).</span></span>  
  
<a name="BKMK_q77"></a>   
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a><span data-ttu-id="00683-194">서비스에 X.509 인증서를 사용하고 있으며 System.Security.Cryptography.CryptographicException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-194">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException.</span></span> <span data-ttu-id="00683-195">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-195">What’s happening?</span></span>  
 <span data-ttu-id="00683-196">이 예외는 보통 IIS 작업자 프로세스를 실행하는 데 사용되는 사용자 계정을 변경한 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-196">This commonly occurs after changing the user account under which the IIS worker process runs.</span></span> <span data-ttu-id="00683-197">예를 들어 Windows XP에서, Aspnet_wp 실행 되는 기본 사용자 계정을 ASPNET에서 사용자 지정 사용자 계정으로 변경 하면이 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-197">For example, in Windows XP, if you change the default user account that the Aspnet_wp.exe runs under from ASPNET to a custom user account, you may see this error.</span></span> <span data-ttu-id="00683-198">프라이빗 키를 사용하는 경우 이 키를 사용하는 프로세스에는 키가 저장된 파일에 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-198">If using a private key, the process that uses it will need to have permissions to access the file storing that key.</span></span>  
  
 <span data-ttu-id="00683-199">이 경우에는 프라이빗 키가 포함된 파일에 대한 프로세스 계정에 읽기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-199">If this is the case, you must give read access privileges to the process's account for the file containing the private key.</span></span> <span data-ttu-id="00683-200">예를 들어, IIS 작업자 프로세스가 밥 계정에서 실행되는 경우 밥에게 프라이빗 키가 포함된 파일에 대한 읽기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-200">For example, if the IIS worker process is running under the Bob account, then you will need to give Bob read access to the file containing the private key.</span></span>  
  
 <span data-ttu-id="00683-201">특정 x.509 인증서에 대 한 개인 키가 포함 된 파일에 대 한 올바른 사용자 계정 액세스 권한을 제공 하는 방법에 대 한 자세한 내용은 [방법: WCF에서 X.509 인증서에 액세스할 수 있도록 설정](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00683-201">For more information about how to give the correct user account access to the file that contains the private key for a specific X.509 certificate, see [How to: Make X.509 Certificates Accessible to WCF](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span></span>  
  
<a name="BKMK_q88"></a>   
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a><span data-ttu-id="00683-202">작업의 첫 번째 매개 변수를 대문자에서 소문자로 변경한 다음에 클라이언트에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="00683-202">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception.</span></span> <span data-ttu-id="00683-203">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-203">What's happening?</span></span>  
 <span data-ttu-id="00683-204">작업 시그니처의 매개 변수 이름 값은 계약의 일부 이며 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-204">The values of the parameter names in the operation signature are part of the contract and are case-sensitive.</span></span> <span data-ttu-id="00683-205">로컬 매개 변수 이름과 클라이언트 애플리케이션의 작업을 설명하는 메타데이터를 구분해야 하는 경우에는 <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> 특성을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="00683-205">Use the <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> attribute when you need to distinguish between the local parameter name and the metadata that describes the operation for client applications.</span></span>  
  
<a name="BKMK_q99"></a>   
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a><span data-ttu-id="00683-206">추적 도구 중 하나를 사용하는 동안 EndpointNotFoundException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-206">I’m using one of my tracing tools and I get an EndpointNotFoundException.</span></span> <span data-ttu-id="00683-207">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-207">What’s happening?</span></span>  
 <span data-ttu-id="00683-208">시스템에서 제공 하는 WCF 추적 메커니즘이 아닌 추적 도구를 사용 하는 경우 주소 필터가 일치 하지 않음을 나타내는 <xref:System.ServiceModel.EndpointNotFoundException>를 수신 하는 경우 <xref:System.ServiceModel.Description.ClientViaBehavior> 클래스를 사용 하 여 메시지를 추적 유틸리티로 보내고 유틸리티가 해당 메시지를 서비스 주소로 리디렉션하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-208">If you are using a tracing tool that is not the system-provided WCF tracing mechanism and you receive an <xref:System.ServiceModel.EndpointNotFoundException> that indicates that there was an address filter mismatch, you need to use the <xref:System.ServiceModel.Description.ClientViaBehavior> class to direct the messages to the tracing utility and have the utility redirect those messages to the service address.</span></span> <span data-ttu-id="00683-209"><xref:System.ServiceModel.Description.ClientViaBehavior> 클래스는 `Via` 주소 지정 헤더를 변경하여 `To` 주소 지정 헤더로 표시되는 최종 수신자와 별도로 다음 네트워크 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-209">The <xref:System.ServiceModel.Description.ClientViaBehavior> class alters the `Via` addressing header to specify the next network address separately from the ultimate receiver, indicated by the `To` addressing header.</span></span> <span data-ttu-id="00683-210">그러나 이 경우 `To` 값을 설정하는 데 사용되는 엔드포인트 주소를 변경해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00683-210">When doing this, however, do not change the endpoint address, which is used to establish the `To` value.</span></span>  
  
 <span data-ttu-id="00683-211">다음 코드 예제는 클라이언트 구성 파일의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00683-211">The following code example shows an example client configuration file.</span></span>  
  
```xml
<endpoint   
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"   
  contract="IMyContract"   
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>   
## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a><span data-ttu-id="00683-212">기본 주소란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00683-212">What is the base address?</span></span> <span data-ttu-id="00683-213">엔드포인트 주소와는 어떤 관계가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="00683-213">How does it relate to an endpoint address?</span></span>  
 <span data-ttu-id="00683-214">기본 주소는 <xref:System.ServiceModel.ServiceHost> 클래스의 루트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="00683-214">A base address is the root address for a <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="00683-215">기본적으로 서비스 구성에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스를 추가하면 호스트가 게시하는 모든 엔드포인트에 대한 WSDL(웹 서비스 기술 언어)이 HTTP 기본 주소, 메타데이터 동작에 제공된 관련 주소 및 "?wsdl"에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="00683-215">By default, if you add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class into your service configuration, the Web Services Description Language (WSDL) for all endpoints the host publishes are retrieved from the HTTP base address, plus any relative address provided to the metadata behavior, plus "?wsdl".</span></span> <span data-ttu-id="00683-216">ASP.NET 및 IIS에 대해 잘 알고 있는 경우 기본 주소는 가상 디렉터리와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="00683-216">If you are familiar with ASP.NET and IIS, the base address is equivalent to the virtual directory.</span></span>  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a><span data-ttu-id="00683-217">NetTcpBinding을 사용하여 서비스 엔드포인트와 MEX 엔드포인트 간에 포트 공유</span><span class="sxs-lookup"><span data-stu-id="00683-217">Sharing a port between a service endpoint and a mex endpoint using the NetTcpBinding</span></span>  
 <span data-ttu-id="00683-218">서비스의 기본 주소를 net.tcp://MyServer:8080/MyService로 지정하고 다음 엔드포인트를 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="00683-218">If you specify the base address for a service as net.tcp://MyServer:8080/MyService and add the following endpoints:</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="00683-219">다음 구성 코드 조각에 나와 있는 것처럼 NetTcpBinding 설정 중 하나를 수정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="00683-219">And if you modify one of the NetTcpBinding settings as shown in the following configuration snippet:</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="00683-220">처리되지 않은 예외: System.ServiceModel.AddressAlreadyInUseException: IP 엔드포인트 0.0.0.0:9000에 이미 수신기가 있습니다.와 유사한 오류가 표시됩니다. 다음 구성 코드 조각에 나와 있는 것처럼 MEX 엔드포인트에 다른 포트를 사용하는 정규화된 URL을 지정하여 이 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-220">You will see an error like the following: Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000 You can work around this error by specifying a fully qualified URL with a different port for the MEX endpoint as shown in the following configuration snippet:</span></span>  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>   
## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a><span data-ttu-id="00683-221">WCF SOAP 애플리케이션에서 WCF 웹 HTTP 애플리케이션을 호출하면 서비스에서 다음 오류를 반환합니다: 405 메서드가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-221">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>  
 <span data-ttu-id="00683-222">Wcf 서비스에서 WCF 웹 HTTP 응용 프로그램 (<xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>를 사용 하는 서비스)을 호출 하면 다음과 같은 예외가 발생할 수 있습니다 .이 예외는 WCF에서 들어오는 <xref:System.ServiceModel.OperationContext>를 사용 하 여 나가는 <xref:System.ServiceModel.OperationContext>를 덮어쓰기 때문에 발생 합니다 ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.``.</span><span class="sxs-lookup"><span data-stu-id="00683-222">Calling a WCF Web HTTP application (a service that uses the <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior>) from a WCF service may generate the following exception: ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` This exception occurs because WCF overwrites the outgoing <xref:System.ServiceModel.OperationContext> with the incoming <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="00683-223">이 문제를 해결 하려면 WCF 웹 HTTP 서비스 작업 내에 <xref:System.ServiceModel.OperationContextScope>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00683-223">To solve this problem, create an <xref:System.ServiceModel.OperationContextScope> within the WCF Web HTTP service operation.</span></span> <span data-ttu-id="00683-224">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00683-224">For example:</span></span>  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="00683-225">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00683-225">See also</span></span>

- [<span data-ttu-id="00683-226">Windows 인증 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="00683-226">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)
