---
title: PII 보안 잠금
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: ad4f4a024b04a028b815faedded58713e001cab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144268"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="bd8ba-102">PII 보안 잠금</span><span class="sxs-lookup"><span data-stu-id="bd8ba-102">PII Security Lockdown</span></span>
<span data-ttu-id="bd8ba-103">이 샘플에서는 WCF(Windows 통신 재단) 서비스의 여러 보안 관련 기능을 다음과 같은 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
- <span data-ttu-id="bd8ba-104">서비스의 구성 파일에서 중요한 정보 암호화</span><span class="sxs-lookup"><span data-stu-id="bd8ba-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
- <span data-ttu-id="bd8ba-105">중첩된 서비스 하위 디렉터리에서 설정을 재정의할 수 없도록 구성 파일에서 요소 잠금</span><span class="sxs-lookup"><span data-stu-id="bd8ba-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
- <span data-ttu-id="bd8ba-106">추적 및 메시지 로그에서 PII(개인적으로 식별할 수 있는 정보)의 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="bd8ba-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bd8ba-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bd8ba-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bd8ba-109">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bd8ba-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="bd8ba-111">토론</span><span class="sxs-lookup"><span data-stu-id="bd8ba-111">Discussion</span></span>  
 <span data-ttu-id="bd8ba-112">이러한 각 기능을 별개로 사용하거나 함께 사용하여 서비스 보안의 여러 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="bd8ba-113">이것은 WCF 서비스 보안에 대한 확실한 가이드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="bd8ba-114">.NET Framework는 데이터베이스에 연결하기 위한 연결 문자열과 같은 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="bd8ba-115">공유된 웹 호스팅 시나리오에서는 서비스의 구성 파일에 포함된 데이터가 노출되지 않도록 구성 파일에서 이 정보를 암호화하는 것이 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="bd8ba-116">.NET Framework 2.0 이상에는 Windows DPAPI(데이터 보호 응용 프로그래밍 인터페이스) 또는 RSA 암호화 공급자를 사용하여 구성 파일의 일부를 암호화하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="bd8ba-117">DPAPI 또는 RSA를 사용하는 aspnet_regiis.exe는 구성 파일의 특정 부분을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="bd8ba-118">웹 호스팅 시나리오에서는 다른 서비스의 하위 디렉터리에 서비스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="bd8ba-119">구성 값을 결정하기 위한 기본 의미 체계를 사용하면 중첩된 디렉터리의 구성 파일이 부모 디렉터리의 구성 값을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="bd8ba-120">특정 상황에서는 다양한 이유로 인해 이 기능이 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="bd8ba-121">WCF 서비스 구성은 중첩된 구성이 재정의된 구성 값을 사용하여 중첩된 서비스를 실행할 때 예외를 생성할 수 있도록 구성 값 의 잠금을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="bd8ba-122">이 샘플에서는 사용자 이름 및 암호와 같은 추적 및 메시지 로그의 알려진 PII(개인적으로 식별할 수 있는 정보)의 로깅을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="bd8ba-123">기본적으로 알려진 PII의 로깅은 사용되지 않지만 특정 상황에서는 애플리케이션 디버깅을 위해 PII의 로깅이 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="bd8ba-124">이 샘플은 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-124">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="bd8ba-125">또한 이 샘플에서는 추적 및 메시지 로깅을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="bd8ba-126">자세한 내용은 추적 [및 메시지 로깅](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) 샘플을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-126">For more information, see the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="bd8ba-127">구성 파일 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="bd8ba-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="bd8ba-128">공유된 웹 호스팅 환경에서의 보안을 위해 중요한 정보가 포함된 데이터베이스 연결 문자열과 같은 특정 구성 요소를 암호화하는 것이 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="bd8ba-129">구성 요소는 .NET Framework 폴더에 있는 aspnet_regiis.exe 도구를 사용하여 암호화될 수 있습니다.예를 들어 %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="bd8ba-130">샘플의 Web.config에서 appSettings 섹션의 값을 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="bd8ba-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1. <span data-ttu-id="bd8ba-131">시작 >실행을 사용하여 명령 프롬프트를 엽니다....</span><span class="sxs-lookup"><span data-stu-id="bd8ba-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="bd8ba-132">입력하고 `cmd` **확인을**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-132">Type in `cmd` and click **OK**.</span></span>  
  
2. <span data-ttu-id="bd8ba-133">`cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728` 명령을 실행하여 현재 .NET Framework 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3. <span data-ttu-id="bd8ba-134">`aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"` 명령을 실행하여 Web.config 폴더에서 appSettings 구성 설정을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="bd8ba-135">구성 파일의 암호화 섹션에 대한 자세한 내용은 ASP.NET[구성(보안 ASP.NET 응용 프로그램 빌드: 인증, 권한 부여 및 보안 통신)에서](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))DPAPI의 방법 및 ASP.NET 구성의 RSA 사용 방법(사용 방법: RSA 사용 ASP.NET[2.0의 구성 섹션 암호화)을](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))참조하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="bd8ba-136">구성 파일 요소 잠금</span><span class="sxs-lookup"><span data-stu-id="bd8ba-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="bd8ba-137">웹 호스팅 시나리오에서는 서비스의 하위 디렉터리에 서비스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="bd8ba-138">이러한 상황에서는 Machine.config의 값을 검사한 다음 디렉터리 트리를 내려가면서 부모 디렉터리의 모든 Web.config 파일과 병합하고 마지막으로 서비스가 포함된 디렉터리의 Web.config 파일을 병합함으로써 하위 디렉터리의 서비스에 대한 구성 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="bd8ba-139">대부분의 구성 요소에서는 기본적으로 하위 디렉터리의 구성 파일이 부모 디렉터리의 값을 재정의하도록 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="bd8ba-140">그러나 특정 상황에서는 하위 디렉터리의 구성 파일이 부모 디렉터리 구성에 설정된 값을 재정의하지 못하도록 방지하는 것이 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="bd8ba-141">.NET Framework에서는 잠겨진 구성 요소를 재정의하는 구성이 런타임 예외를 throw하도록 구성 파일 요소를 잠그는 방법이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="bd8ba-142">구성 파일에서 노드에 대한 `lockItem` 특성을 지정하여 구성 요소를 잠글 수 있습니다. 예를 들어, 중첩된 구성 파일의 계산기 서비스가 동작을 변경할 수 없도록 구성 파일에서 CalculatorServiceBehavior 노드를 잠그려면 다음 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>
          <serviceBehaviors>
             <behavior name="CalculatorServiceBehavior" lockItem="true">
               <serviceMetadata httpGetEnabled="True"/>
               <serviceDebug includeExceptionDetailInFaults="False" />
             </behavior>
          </serviceBehaviors>
       </behaviors>
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="bd8ba-143">구성 요소 잠금은 더 세부적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="bd8ba-144">요소 목록을 `lockElements`에 대한 값으로 지정하여 하위 요소 컬렉션 내에서 요소 집합을 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="bd8ba-145">또한 특성 목록을 `lockAttributes`에 대한 값으로 지정하여 요소 내에서 특성 집합을 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="bd8ba-146">노드에서 `lockAllElementsExcept` 또는 `lockAllAttributesExcept` 특성을 지정하면 지정된 목록을 제외하고 요소 또는 특성의 전체 컬렉션을 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="bd8ba-147">PII 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="bd8ba-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="bd8ba-148">PII 로깅은 두 개의 스위치로 제어됩니다. 하나는 컴퓨터 관리자가 PII 로깅을 허용하거나 거부할 수 있게 하는 Machine.config에 있는 컴퓨터 수준 설정이고 다른 하나는 애플리케이션 관리자가 Web.config 또는 App.config 파일의 각 소스에 대해 PII 로깅을 설정/해제할 수 있게 하는 애플리케이션 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="bd8ba-149">컴퓨터 전체 설정은 `enableLoggingKnownPii` Machine.config의 `true` `false` `machineSettings` 요소 또는 에 설정하여 제어됩니다. 예를 들어 다음을 통해 응용 프로그램에서 PII 로깅을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="bd8ba-150">Machine.config 파일의 기본 위치는 %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG입니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="bd8ba-151">`enableLoggingKnownPii` 특성이 Machine.config에 없을 경우 PII 로깅이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="bd8ba-152">애플리케이션에 대해 PII 로깅을 사용하도록 설정하려면 Web.config 또는 App.config 파일에서 소스 요소의 `logKnownPii` 특성을 `true` 또는 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="bd8ba-153">예를 들어, 다음은 메시지 로깅 및 추적 로깅 모두에 대해 PII 로깅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>
                ...
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="bd8ba-154">`logKnownPii` 특성이 지정되지 않은 경우 PII가 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="bd8ba-155">`enableLoggingKnownPii`가 `true`로 설정되고 `logKnownPii`가 `true`로 설정된 경우에만 PII가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd8ba-156">System.Diagnostics는 구성 파일에 나열된 첫 번째 소스를 제외한 모든 소스의 모든 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="bd8ba-157">구성 파일의 두 번째 소스에 `logKnownPii` 특성을 추가해도 아무 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bd8ba-158">이 샘플을 실행하려면 Machine.config를 수동으로 수정해야 합니다. 잘못된 값이나 구문으로 Machine.config를 수정할 때 모든 .NET Framework 응용 프로그램이 실행되지 않을 수 있도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="bd8ba-159">또한 DPAPI 및 RSA를 사용하여 구성 파일 요소를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="bd8ba-160">자세한 내용은 다음 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-160">For more information, see the following links:</span></span>  
  
- <span data-ttu-id="bd8ba-161">[보안된 ASP.NET 응용 프로그램 빌드: 인증, 권한 부여 및 보안 통신](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="bd8ba-161">[Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span></span>  
  
- <span data-ttu-id="bd8ba-162">[방법: RSA를 사용하여 ASP.NET 2.0에서 구성 섹션 암호화](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="bd8ba-162">[How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bd8ba-163">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bd8ba-163">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="bd8ba-164">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bd8ba-165">필요한 경우 부모 노드가 추가되도록 Machine.config를 편집하여 `enableLoggingKnownPii` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3. <span data-ttu-id="bd8ba-166">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="bd8ba-167">단일 또는 컴퓨터 간 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="bd8ba-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="bd8ba-168">샘플을 정리하려면</span><span class="sxs-lookup"><span data-stu-id="bd8ba-168">To clean up the sample</span></span>  
  
1. <span data-ttu-id="bd8ba-169">Machine.config를 편집하여 `enableLoggingKnownPii` 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8ba-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd8ba-170">See also</span></span>

- <span data-ttu-id="bd8ba-171">[AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bd8ba-171">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
