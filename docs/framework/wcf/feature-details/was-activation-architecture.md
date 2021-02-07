---
description: WAS 활성화 아키텍처에 대해 자세히 알아보세요.
title: WAS Activation 아키텍처
ms.date: 03/30/2017
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
ms.openlocfilehash: 616b3b404258356bcd5600c68b6f70aaf096e978
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756021"
---
# <a name="was-activation-architecture"></a><span data-ttu-id="5b6af-103">WAS Activation 아키텍처</span><span class="sxs-lookup"><span data-stu-id="5b6af-103">WAS Activation Architecture</span></span>

<span data-ttu-id="5b6af-104">이 항목에서는 Windows Process Activation Service(WAS라고도 함)의 구성 요소를 항목별로 정리하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-104">This topic itemizes and discusses the components of the Windows Process Activation Service (also known as WAS).</span></span>  
  
## <a name="activation-components"></a><span data-ttu-id="5b6af-105">활성화 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5b6af-105">Activation Components</span></span>  

 <span data-ttu-id="5b6af-106">WAS는 여러 가지 아키텍처 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-106">WAS consists of several architectural components:</span></span>  
  
- <span data-ttu-id="5b6af-107">수신기 어댑터.</span><span class="sxs-lookup"><span data-stu-id="5b6af-107">Listener adapters.</span></span> <span data-ttu-id="5b6af-108">특정 네트워크 프로토콜에서 메시지를 받고, 들어오는 메시지를 올바른 작업자 프로세스로 라우트하기 위해 WAS와 통신하는 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-108">Windows services that receive messages on specific network protocols and communicate with WAS to route incoming messages to the correct worker process.</span></span>  
  
- <span data-ttu-id="5b6af-109">WAS.</span><span class="sxs-lookup"><span data-stu-id="5b6af-109">WAS.</span></span> <span data-ttu-id="5b6af-110">작업자 프로세스 만들기 및 수명을 관리하는 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-110">The Windows service that manages the creation and lifetime of worker processes.</span></span>  
  
- <span data-ttu-id="5b6af-111">제네릭 작업자 프로세스 실행 파일(w3wp.exe).</span><span class="sxs-lookup"><span data-stu-id="5b6af-111">The generic worker process executable (w3wp.exe).</span></span>  
  
- <span data-ttu-id="5b6af-112">애플리케이션 관리자.</span><span class="sxs-lookup"><span data-stu-id="5b6af-112">Application manager.</span></span> <span data-ttu-id="5b6af-113">작업자 프로세스 내에서 애플리케이션을 호스팅하는 애플리케이션 도메인 만들기 및 수명을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-113">Manages the creation and lifetime of application domains that host applications within the worker process.</span></span>  
  
- <span data-ttu-id="5b6af-114">프로토콜 처리기.</span><span class="sxs-lookup"><span data-stu-id="5b6af-114">Protocol handlers.</span></span> <span data-ttu-id="5b6af-115">작업자 프로세스에서 실행되고 작업자 프로세스와 개별 수신기 어댑터 간 통신을 관리하는 프로토콜 관련 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-115">Protocol-specific components that run in the worker process and manage communication between the worker process and the individual listener adapters.</span></span> <span data-ttu-id="5b6af-116">프로토콜 처리기 형식에는 프로세스 프로토콜 처리기와 AppDomain 프로토콜 처리기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-116">Two types of protocol handlers exist: process protocol handlers and AppDomain protocol handlers.</span></span>  
  
 <span data-ttu-id="5b6af-117">WAS가 작업자 프로세스 인스턴스를 활성화하면 작업자 프로세스에 필요한 프로세스 프로토콜 처리기를 로드하고, 애플리케이션 관리자를 사용하여 애플리케이션을 호스트할 애플리케이션 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-117">When WAS activates a worker process instance, it loads the process protocol handlers required into the worker process and uses the application manager to create an application domain to host the application.</span></span> <span data-ttu-id="5b6af-118">애플리케이션 도메인은 애플리케이션에서 사용하는 네트워크 프로토콜에 필요한 AppDomain 프로토콜 처리기와 애플리케이션의 코드를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-118">The application domain loads the application’s code as well as the AppDomain protocol handlers that the network protocols used by the application require.</span></span>  
  
 ![WAS 아키텍처를 보여 주는 스크린샷](./media/was-activation-architecture/windows-process-application-service-architecture.gif)  
  
### <a name="listener-adapters"></a><span data-ttu-id="5b6af-120">수신기 어댑터</span><span class="sxs-lookup"><span data-stu-id="5b6af-120">Listener Adapters</span></span>  

 <span data-ttu-id="5b6af-121">수신기 어댑터는 수신 대기하는 네트워크 프로토콜을 사용하여 메시지를 받는 데 사용되는 네트워크 통신 논리를 구현하는 개별 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-121">Listener adapters are individual Windows services that implement the network communication logic used to receive messages using the network protocol on which they listen.</span></span> <span data-ttu-id="5b6af-122">다음 표에서는 WCF (Windows Communication Foundation) 프로토콜용 수신기 어댑터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-122">The following table lists the listener adapters for Windows Communication Foundation (WCF) protocols.</span></span>  
  
|<span data-ttu-id="5b6af-123">수신기 어댑터 서비스 이름</span><span class="sxs-lookup"><span data-stu-id="5b6af-123">Listener adapter service name</span></span>|<span data-ttu-id="5b6af-124">프로토콜</span><span class="sxs-lookup"><span data-stu-id="5b6af-124">Protocol</span></span>|<span data-ttu-id="5b6af-125">참고</span><span class="sxs-lookup"><span data-stu-id="5b6af-125">Notes</span></span>|  
|-----------------------------------|--------------|-----------|  
|<span data-ttu-id="5b6af-126">W3SVC</span><span class="sxs-lookup"><span data-stu-id="5b6af-126">W3SVC</span></span>|<span data-ttu-id="5b6af-127">http</span><span class="sxs-lookup"><span data-stu-id="5b6af-127">http</span></span>|<span data-ttu-id="5b6af-128">IIS 7.0 및 WCF 모두에 대해 HTTP 활성화를 제공 하는 공용 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-128">Common component that provides HTTP activation for both IIS 7.0 and WCF.</span></span>|  
|<span data-ttu-id="5b6af-129">NetTcpActivator</span><span class="sxs-lookup"><span data-stu-id="5b6af-129">NetTcpActivator</span></span>|<span data-ttu-id="5b6af-130">net.tcp</span><span class="sxs-lookup"><span data-stu-id="5b6af-130">net.tcp</span></span>|<span data-ttu-id="5b6af-131">NetTcpPortSharing 서비스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-131">Depends on the NetTcpPortSharing service.</span></span>|  
|<span data-ttu-id="5b6af-132">NetPipeActivator</span><span class="sxs-lookup"><span data-stu-id="5b6af-132">NetPipeActivator</span></span>|<span data-ttu-id="5b6af-133">net.pipe</span><span class="sxs-lookup"><span data-stu-id="5b6af-133">net.pipe</span></span>||  
|<span data-ttu-id="5b6af-134">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="5b6af-134">NetMsmqActivator</span></span>|<span data-ttu-id="5b6af-135">net.msmq</span><span class="sxs-lookup"><span data-stu-id="5b6af-135">net.msmq</span></span>|<span data-ttu-id="5b6af-136">WCF 기반 메시지 큐 응용 프로그램에 사용할입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-136">For use with WCF-based Message Queuing applications.</span></span>|  
|<span data-ttu-id="5b6af-137">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="5b6af-137">NetMsmqActivator</span></span>|<span data-ttu-id="5b6af-138">msmq.formatname</span><span class="sxs-lookup"><span data-stu-id="5b6af-138">msmq.formatname</span></span>|<span data-ttu-id="5b6af-139">이전 버전의 기존 메시지 큐 애플리케이션과의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-139">Provides backwards compatibility with existing Message Queuing applications.</span></span>|  
  
 <span data-ttu-id="5b6af-140">특정 프로토콜의 수신기 어댑터는 다음 XML 예제에서처럼 설치하는 동안 applicationHost.config 파일에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-140">Listener adapters for specific protocols are registered during installation in the applicationHost.config file, as shown in the following XML example.</span></span>  
  
```xml  
<system.applicationHost>  
    <listenerAdapters>  
        <add name="http" />  
        <add name="net.tcp"
          identity="S-1-5-80-3579033775-2824656752-1522793541-1960352512-462907086" />  
         <add name="net.pipe"
           identity="S-1-5-80-2943419899-937267781-4189664001-1229628381-3982115073" />  
          <add name="net.msmq"
            identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
           <add name="msmq.formatname"
             identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
    </listenerAdapters>  
</system.applicationHost>  
```  
  
### <a name="protocol-handlers"></a><span data-ttu-id="5b6af-141">프로토콜 처리기</span><span class="sxs-lookup"><span data-stu-id="5b6af-141">Protocol Handlers</span></span>  

 <span data-ttu-id="5b6af-142">특정 프로토콜에 대한 프로세스 및 AppDomain 프로토콜 처리기는 시스템 수준의 Web.config 파일에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6af-142">Process and AppDomain protocol handlers for specific protocols are registered in the machine-level Web.config file.</span></span>  
  
```xml  
<system.web>  
   <protocols>  
      <add name="net.tcp"
        processHandlerType=  
         "System.ServiceModel.WasHosting.TcpProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.TcpAppDomainProtocolHandler"  
        validate="false" />  
      <add name="net.pipe"
        processHandlerType=  
         "System.ServiceModel.WasHosting.NamedPipeProcessProtocolHandler"  
          appDomainHandlerType=  
           "System.ServiceModel.WasHosting.NamedPipeAppDomainProtocolHandler"/>  
      <add name="net.msmq"  
        processHandlerType=  
         "System.ServiceModel.WasHosting.MsmqProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.MsmqAppDomainProtocolHandler"  
        validate="false" />  
   </protocols>  
</system.web>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b6af-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b6af-143">See also</span></span>

- [<span data-ttu-id="5b6af-144">WCF에서 사용하도록 WAS 구성</span><span class="sxs-lookup"><span data-stu-id="5b6af-144">Configuring WAS for Use with WCF</span></span>](configuring-the-wpa--service-for-use-with-wcf.md)
- <span data-ttu-id="5b6af-145">[Windows Server App Fabric 호스팅 기능](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5b6af-145">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
