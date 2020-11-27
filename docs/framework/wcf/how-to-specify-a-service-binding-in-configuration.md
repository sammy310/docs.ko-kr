---
title: '방법: 구성에서 서비스 바인딩 지정'
description: 구성 파일에서 WCF 서비스에 대 한 끝점을 구성 하는 방법에 대해 알아봅니다. 계약은 서비스에 대해 정의 되 고 클래스에서 구현 됩니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 06b1cd009d28f854ec73286efa29d42f0f557314
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293691"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="d540a-104">방법: 구성에서 서비스 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="d540a-104">How to: Specify a Service Binding in Configuration</span></span>

<span data-ttu-id="d540a-105">이 예제에서 `ICalculator` 계약이 기본 계산기 서비스에 대해 정의되고, 서비스가 `CalculatorService` 클래스에 구현된 다음 해당 엔드포인트가 Web.config 파일에 구성됩니다. 여기서 서비스는 <xref:System.ServiceModel.BasicHttpBinding>을 사용하는 것으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-105">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="d540a-106">구성 대신 코드를 사용 하 여이 서비스를 구성 하는 방법에 대 한 자세한 내용은 [방법: 코드에서 서비스 바인딩 지정](how-to-specify-a-service-binding-in-code.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d540a-106">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="d540a-107">일반적으로 바인딩 및 주소 정보를 코드에서 명령적으로 지정하지 않고 구성에서 선언적으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-107">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="d540a-108">일반적으로 배포 된 서비스에 대 한 바인딩 및 주소가 서비스를 개발 하는 동안 사용 된 것과 다르기 때문에 일반적으로 코드에서 끝점을 정의 하는 것은 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-108">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="d540a-109">일반적으로 바인딩 및 주소 지정 정보를 코드와 구분하면 애플리케이션을 다시 컴파일하거나 다시 배포할 필요 없이 해당 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-109">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="d540a-110">[구성 편집기 도구 (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)를 사용 하 여 다음 구성 단계를 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-110">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="d540a-111">이 예제의 소스 복사에 대해서는 [Basicbinding](./samples/basicbinding.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d540a-111">For the source copy of this example, see [BasicBinding](./samples/basicbinding.md).</span></span>  
  
## <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="d540a-112">서비스를 구성하는 데 사용할 BasicHttpBinding을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="d540a-112">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1. <span data-ttu-id="d540a-113">서비스 유형에 대한 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-113">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="d540a-114">서비스 클래스에 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-114">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="d540a-115">주소 또는 바인딩 정보는 서비스 구현 내에 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-115">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="d540a-116">또한 구성 파일에서 해당 정보를 가져오기 위해 코드를 쓰지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-116">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3. <span data-ttu-id="d540a-117">Web.config 파일을 만들어 `CalculatorService`을 사용하는 <xref:System.ServiceModel.WSHttpBinding>에 대한 엔드포인트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-117">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  

            <!-- Leave the address blank to be populated by default -->
            <!-- from the hosting environment,in this case IIS, so -->
            <!-- the address will just be that of the IIS Virtual -->
            <!-- Directory. -->

            <!-- Specify the binding configuration name for that -->
            <!-- binding type. This is optional but useful if you -->
            <!-- want to modify the properties of the binding. -->
            <!-- The bindingConfiguration name Binding1 is defined -->
            <!-- below in the bindings element. -->
            <endpoint
                address=""
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="d540a-118">다음 줄이 포함된 Service.svc 파일을 만든 다음 IIS(인터넷 정보 서비스) 가상 디렉터리에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-118">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```aspx-csharp
    <%@ServiceHost language=c# Service="CalculatorService" %>
    ```  
  
## <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="d540a-119">바인딩 속성의 기본값을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d540a-119">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="d540a-120">의 기본 속성 값 중 하나를 수정 하려면 <xref:System.ServiceModel.WSHttpBinding> 요소 내에 새 바인딩 구성 이름을 만들고 `<binding name="Binding1">` [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) 이 바인딩 요소에서 바인딩의 특성에 대해 새 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-120">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="d540a-121">예를 들어 기본 열기 및 닫기 시간 제한 값을 1분에서 2분으로 변경하려면 구성 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d540a-121">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d540a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d540a-122">See also</span></span>

- [<span data-ttu-id="d540a-123">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d540a-123">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d540a-124">엔드포인트 주소 지정</span><span class="sxs-lookup"><span data-stu-id="d540a-124">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
