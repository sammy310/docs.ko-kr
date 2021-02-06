---
description: '자세한 정보: Windows Communication Foundation 채택 예상: 향후 통합 속도 향상'
title: 'Windows Communication Foundation 채택에 대한 기대: 향후 통합 간소화'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: 512e35e8a4cd6057c96e96a1474f393c3f006525
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643880"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Windows Communication Foundation 채택에 대한 기대: 향후 통합 간소화

지금 ASP.NET을 사용 하 고 나중에 WCF를 사용 하는 경우이 항목에서는 새 ASP.NET 웹 서비스가 WCF 응용 프로그램과 함께 잘 작동 하도록 하는 지침을 제공 합니다.  
  
## <a name="general-recommendations"></a>일반 권장 사항  

 새로운 서비스를 위해 ASP.NET 2.0을 채택하십시오. 이렇게 하면 새 버전의 개선 사항과 향상된 내용에 접근할 수 있습니다. 그러나 동일한 응용 프로그램에서 WCF 구성 요소와 함께 ASP.NET 2.0 구성 요소를 사용할 수 있습니다.  
  
## <a name="protocols"></a>프로토콜  

 ASP.NET 2.0의 새 기능을 사용하여 WS-I Basic Profile 1.1 준수에 대한 유효성을 검사합니다.  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 WS-I Basic Profile 1.1을 준수 하는 ASP.NET 웹 서비스는 WCF 미리 정의 된 바인딩를 사용 하 여 WCF 클라이언트와 상호 운용할 수 <xref:System.ServiceModel.BasicHttpBinding> 있습니다.  
  
## <a name="service-development"></a>서비스 개발  

 SOAPAction HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 특성을 사용하지 마십시오. WCF는 메시지를 라우팅하는 데 SOAPAction HTTP 헤더를 사용 합니다.  
  
## <a name="data-representation"></a>데이터 표현  

 <xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다. ASP.NET 웹 서비스에서 사용할 데이터 형식을 정의 하는 경우 나중에 WCF를 도입 하는 것이 예상 되 면 다음을 수행 합니다.  
  
1. XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.  
  
2. 클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다. .NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.  
  
 이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다. ASP.NET 웹 서비스에 의해 메시지에 사용 되는 형식은 WCF 응용 프로그램에서 데이터 계약으로 처리 될 수 있으며,이에 따라 WCF 응용 프로그램의 성능이 향상 되는 이점이 있습니다.  
  
## <a name="security"></a>보안  

 IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오. WCF 클라이언트는 이러한 기능을 지원 하지 않습니다. 서비스의 보안을 유지 해야 하는 경우 WCF에서 제공 하는 옵션을 사용 합니다. 이러한 옵션은 더 다양 하며 표준 프로토콜을 기반으로 합니다.  
  
## <a name="see-also"></a>참고 항목

- [Windows Communication Foundation 채택에 대한 기대: 향후 마이그레이션 간소화](anticipating-adopting-wcf-migration.md)
