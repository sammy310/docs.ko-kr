---
title: Windows Communication Foundation과 함께 사용하도록 Windows Process Activation Service 구성
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 86e50b80d84479ca32b3d4d1fe3f205983640c76
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464165"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a><span data-ttu-id="f9d30-102">Windows Communication Foundation과 함께 사용하도록 Windows Process Activation Service 구성</span><span class="sxs-lookup"><span data-stu-id="f9d30-102">Configuring the Windows Process Activation Service for Use with Windows Communication Foundation</span></span>
<span data-ttu-id="f9d30-103">이 항목에서는 HTTP 네트워크 프로토콜을 통해 통신하지 않는 WCF(Windows 통신 Foundation) 서비스를 호스트하기 위해 Windows Vista에서 WINDOWS 프로세스 정품 인증 서비스(WAS라고도 함)를 설정하는 데 필요한 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) in Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="f9d30-104">다음 단원에서는 이 구성 단계에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="f9d30-105">필요한 WCF 활성화 구성 요소를 설치(또는 설치 확인)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-105">Install (or confirm the installation of) the WCF activation components required.</span></span>  
  
- <span data-ttu-id="f9d30-106">사용할 네트워크 프로토콜 바인딩으로 WAS 사이트를 만들거나 새 프로토콜 바인딩을 기존 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-106">Create a WAS site with the network protocol bindings you wish to use, or add a new protocol binding to an existing site.</span></span>  
  
- <span data-ttu-id="f9d30-107">서비스를 호스팅할 애플리케이션을 만들고 이 애플리케이션에서 필요한 네트워크 프로토콜을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-107">Create an application to host your services and enable that application to use the required network protocols.</span></span>  
  
- <span data-ttu-id="f9d30-108">HTTP가 아닌 끝점을 노출하는 WCF 서비스를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-108">Build a WCF service that exposes a non-HTTP endpoint.</span></span>  
  
## <a name="configuring-a-site-with-non-http-bindings"></a><span data-ttu-id="f9d30-109">HTTP가 아닌 바인딩을 사용하여 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="f9d30-109">Configuring a Site with Non-HTTP bindings</span></span>  
 <span data-ttu-id="f9d30-110">WAS에 HTTP가 아닌 바인딩을 사용하려면 사이트 바인딩을 WAS 구성에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-110">To use a non-HTTP binding with WAS, the site binding must be added to the WAS configuration.</span></span> <span data-ttu-id="f9d30-111">WAS에 대한 구성 저장소는 %windir%\system32\inetsrv\config 디렉터리에 있는 applicationHost.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-111">The configuration store for WAS is the applicationHost.config file, located in the %windir%\system32\inetsrv\config directory.</span></span> <span data-ttu-id="f9d30-112">WAS와 IIS 7.0에서 이 구성 저장소를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-112">This configuration store is shared by both WAS and IIS 7.0.</span></span>  
  
 <span data-ttu-id="f9d30-113">applicationHost.config는 메모장과 같은 표준 텍스트 편집기에서 열 수 있는 XML 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-113">applicationHost.config is an XML text file that can be opened with any standard text editor (such as Notepad).</span></span> <span data-ttu-id="f9d30-114">그러나 IIS 7.0 명령줄 구성 도구(appcmd.exe)는 비 HTTP 사이트 바인딩을 추가하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-114">However, the IIS 7.0 command-line configuration tool (appcmd.exe) is the preferred way to add non-HTTP site bindings.</span></span>  
  
 <span data-ttu-id="f9d30-115">다음 명령은 appcmd.exe(이 명령은 한 줄로 입력됨)를 사용하여 net.tcp 사이트 바인딩을 기본 웹 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-115">The following command adds a net.tcp site binding to the default Web site using appcmd.exe (this command is entered as a single line).</span></span>  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 <span data-ttu-id="f9d30-116">이 명령은 applicationHost.config 파일에 아래 표시된 줄을 추가하여 새 net.tcp 바인딩을 기본 웹 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-116">This command adds the new net.tcp binding to the default Web site by adding the line indicated below to the applicationHost.config file.</span></span>  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a><span data-ttu-id="f9d30-117">HTTP가 아닌 프로토콜을 사용하도록 애플리케이션 설정</span><span class="sxs-lookup"><span data-stu-id="f9d30-117">Enabling an Application to Use Non-HTTP Protocols</span></span>  
 <span data-ttu-id="f9d30-118">응용 프로그램 수준에서 개별 네트워크 프로토콜을 활성화하거나 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-118">You can enable or disable individual network protocolsat the application level.</span></span> <span data-ttu-id="f9d30-119">다음 명령은 `Default Web Site`에서 실행되는 애플리케이션에 대한 HTTP 및 net.tcp 프로토콜을 모두 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-119">The following command illustrates how to enable both the HTTP and net.tcp protocols for an application that runs in the `Default Web Site`.</span></span>  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 <span data-ttu-id="f9d30-120">활성화된 프로토콜 목록은 \<ApplicationDefaults> ApplicationHost.config에 저장된 사이트의 XML 구성 요소에서 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-120">The list of enabled protocols can also be set in the \<applicationDefaults> element of the site’s XML configuration stored in ApplicationHost.config.</span></span>  
  
 <span data-ttu-id="f9d30-121">applicationHost.config의 다음과 같은 XML 코드는 HTTP 프로토콜 및 HTTP가 아닌 프로토콜에 모두 바인딩되는 사이트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-121">The following XML code from applicationHost.config illustrates a site bound to both HTTP and non-HTTP protocols.</span></span> <span data-ttu-id="f9d30-122">HTTP가 아닌 프로토콜을 지원하는 데 필요한 추가 구성은 주석으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-122">The additional configuration required to support non-HTTP protocols is called out with comments.</span></span>  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
      <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
      </application>  
      <bindings>  
            <!-- The following two lines are added by the command. -->
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults
      applicationPool="DefaultAppPool"
      <!-- The following line is inserted by the command. -->
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 <span data-ttu-id="f9d30-123">WAS를 설치 및 구성하지 않은 상태에서 WAS for Non-HTTP Activation을 사용하여 서비스를 활성화하려고 하면 다음 오류가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-123">If you attempt to activate a service using WAS for Non-HTTP activation and you have not installed and configured WAS you may see the following error:</span></span>  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 <span data-ttu-id="f9d30-124">이 오류가 표시되는 경우 WAS for Non-HTTP Activation을 올바르게 설치하고 구성하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9d30-124">If you see this error ensure WAS for Non-HTTP Activation is installed and configured properly.</span></span> <span data-ttu-id="f9d30-125">자세한 내용은 [WCF 활성화 구성 요소 설치 및 구성 방법을](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9d30-125">For more information, see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a><span data-ttu-id="f9d30-126">비 HTTP 활성화에 WAS를 사용하는 WCF 서비스 빌드</span><span class="sxs-lookup"><span data-stu-id="f9d30-126">Building a WCF Service That Uses WAS for Non-HTTP activation</span></span>  
 <span data-ttu-id="f9d30-127">WAS를 설치하고 구성하는 단계를 수행한 [후(WCF 활성화 구성 요소 설치 및 구성 방법](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)참조), 활성화를 위해 WAS를 사용할 서비스를 구성하는 것은 IIS에서 호스팅되는 서비스를 구성하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d30-127">Once you perform the steps to install and configure WAS (see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), configuring a service to use WAS for activation is similar to configuring a service that is hosted in IIS.</span></span>  
  
 <span data-ttu-id="f9d30-128">WAS 활성화 WCF 서비스 구축에 대한 자세한 지침은 [WAS에서 WCF 서비스 호스트](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)방법을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9d30-128">For detailed instructions about building a WAS-activated WCF service, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d30-129">참조</span><span class="sxs-lookup"><span data-stu-id="f9d30-129">See also</span></span>

- [<span data-ttu-id="f9d30-130">Windows Process Activation Service에서의 호스팅</span><span class="sxs-lookup"><span data-stu-id="f9d30-130">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)
- <span data-ttu-id="f9d30-131">[Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f9d30-131">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
