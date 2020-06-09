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
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>방법: WCF 엔드포인트 및 메시지 큐 애플리케이션과 메시지 교환
Msmq 통합 바인딩을 사용 하 여 기존 메시지 큐 (MSMQ) 응용 프로그램을 wcf (Windows Communication Foundation) 응용 프로그램과 통합 하 여 msmq 메시지를 WCF 메시지와 상호 변환할 수 있습니다. 이렇게 하면 WCF 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출할 수 있을 뿐 아니라 MSMQ 발신자 응용 프로그램에서 WCF 서비스를 호출할 수 있습니다.  
  
 이 섹션에서는 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> (1) WCF 클라이언트와 (2) msmq 응용 프로그램 클라이언트 및 wcf 서비스를 사용 하 여 작성 된 msmq 응용 프로그램 서비스 간의 대기 중인 통신에를 사용 하는 방법을 설명 합니다.  
  
 WCF 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출 하는 방법을 보여 주는 전체 샘플은 [메시지 큐에 Windows Communication Foundation](../samples/wcf-to-message-queuing.md) 샘플을 참조 하세요.  
  
 MSMQ 클라이언트에서 WCF 서비스를 호출 하는 방법을 보여 주는 전체 샘플은 [메시지 큐 to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) 샘플을 참조 하세요.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>MSMQ 클라이언트로부터 메시지를 수신하는 WCF 서비스를 만들려면  
  
1. 다음 예제 코드에 표시 된 것 처럼 MSMQ 발신자 응용 프로그램에서 대기 중인 메시지를 수신 하는 WCF 서비스에 대 한 서비스 계약을 정의 하는 인터페이스를 정의 합니다.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. 다음 예제 코드에 표시된 것처럼 인터페이스를 구현하고 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 클래스에 적용합니다.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 지정하는 구성 파일을 만듭니다.  

4. 구성된 바인딩을 사용하는 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스화합니다.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>MSMQ 수신자 애플리케이션에 메시지를 보내는 WCF 클라이언트를 만들려면  
  
1. 다음 예제 코드에 표시 된 것 처럼 대기 중인 메시지를 MSMQ 수신자에 게 보내는 WCF 클라이언트에 대 한 서비스 계약을 정의 하는 인터페이스를 정의 합니다.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. WCF 클라이언트에서 MSMQ 수신기를 호출 하는 데 사용 하는 클라이언트 클래스를 정의 합니다.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. MsmqIntegrationBinding 바인딩을 사용하도록 지정하는 구성을 만듭니다.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. 클라이언트 클래스의 인스턴스를 만들고 메시지 수신 서비스에 의해 정의된 메서드를 호출합니다.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>참고 항목

- [큐 개요](queues-overview.md)
- [방법: WCF 엔드포인트와 대기 중인 메시지 교환](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Windows Communication Foundation에서 메시지 큐로](../samples/wcf-to-message-queuing.md)
- [메시지 큐(MSMQ) 설치](../samples/installing-message-queuing-msmq.md)
- [Windows Communication Foundation로 메시지 큐](../samples/message-queuing-to-wcf.md)
- [메시지 큐에 대한 메시지 보안](../samples/message-security-over-message-queuing.md)
