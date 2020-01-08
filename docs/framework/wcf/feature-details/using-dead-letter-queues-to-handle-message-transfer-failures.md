---
title: 배달 못 한 편지 큐를 사용하여 메시지 전송 오류 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9e891c6a-d960-45ea-904f-1a00e202d61a
ms.openlocfilehash: 0be22fa1e81c85d82494bc4b93468a18f05d6423
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345566"
---
# <a name="using-dead-letter-queues-to-handle-message-transfer-failures"></a>배달 못 한 편지 큐를 사용하여 메시지 전송 오류 처리
대기 중인 메시지를 배달하지 못할 수 있습니다. 이러한 실패 메시지는 배달 못 한 편지 큐에 기록됩니다. 네트워크 오류, 삭제된 큐, 꽉 찬 큐, 인증 오류 또는 정시 배달 실패와 같은 이유로 인해 배달 실패가 발생할 수 있습니다.  
  
 대기 중인 메시지는 수신 애플리케이션이 적절한 시간 내에 큐에서 메시지를 읽지 못하는 경우 오랫동안 큐에 남을 수 있습니다. 이러한 동작은 시간이 중요한 메시지에 적합하지 않을 수 있습니다. 시간이 중요한 메시지에는 대기 중인 바인딩에 설정되어 있는 TTL(Time to Live) 속성이 있으며, 이 속성은 메시지가 만료되기 전에 큐에 있을 수 있는 시간을 나타냅니다. 만료된 메시지는 배달 못한 편지 큐라는 특수 큐로 보내집니다. 또한 큐 할당량 초과 또는 인증 오류 등 다른 이유로 메시지가 배달 못 한 편지 큐에 배치될 수도 있습니다.  
  
 일반적으로 애플리케이션에서는 배달 못 한 편지 큐에서 메시지를 읽는 보정 논리 및 실패 이유를 작성합니다. 보정 논리는 실패의 원인에 따라 달라집니다. 예를 들어, 인증 오류의 경우 메시지에 첨부된 인증서를 수정하여 메시지를 다시 보낼 수 있습니다. 대상 큐 할당량을 초과하여 배달에 실패한 경우 할당량 문제가 해결되었기를 기대하며 배달을 다시 시도할 수 있습니다.  
  
 대부분의 큐 시스템에는 해당 시스템에서 실패한 모든 메시지가 저장되는 시스템 차원의 배달 못 한 편지 큐가 있습니다. 메시지 큐(MSMQ)에서는 두 개의 시스템 차원의 배달 못 한 편지 큐를 제공합니다. 하나는 트랜잭션 큐에 배달하지 못한 메시지를 저장하는 시스템 차원의 배달 못 한 트랜잭션 큐이고 다른 하나는 비트랜잭션 큐에 배달하지 못한 메시지를 저장하는 시스템 차원의 배달 못 한 비트랜잭션 큐입니다. 두 클라이언트가 서로 다른 두 서비스에 메시지를 보내는 경우 WCF의 서로 다른 큐에서 보낼 동일한 MSMQ 서비스를 공유 하는 경우 시스템 배달 못 한 편지 큐에 메시지를 혼합할 수 있습니다. 이 방법이 항상 최상은 아닙니다. 예를 들어 보안과 같이 경우에 따라 한 클라이언트가 배달 못 한 편지 큐에서 다른 클라이언트의 메시지를 읽을 수 없도록 할 수도 있습니다. 또한 공유된 배달 못 한 편지 큐에서는 클라이언트가 큐를 탐색하여 보낸 메시지를 찾도록 합니다. 이런 경우 배달 못 한 편지 큐에 있는 메시지의 수에 따라 지나치게 많은 비용이 들 수 있습니다. 따라서 WCF`NetMsmqBinding`에서 Windows Vista의 `MsmqIntegrationBinding,` 및 MSMQ는 사용자 지정 배달 못 한 편지 큐 (경우에 따라 응용 프로그램 특정 배달 못 한 편지 큐 라고도 함)를 제공 합니다.  
  
 사용자 지정 배달 못 한 편지 큐에서는 메시지를 보내는 동일한 MSMQ 서비스를 공유하는 클라이언트를 격리할 수 있습니다.  
  
 Windows Server 2003 및 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]Windows Communication Foundation (WCF)는 대기 중인 모든 클라이언트 응용 프로그램에 대해 시스템 차원의 배달 못 한 편지 큐를 제공 합니다. Windows Vista에서 WCF는 대기 중인 각 클라이언트 응용 프로그램에 대해 배달 못 한 편지 큐를 제공 합니다.  
  
## <a name="specifying-use-of-the-dead-letter-queue"></a>배달 못 한 편지 큐의 사용 지정  
 배달 못 한 편지 큐는 송신 애플리케이션의 큐 관리자에 있습니다. 이 관리자는 만료되었거나 전송 또는 배달하지 못한 메시지를 보관합니다.  
  
 바인딩에는 다음과 같은 배달 못 한 편지 큐 속성이 있습니다.  
  
- <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>  
  
- <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>  
  
## <a name="reading-messages-from-the-dead-letter-queue"></a>배달 못 한 편지 큐에서 메시지 읽기  
 배달 못 한 편지 큐에서 메시지를 읽는 응용 프로그램은 다음과 같은 사소한 차이점을 제외 하 고 응용 프로그램 큐에서 읽는 WCF 서비스와 비슷합니다.  
  
- 시스템 트랜잭션 배달 못 한 편지 큐에서 메시지를 읽으려면 URI(Uniform Resource Identifier)가 net.msmq://localhost/system$;DeadXact 형식이어야 합니다.  
  
- 배달 못 한 시스템 비트랜잭션 큐에서 메시지를 읽으려면 URI가 net.msmq://localhost/system$;DeadLetter 형식이어야 합니다.  
  
- 사용자 지정 배달 못 한 편지 큐에서 메시지를 읽으려면 URI는\< *//localhost/private/> 형식*이어야 합니다. 여기서 *custom-dlq-name* 은 사용자 지정 배달 못 한 편지 큐의 이름입니다.  
  
 큐에 주소를 지정 하는 방법에 대 한 자세한 내용은 [서비스 끝점 및 큐 주소 지정](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md)을 참조 하세요.  
  
 수신기의 WCF 스택은 서비스가 수신 대기 하는 주소와 메시지의 주소를 일치 시킵니다. 주소가 일치하면 메시지가 디스패치되고, 그렇지 않으면 메시지가 디스패치되지 않습니다. 일반적으로 배달 못 한 편지 큐에 있는 메시지는 배달 못 한 편지 큐 서비스가 아닌 서비스에 주소가 지정되기 때문에 배달 못 한 편지 큐에서 메시지를 읽을 때 문제가 발생할 수 있습니다. 따라서 배달 못 한 편지 큐에서 메시지를 읽는 서비스는 수신자와 관계없이 큐의 모든 메시지를 일치시키도록 스택에 지시하는 주소 필터 `ServiceBehavior`를 설치해야 합니다. 특히 `ServiceBehavior`를 <xref:System.ServiceModel.AddressFilterMode.Any> 매개 변수와 함께 배달 못 한 편지 큐에서 메시지를 읽는 서비스에 추가해야 합니다.  
  
## <a name="poison-message-handling-from-the-dead-letter-queue"></a>배달 못 한 편지 큐에서 포이즌 메시지 처리  
 경우에 따라 배달 못 한 편지 큐에서 포이즌 메시지 처리가 가능합니다. 시스템 큐에서 하위 큐를 만들 수 없기 때문에 배달 못 한 시스템 큐에서 메시지를 읽는 경우 `ReceiveErrorHandling`을 `Move`로 설정할 수 없습니다. 사용자 지정 배달 못 한 편지 큐에서 메시지를 읽는 경우 하위 큐를 사용할 수 있으므로 `Move`는 포이즌 메시지의 유효한 처리 방식입니다.  
  
 `ReceiveErrorHandling`이 `Reject`로 설정된 경우 사용자 지정 배달 못 한 편지 큐에서 메시지를 읽으면 포이즌 메시지가 배달 못 한 시스템 큐에 저장됩니다. 배달 못 한 시스템 큐에서 메시지를 읽는 경우 메시지가 손실/삭제됩니다. MSMQ에서 배달 못 한 시스템 큐의 거부로 인해 메시지가 손실/삭제됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 배달 못 한 편지 큐를 만드는 방법 및 이를 사용하여 만료된 메시지를 처리하는 방법을 보여 줍니다. 예제는 [방법: 대기 중인 메시지를 WCF 끝점과 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)의 예제를 기반으로 합니다. 다음 예제에서는 각 애플리케이션의 배달 못 한 편지 큐를 사용하는 주문 처리 서비스에 클라이언트 코드를 작성하는 방법을 보여 줍니다. 또한 예제에서는 배달 못 한 편지 큐에서 메시지를 처리하는 방법을 보여 줍니다.  
  
 다음은 각 애플리케이션의 배달 못 한 편지 큐를 지정하는 클라이언트의 코드입니다.  
  
 [!code-csharp[S_DeadLetter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/client.cs#1)]
 [!code-vb[S_DeadLetter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/client.vb#1)]  
  
 다음은 클라이언트 구성 파일의 코드입니다.  

 다음은 배달 못 한 편지 큐의 메시지를 처리하는 서비스의 코드입니다.  
  
 [!code-csharp[S_DeadLetter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/dlservice.cs#3)]
 [!code-vb[S_DeadLetter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/dlservice.vb#3)]  
  
 다음은 배달 못 한 편지 큐 서비스 구성 파일의 코드입니다.  

## <a name="see-also"></a>참조

- [큐 개요](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [방법: 대기 중인 메시지와 WCF 엔드포인트 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [포이즌 메시지 처리](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
