---
title: '방법: WCF 엔드포인트 및 메시지 큐 애플리케이션과 메시지 교환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 0775de90903aed27a8d0006614a4b6f2d857eee3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597100"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="eb361-102">방법: WCF 엔드포인트 및 메시지 큐 애플리케이션과 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="eb361-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="eb361-103">Msmq 통합 바인딩을 사용 하 여 기존 메시지 큐 (MSMQ) 응용 프로그램을 wcf (Windows Communication Foundation) 응용 프로그램과 통합 하 여 msmq 메시지를 WCF 메시지와 상호 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="eb361-104">이렇게 하면 WCF 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출할 수 있을 뿐 아니라 MSMQ 발신자 응용 프로그램에서 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="eb361-105">이 섹션에서는 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> (1) WCF 클라이언트와 (2) msmq 응용 프로그램 클라이언트 및 wcf 서비스를 사용 하 여 작성 된 msmq 응용 프로그램 서비스 간의 대기 중인 통신에를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="eb361-106">WCF 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출 하는 방법을 보여 주는 전체 샘플은 [메시지 큐에 Windows Communication Foundation](../samples/wcf-to-message-queuing.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb361-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="eb361-107">MSMQ 클라이언트에서 WCF 서비스를 호출 하는 방법을 보여 주는 전체 샘플은 [메시지 큐 to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb361-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="eb361-108">MSMQ 클라이언트로부터 메시지를 수신하는 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="eb361-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1. <span data-ttu-id="eb361-109">다음 예제 코드에 표시 된 것 처럼 MSMQ 발신자 응용 프로그램에서 대기 중인 메시지를 수신 하는 WCF 서비스에 대 한 서비스 계약을 정의 하는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. <span data-ttu-id="eb361-110">다음 예제 코드에 표시된 것처럼 인터페이스를 구현하고 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. <span data-ttu-id="eb361-111"><xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 지정하는 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  

4. <span data-ttu-id="eb361-112">구성된 바인딩을 사용하는 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="eb361-113">MSMQ 수신자 애플리케이션에 메시지를 보내는 WCF 클라이언트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="eb361-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1. <span data-ttu-id="eb361-114">다음 예제 코드에 표시 된 것 처럼 대기 중인 메시지를 MSMQ 수신자에 게 보내는 WCF 클라이언트에 대 한 서비스 계약을 정의 하는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. <span data-ttu-id="eb361-115">WCF 클라이언트에서 MSMQ 수신기를 호출 하는 데 사용 하는 클라이언트 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. <span data-ttu-id="eb361-116">MsmqIntegrationBinding 바인딩을 사용하도록 지정하는 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. <span data-ttu-id="eb361-117">클라이언트 클래스의 인스턴스를 만들고 메시지 수신 서비스에 의해 정의된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="eb361-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="eb361-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb361-118">See also</span></span>

- [<span data-ttu-id="eb361-119">큐 개요</span><span class="sxs-lookup"><span data-stu-id="eb361-119">Queues Overview</span></span>](queues-overview.md)
- [<span data-ttu-id="eb361-120">방법: WCF 엔드포인트와 대기 중인 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="eb361-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [<span data-ttu-id="eb361-121">Windows Communication Foundation에서 메시지 큐로</span><span class="sxs-lookup"><span data-stu-id="eb361-121">Windows Communication Foundation to Message Queuing</span></span>](../samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="eb361-122">메시지 큐(MSMQ) 설치</span><span class="sxs-lookup"><span data-stu-id="eb361-122">Installing Message Queuing (MSMQ)</span></span>](../samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="eb361-123">Windows Communication Foundation로 메시지 큐</span><span class="sxs-lookup"><span data-stu-id="eb361-123">Message Queuing to Windows Communication Foundation</span></span>](../samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="eb361-124">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="eb361-124">Message Security over Message Queuing</span></span>](../samples/message-security-over-message-queuing.md)
