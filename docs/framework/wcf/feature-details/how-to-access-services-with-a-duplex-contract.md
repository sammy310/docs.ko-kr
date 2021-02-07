---
description: '자세히 알아보기: 방법: 이중 계약을 사용 하 여 서비스 액세스'
title: '방법: 이중 계약을 사용 하 여 서비스 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: e58225e6b77115004c3c201d606e328aab184b75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742890"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>방법: 이중 계약을 사용 하 여 서비스 액세스

WCF (Windows Communication Foundation)의 한 가지 기능은 이중 메시징 패턴을 사용 하는 서비스를 만드는 기능입니다. 이 패턴을 사용하면 서비스에서 콜백을 통해 클라이언트와 통신할 수 있습니다. 이 항목에서는 콜백 인터페이스를 구현 하는 클라이언트 클래스에서 WCF 클라이언트를 만드는 단계를 보여 줍니다.

이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다. 클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.

기본 WCF 서비스 및 클라이언트를 만드는 방법에 대 한 자습서는 [시작 자습서](../getting-started-tutorial.md)를 참조 하세요.

## <a name="to-access-a-duplex-service"></a>이중 서비스에 액세스하려면

1. 두 인터페이스를 포함하는 서비스를 만듭니다. 첫 번째 인터페이스는 서비스에 대한 것이고 두 번째 인터페이스는 콜백에 대한 것입니다. 이중 서비스를 만드는 방법에 대 한 자세한 내용은 [방법: 이중 계약 만들기](how-to-create-a-duplex-contract.md)를 참조 하세요.

2. 서비스를 실행합니다.

3. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 클라이언트에 대 한 계약 (인터페이스)을 생성 합니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은  [방법: 클라이언트 만들기](../how-to-create-a-wcf-client.md)를 참조 하세요.

4. 다음 예제에 표시된 것처럼 클라이언트 클래스에서 콜백 인터페이스를 구현합니다.

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <xref:System.ServiceModel.InstanceContext> 클래스의 인스턴스를 만듭니다. 생성자에 클라이언트 클래스의 인스턴스가 필요합니다.

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. 개체가 필요한 생성자를 사용 하 여 WCF 클라이언트의 인스턴스를 만듭니다 <xref:System.ServiceModel.InstanceContext> . 생성자의 두 번째 매개 변수는 구성 파일에 있는 엔드포인트의 이름입니다.

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. 필요에 따라 WCF 클라이언트의 메서드를 호출 합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 이중 계약에 액세스하는 클라이언트 클래스를 만드는 방법을 보여 줍니다.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>참고 항목

- [초보자를 위한 자습서](../getting-started-tutorial.md)
- [방법: 이중 계약 만들기](how-to-create-a-duplex-contract.md)
- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [방법: 클라이언트 만들기](../how-to-create-a-wcf-client.md)
- [방법: ChannelFactory 사용](how-to-use-the-channelfactory.md)
