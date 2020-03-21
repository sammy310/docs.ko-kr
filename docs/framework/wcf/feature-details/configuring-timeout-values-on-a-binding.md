---
title: 바인딩에 시간 제한 값 구성
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: 968e80bbd4b50d72d089a325f8e3fe498de2eac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185293"
---
# <a name="configuring-timeout-values-on-a-binding"></a>바인딩에 시간 제한 값 구성
WCF 바인딩에서 사용할 수 있는 시간 제한 설정은 여러 가지가 있습니다. 이러한 시간 제한 설정을 정확하게 설정하면 서비스 성능이 향상될 뿐만 아니라 서비스의 유용성과 보안에도 도움이 됩니다. WCF 바인딩에서 사용할 수 있는 시간 제한은 다음과 같습니다.  
  
1. OpenTimeout  
  
2. CloseTimeout  
  
3. SendTimeout  
  
4. ReceiveTimeout  
  
## <a name="wcf-binding-timeouts"></a>WCF 바인딩 시간 제한  
 이 항목에서 설명하는 각 설정은 바인딩 자체에서 코드 또는 구성으로 지정합니다. 다음 코드에서는 자체 호스트된 서비스의 컨텍스트에서 WCF 바인딩에 시간 제한을 프로그래밍 방식으로 설정하는 방법을 보여 줍니다.  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");

    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));

        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);

        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 다음 예제에서는 구성 파일에서 바인딩에 시간 제한을 구성하는 방법을 보여 줍니다.  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00"
                 closeTimeout="00:10:00"
                 sendTimeout="00:10:00"
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 이러한 설정에 대한 자세한 내용은 <xref:System.ServiceModel.Channels.Binding> 클래스 문서를 참조하세요.  
  
### <a name="client-side-timeouts"></a>클라이언트 측 시간 제한  
 클라이언트 쪽:  
  
1. SendTimeout - 요청/회신 서비스 작업의 회신 메시지 수신을 포함하여 메시지 보내기의 전체 과정을 제어하는 OperationTimeout을 초기화하는 데 사용합니다. 이 시간 제한은 콜백 계약 메서드에서 회신 메시지를 보낼 때도 적용됩니다.  
  
2. OpenTimeout - 명시적 시간 시간 지정 값이 지정되지 않은 채널을 열 때 사용됩니다.  
  
3. CloseTimeout - 명시적 시간 시간 값을 지정하지 않은 채널을 닫을 때 사용됩니다.  
  
4. 수신 시간 아웃 - 사용되지 않습니다.  
  
### <a name="service-side-timeouts"></a>서비스 측 시간 시간  
 서비스 측:  
  
1. 송신 시간, 오픈 타임아웃, 닫기 시간 아웃은 클라이언트와 동일합니다.  
  
2. ReceiveTimeout – 서비스 프레임워크 레이어에서 제한 시간 만료 전에 세션이 유휴 상태일 수 있는 시간을 제어하는 세션 유휴 시간 제한을 초기화하는 데 사용합니다.
