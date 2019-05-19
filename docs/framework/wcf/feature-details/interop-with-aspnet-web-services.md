---
title: ASP.NET 웹 서비스와의 상호 운용성
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: c1b027eda315a76778e772235dc5f66e03c9d83e
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65875543"
---
# <a name="interoperability-with-aspnet-web-services"></a>ASP.NET 웹 서비스와의 상호 운용성
Windows Communication Foundation (WCF) 웹 서비스와 ASP.NET 웹 서비스 간의 상호 운용성 두 기술을 사용 하 여 구현 된 서비스는 WS에 따르는지 확인 하 여 수행할 수 있습니다-Basic Profile 1.1 사양입니다. WS 따르는 ASP.NET 웹 서비스-는 WCF 시스템 제공 바인딩을 사용 하 여 WCF 클라이언트와 상호 운용 가능한 Basic Profile 1.1 <xref:System.ServiceModel.BasicHttpBinding>합니다.  
  
 다음 예제 코드에 표시된 것처럼 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 및 <xref:System.Web.Services.WebService> 특성을 클래스가 아니라 인터페이스에 추가하고 클래스를 기록하는 <xref:System.Web.Services.WebMethodAttribute> 옵션을 사용하여 인터페이스를 구현합니다.  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <xref:System.Web.Services.WebService> 특성을 가진 인터페이스는 서비스에 의해 수행되는 작업에 대한 계약을 구성하며, 같은 계약을 다른 방식으로 구현하는 다양한 클래스에서 이 서비스를 다시 사용할 수 있으므로 이 옵션을 사용하는 것이 좋습니다.  
  
 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 `SOAPAction` 특성을 사용하지 마십시오. WCF를 사용 하는 `SOAPAction` 메시지 라우팅에 대 한 HTTP 헤더입니다.  
  
 <xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다. 도입 WCF에 대비 하 여에서 ASP.NETWeb 서비스 사용에 대 한 데이터 형식을 정의 하는 경우 다음을 수행 합니다.  
  
- XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.  
  
- 클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다. .NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.  
  
- 이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다. ASP.NET 웹 서비스에서 메시지에 사용 된 유형은 처리할 수 데이터 계약으로 WCF 응용 프로그램에서 WCF 응용 프로그램에서 더 나은 성능 다른 이점과 함께 생성 합니다.  
  
 IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오. WCF 클라이언트 지원 하지 않습니다. 서비스를 보호 해야 하는 경우 이러한 옵션은 강력 하며 표준 프로토콜을 기반으로 하기 때문에 WCF에서 제공 하는 옵션을 사용 합니다.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>ServiceModel HttpModule 로드에 의한 성능 영향  
 .NET Framework 3.0의 경우 WCF `HttpModule`은 모든 ASP.NET 응용 프로그램에서 WCF를 사용할 수 있도록 루트 Web.config 파일에 설치되어 있습니다. 이는 성능에 영향을 줄 수 있기 때문에 다음 예제에서처럼 Web.config 파일에 대해 `ServiceModel`을 제거할 수 있습니다.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>참고자료

- [방법: ASP.NET 웹 서비스 클라이언트와 상호 운용 하도록 WCF 서비스 구성](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
