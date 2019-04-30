---
title: '방법: COM+ 서비스 설정 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: dd5625fd3f2c0cc2e1e2a261b091a029cd4226ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039418"
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="cacaa-102">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="cacaa-102">How to: Configure COM+ Service Settings</span></span>
<span data-ttu-id="cacaa-103">COM+ 서비스 구성 도구를 사용하여 응용 프로그램 인터페이스를 추가하거나 제거하면 응용 프로그램의 구성 파일에서 웹 서비스 구성이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-103">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="cacaa-104">COM + 호스팅 모드에서는 Application.config 파일은 응용 프로그램 루트 디렉터리에 배치 (응용 프로그램 %PROGRAMFILES%\ComPlus\\기본값인 {appid}).</span><span class="sxs-lookup"><span data-stu-id="cacaa-104">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="cacaa-105">웹 호스팅 모드에서는 지정된 vroot 디렉터리에 Web.config 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-105">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cacaa-106">메시지 서명을 사용하여 클라이언트와 서버 사이에서 메시지가 변조되지 않도록 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-106">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="cacaa-107">또한 메시지 또는 전송 계층 암호화를 사용하여 클라이언트와 서버 간의 메시지에서 정보가 공개되지 않도록 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-107">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="cacaa-108">Windows Communication Foundation (WCF) 서비스와 마찬가지로 사용할지 제한 동시 호출 수, 연결, 인스턴스 및 보류 중인 작업 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-108">As with Windows Communication Foundation (WCF) services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="cacaa-109">이렇게 하면 리소스를 과도하게 사용하지 않도록 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-109">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="cacaa-110">스로틀 동작은 서비스 구성 파일 설정을 통해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-110">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cacaa-111">예제</span><span class="sxs-lookup"><span data-stu-id="cacaa-111">Example</span></span>  
 <span data-ttu-id="cacaa-112">다음 인터페이스를 구현하는 구성 요소를 고려해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-112">Consider a component that implements the following interface:</span></span>  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="cacaa-113">구성 요소가 웹 서비스로 노출되는 경우, 노출되어 클라이언트가 준수해야 하는 해당 서비스 계약은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-113">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```  
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="cacaa-114">IID는 계약에 대한 초기 네임스페이스의 일부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-114">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="cacaa-115">이 서비스를 사용하는 클라이언트 응용 프로그램은 이 계약을 준수함과 동시에 응용 프로그램 구성에 지정된 것과 호환되는 바인딩을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-115">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="cacaa-116">다음 코드 예제는 기본 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-116">The following code example shows a default configuration file.</span></span> <span data-ttu-id="cacaa-117">Windows Communication Foundation (WCF) 웹 서비스인이 표준 서비스 모델 구성 스키마를 준수 하 고 동일한 방식으로 다른 WCF 서비스 구성 파일에서 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-117">Being a Windows Communication Foundation (WCF) Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other WCF services configuration files.</span></span>  
  
 <span data-ttu-id="cacaa-118">대표적인 수정 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-118">Typical modifications would include:</span></span>  
  
- <span data-ttu-id="cacaa-119">엔드포인트 주소를 기본 ApplicationName/ComponentName/InterfaceName 형식에서 보다 사용이 간편한 형식으로 변경</span><span class="sxs-lookup"><span data-stu-id="cacaa-119">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
- <span data-ttu-id="cacaa-120">기본에서 서비스의 네임 스페이스 수정 `http://tempuri.org/InterfaceID` 관련성이 양식에 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-120">Modifying the namespace of the service from the default `http://tempuri.org/InterfaceID` form to a more relevant form.</span></span>  
  
- <span data-ttu-id="cacaa-121">다른 전송 바인딩을 사용하도록 엔드포인트 변경</span><span class="sxs-lookup"><span data-stu-id="cacaa-121">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="cacaa-122">COM+ 호스팅의 경우 기본적으로 명명된 파이프 전송이 사용되지만 대신 TCP 같은 시스템 외 전송을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cacaa-122">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cacaa-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="cacaa-123">See also</span></span>

- [<span data-ttu-id="cacaa-124">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="cacaa-124">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
