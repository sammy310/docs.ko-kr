---
title: 클라이언트 동작 구성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 83fdc77bd17115f9952f2ca6c494ed0eb873cd9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608777"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="4d06a-102">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="4d06a-102">Configuring Client Behaviors</span></span>
<span data-ttu-id="4d06a-103">두 가지 방법으로 동작을 구성 하는 Windows Communication Foundation (WCF):에 정의 된 동작 구성을 참조 하거나는 `<behavior>` 또는 프로그래밍 방식으로 호출을 클라이언트 응용 프로그램 구성 파일의 섹션 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-103">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="4d06a-104">이 항목에서는 두 접근 방식 모두에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="4d06a-105">구성 파일을 사용할 경우 동작 구성은 구성 설정의 명명된 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="4d06a-106">각 동작 구성의 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="4d06a-107">이 문자열은 엔드포인트를 동작에 연결하는 엔드포인트 구성의 `behaviorConfiguration` 특성에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d06a-108">예제</span><span class="sxs-lookup"><span data-stu-id="4d06a-108">Example</span></span>  
 <span data-ttu-id="4d06a-109">다음 구성 코드에서는 `myBehavior`라는 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="4d06a-110">클라이언트 엔드포인트는 `behaviorConfiguration` 특성에서 이 동작을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="4d06a-111">프로그래밍 방식으로 동작 사용</span><span class="sxs-lookup"><span data-stu-id="4d06a-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="4d06a-112">또한 구성 하거나 적절 한 배치 하 여 동작을 프로그래밍 방식으로 삽입 `Behaviors` Windows Communication Foundation (WCF) 클라이언트 개체 또는 클라이언트를 열기 전에 클라이언트 채널 팩터리 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d06a-113">예제</span><span class="sxs-lookup"><span data-stu-id="4d06a-113">Example</span></span>  
 <span data-ttu-id="4d06a-114">다음 코드 예제에서는 채널 개체를 만들기 전에 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 속성에서 반환된 <xref:System.ServiceModel.Description.ServiceEndpoint>의 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 속성에 액세스하여 프로그래밍 방식으로 동작을 삽입하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d06a-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="4d06a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4d06a-115">See also</span></span>

- [<span data-ttu-id="4d06a-116">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4d06a-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
