---
title: 'Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185467"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함
새 ASP.NET 응용 프로그램을 WCF로 더 쉽게 마이그레이션하려면 위의 권장 사항과 다음 권장 사항을 따르십시오.  
  
## <a name="protocols"></a>프로토콜  
 SOAP 1.2에 대한 ASP.NET 2.0 지원을 사용하지 않습니다.  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>
      </webServices>  
     </system.web>
</configuration>  
```  
  
 WCF는 SOAP 1.1 및 SOAP 1.2와 같은 다른 프로토콜을 준수하는 메시지가 서로 다른 끝점을 사용하려면 그렇게 하는 것이 좋습니다. ASP.NET 2.0 웹 서비스가 기본 구성인 SOAP 1.1과 SOAP 1.2를 모두 지원하도록 구성된 경우 모든 ASP.NET 웹과 호환되는 원래 주소의 단일 WCF 끝점으로 마이그레이션할 수 없습니다. 서비스의 기존 클라이언트입니다. 또한 SOAP 1.1 대신 1.2를 선택하면 서비스의 클라이언트가 보다 엄격하게 제한됩니다.  
  
## <a name="service-development"></a>서비스 개발  
 WCF를 사용하면 인터페이스 또는 클래스에 <xref:System.ServiceModel.ServiceContractAttribute> 적용하여 서비스 계약을 정의할 수 있습니다. 이 특성을 인터페이스에 적용하면 원하는 수의 클래스에서 다양하게 구현할 수 있는 계약의 정의가 생성되므로 클래스보다는 인터페이스에 적용하는 것이 좋습니다. ASP.NET 2.0은 클래스뿐만 아니라 인터페이스에도 <xref:System.Web.Services.WebService> 특성을 적용하는 옵션을 지원합니다. 그러나 이미 설명했듯이 ASP.NET 2.0에는 <xref:System.Web.Services.WebService> 특성이 클래스가 아닌 인터페이스에 적용될 경우 이 특성의 Namespace 매개 변수가 아무런 효과가 없다는 결점이 있습니다. 일반적으로 기본 ASP.NET값에서 `http://tempuri.org` <xref:System.Web.Services.WebService> <xref:System.ServiceModel.ServiceContractAttribute> 서비스의 네임스페이스를 수정하는 것이 좋습니다.  
  
- 이러한 인터페이스를 정의하는 메서드에 코드를 가능한 한 적게 사용합니다. 메서드의 작업을 다른 클래스에 위임하도록 합니다. 그런 다음 새 WCF 서비스 형식은 해당 클래스에 실질적인 작업을 위임할 수도 있습니다.  
  
- `MessageName`의 <xref:System.Web.Services.WebMethodAttribute> 매개 변수를 사용하여 서비스 작업에 명시적 이름을 제공합니다.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     ASP.NET 작업의 기본 이름은 WCF에서 제공하는 기본 이름과 다르기 때문에 이렇게 하는 것이 중요합니다. 명시적 이름을 제공함으로써 기본 이름을 사용하지 않아도 됩니다.  
  
- WCF는 다형성 방법으로 작업 구현을 지원하지 않으므로 다형성 메서드를 사용 하 ASP.NET 웹 서비스 작업을 구현 하지 마십시오.  
  
- <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>를 사용하여 HTTP 요청을 메서드로 라우트할 SOAPAction HTTP 헤더에 명시적 값을 제공합니다.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     이 방법을 사용하면 ASP.NET WCF에서 사용하는 기본 SOAPAction 값을 동일하게 사용할 필요가 없습니다.  
  
- SOAP 확장을 사용하지 마세요. SOAP 확장이 필요한 경우 고려중인 목적이 WCF에서 이미 제공한 기능인지 확인합니다. 이것이 사실이라면 WCF를 즉시 채택하지 않기로 한 선택을 재고하십시오.  
  
## <a name="state-management"></a>상태 관리  
 서비스의 상태를 유지하지 마세요. 상태를 유지 하면 응용 프로그램의 확장성이 저하 되는 경향이 있지만 ASP.NET 및 WCF의 상태 관리 메커니즘은 매우 다르지만 WCF는 ASP.NET 호환성 모드에서 ASP.NET 메커니즘을 지원합니다.  
  
## <a name="exception-handling"></a>예외 처리  
 서비스에서 보내고 받을 데이터 형식의 구조를 디자인할 때 클라이언트로 전달하려는 서비스에서 발생할 수 있는 다양한 종류의 예외를 표시하기 위한 구조도 디자인합니다.  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
        get {
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 다음과 같이 해당 클래스에 자신을 XML로 serialize할 수 있는 기능을 부여합니다.  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 그러면 해당 클래스를 사용하여 명시적으로 throw된 <xref:System.Web.Services.Protocols.SoapException> 인스턴스에 대한 자세한 정보를 제공할 수 있습니다.  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 이러한 예외 클래스는 WCF <xref:System.ServiceModel.FaultException%601> 클래스를 사용하여 새 예외 클래스를 쉽게 다시 사용할 수 있습니다.`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>보안  
 다음은 몇 가지 보안 권장 사항입니다.  
  
- 서비스가 WCF로 마이그레이션된 경우 ASP.NET ASP.NET 통합 모드의 사용을 제한하므로 ASP.NET 2.0 프로파일을 사용하지 마십시오.  
  
- ASP.NET 웹 서비스가 IIS(인터넷 정보 서비스)를 사용하여 ACL을 지원하기 ASP.NET 때문에 ACL을 사용하여 서비스에 대한 액세스를 제어하지 마십시오.  
  
- 서비스 리소스에 대한 액세스 권한을 부여할 때 ASP.NET 2.0 역할 공급자를 사용할 것을 고려해 보세요.  
  
## <a name="see-also"></a>참고 항목

- [Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
