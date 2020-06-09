---
title: 중간 계층 클라이언트 애플리케이션
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: c50223a55765f211dae710f96bffa7716ce36b32
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598816"
---
# <a name="middle-tier-client-applications"></a>중간 계층 클라이언트 애플리케이션
이 항목에서는 WCF (Windows Communication Foundation)를 사용 하는 중간 계층 클라이언트 응용 프로그램과 관련 된 다양 한 문제에 대해 설명 합니다.  
  
## <a name="increasing-middle-tier-client-performance"></a>중간 계층 클라이언트 성능 향상  
 ASP.NET를 사용 하는 웹 서비스와 같은 이전 통신 기술에 비해 wcf 클라이언트 인스턴스 생성은 다양 한 WCF 기능 집합으로 인해 더 복잡할 수 있습니다. 예를 들어, <xref:System.ServiceModel.ChannelFactory%601> 개체가 열릴 때 클라이언트 인스턴스에 대한 시작 시간을 늘리는 절차인 서비스를 사용하여 보안 세션을 설정할 수 있습니다. 일반적으로 이러한 추가 기능 기능은 WCF 클라이언트에서 여러 번의 호출을 수행 하므로 클라이언트 응용 프로그램에 영향을 주지 않으며,이를 닫습니다.  
  
 그러나 중간 계층 클라이언트 응용 프로그램에서는 많은 WCF 클라이언트 개체를 신속 하 게 만들 수 있으며, 결과적으로 초기화 요구 사항이 증가 합니다. 서비스를 호출할 때 중간 계층 애플리케이션의 성능을 향상시키는 두 가지 기본적인 방법이 있습니다.  
  
- WCF 클라이언트 개체를 캐시 하 고 가능한 경우 후속 호출에 다시 사용 합니다.  
  
- 개체를 만든 <xref:System.ServiceModel.ChannelFactory%601> 다음 해당 개체를 사용 하 여 각 호출에 대 한 새 WCF 클라이언트 채널 개체를 만듭니다.  
  
 이러한 방법을 사용할 때 고려해야 할 문제는 다음과 같습니다.  
  
- 서비스에서 세션을 사용 하 여 클라이언트 관련 상태를 유지 관리 하는 경우 서비스의 상태가 중간 계층 클라이언트의 상태와 연결 되어 있기 때문에 다중 클라이언트 계층 요청에서 중간 계층 WCF 클라이언트를 다시 사용할 수 없습니다.  
  
- 서비스가 클라이언트 단위로 인증을 수행 해야 하는 경우 WCF 클라이언트 (또는)를 만든 후 중간 계층의 클라이언트 자격 증명을 수정할 수 없기 때문에 중간 계층의 들어오는 각 요청에 대해 중간 계층의 들어오는 각 요청에 대해 새 클라이언트를 만들어야 합니다 <xref:System.ServiceModel.ChannelFactory%601> .  
  
- 채널과 채널에서 만든 클라이언트는 스레드로부터 안전하므로 네트워크에서 동시에 여러 메시지 쓰기를 지원하지 않을 수 있습니다. 큰 메시지를 보낼 경우, 특히 스트리밍할 경우에는 다른 보내기 작업이 완료되는 동안 보내기 작업이 차단될 수 있습니다. 따라서 채널을 재사용하여 제어의 흐름이 서비스로 반환될 경우 즉, 코드 경로에서 공유 클라이언트에 대한 콜백을 생성하는 서비스를 공유 클라이언트가 호출할 경우 동시성 결여 및 교착 상태의 두 가지 문제가 발생할 수 있습니다. 이는 다시 사용 하는 WCF 클라이언트의 형식에 관계 없이 적용 됩니다.  
  
- 채널을 공유하는지 여부에 관계없이 오류가 발생한 채널을 처리해야 합니다. 그러나 채널을 다시 사용할 경우 오류 채널에서 대기 중인 여러 요청 또는 보내기를 종료할 수 있습니다.  
  
 여러 요청에 대해 클라이언트를 재사용 하는 모범 사례를 보여 주는 예제는 [ASP.NET 클라이언트의 데이터 바인딩](../samples/data-binding-in-an-aspnet-client.md)을 참조 하세요.  
  
 또한 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize할 수 있는 데이터 형식을 사용하는 클라이언트가 런타임에 해당 데이터 형식에 대한 serialization 코드를 생성하고 컴파일할 때 시작 성능이 저하될 수 있습니다. 이 시작 성능을 향상시킬 수 있습니다. [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 는 응용 프로그램에 대해 컴파일된 어셈블리에서 필요한 serialization 코드를 생성 하 여 이러한 응용 프로그램의 시작 성능을 향상 시킬 수 있습니다. 자세한 내용은 [방법: XmlSerializer를 사용 하 여 WCF 클라이언트 응용 프로그램의 시작 시간 향상](startup-time-of-wcf-client-applications-using-the-xmlserializer.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [WCF 클라이언트를 사용하여 서비스 액세스](accessing-services-using-a-client.md)
