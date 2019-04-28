---
title: '방법: 코드에서 서비스 엔드포인트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 65d26c0b9a41a6825108b73f822add4d91400055
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787688"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a>방법: 코드에서 서비스 엔드포인트 만들기
이 예제에서는 계산기 서비스에 대해 `ICalculator` 계약을 정의하고, `CalculatorService` 클래스에서 서비스를 구현한 다음 코드로 엔드포인트를 정의합니다. 이 때 서비스가 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용하도록 지정합니다.  
  
 일반적으로 바인딩 및 주소 정보를 코드에서 명령적으로 지정하지 않고 구성에서 선언적으로 지정하는 것이 좋습니다. 일반적으로 배포된 서비스의 바인딩과 주소가 서비스를 배포할 때 사용된 바인딩 및 주소와 다르기 때문에 코드로 엔드포인트를 정의하는 것은 효과적이지 않습니다. 일반적으로 바인딩 및 주소 지정 정보를 코드와 구분하면 응용 프로그램을 다시 컴파일하거나 다시 배포할 필요 없이 해당 정보를 변경할 수 있습니다.  
  
#### <a name="to-create-a-service-endpoint-in-code"></a>코드에서 서비스 엔드포인트를 만들려면  
  
1. 서비스 계약을 정의하는 인터페이스를 만듭니다.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. 1단계에서 정의한 서비스 계약을 구현합니다.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. 호스팅 응용 프로그램에서 서비스에 사용할 바인딩 및 서비스에 대한 기본 주소를 만듭니다.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. 호스트를 만들고, 호스트에 대한 서비스 엔드포인트를 추가할 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> 또는 다른 오버로드 중 하나를 호출합니다.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     코드에서 바인딩을 지정하되 런타임에서 제공하는 기본 엔드포인트를 사용하려면 <xref:System.ServiceModel.ServiceHost>를 만들 때 기본 주소를 생성자로 전달하고 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>를 호출하지 마세요.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     기본 끝점에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [방법: 코드에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
