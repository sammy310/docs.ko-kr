---
title: 'Windows Communication Foundation 채택에 대한 기대: 향후 마이그레이션 간소화'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: b43f509bd49ebe89d7ed0be4c37b3ed179aaeb8c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576501"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Windows Communication Foundation 채택에 대한 기대: 향후 마이그레이션 간소화
새 ASP.NET 응용 프로그램을 WCF로 더 쉽게 마이그레이션하려면 앞의 권장 사항과 다음 권장 사항을 따르세요.  
  
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
  
 WCF는 다른 끝점을 사용 하기 위해 SOAP 1.1 및 SOAP 1.2과 같은 다양 한 프로토콜에 맞는 메시지를 필요로 하기 때문에 권장 됩니다. ASP.NET 2.0 웹 서비스가 기본 구성 인 SOAP 1.1 및 SOAP 1.2을 모두 지원 하도록 구성 된 경우 모든 ASP.NET 웹 서비스의 기존 클라이언트와 호환 되는 원래 주소에서 단일 WCF 끝점으로 마이그레이션할 수 없습니다. 또한 SOAP 1.1 대신 1.2를 선택하면 서비스의 클라이언트가 보다 엄격하게 제한됩니다.  
  
## <a name="service-development"></a>서비스 개발  
 WCF를 사용 하면 인터페이스 또는 클래스에를 적용 하 여 서비스 계약을 정의할 수 있습니다 <xref:System.ServiceModel.ServiceContractAttribute> . 이 특성을 인터페이스에 적용하면 원하는 수의 클래스에서 다양하게 구현할 수 있는 계약의 정의가 생성되므로 클래스보다는 인터페이스에 적용하는 것이 좋습니다. ASP.NET 2.0은 클래스뿐만 아니라 인터페이스에도 <xref:System.Web.Services.WebService> 특성을 적용하는 옵션을 지원합니다. 그러나 이미 설명했듯이 ASP.NET 2.0에는 <xref:System.Web.Services.WebService> 특성이 클래스가 아닌 인터페이스에 적용될 경우 이 특성의 Namespace 매개 변수가 아무런 효과가 없다는 결점이 있습니다. 일반적으로 특성의 Namespace 매개 변수를 사용 하 여 서비스의 네임 스페이스를 기본값에서 수정 하는 것이 좋습니다 `http://tempuri.org` <xref:System.Web.Services.WebService> <xref:System.ServiceModel.ServiceContractAttribute> . 인터페이스 또는 클래스에 특성을 적용 하 여 ASP.NET 웹 서비스를 계속 정의 해야 합니다.  
  
- 이러한 인터페이스를 정의하는 메서드에 코드를 가능한 한 적게 사용합니다. 메서드의 작업을 다른 클래스에 위임하도록 합니다. 그러면 새 WCF 서비스 형식이 해당 클래스에 시키며 관리가 작업을 위임할 수도 있습니다.  
  
- `MessageName`의 <xref:System.Web.Services.WebMethodAttribute> 매개 변수를 사용하여 서비스 작업에 명시적 이름을 제공합니다.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     ASP.NET의 작업에 대 한 기본 이름이 WCF에서 제공 하는 기본 이름과 다르기 때문에이 작업을 수행 하는 것이 중요 합니다. 명시적 이름을 제공함으로써 기본 이름을 사용하지 않아도 됩니다.  
  
- WCF는 다형성 메서드로 작업을 구현 하는 작업을 지원 하지 않기 때문에 다형 메서드를 사용 하 여 ASP.NET 웹 서비스 작업을 구현 하지 마십시오.  
  
- <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>를 사용하여 HTTP 요청을 메서드로 라우트할 SOAPAction HTTP 헤더에 명시적 값을 제공합니다.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     이 방법을 사용 하면 ASP.NET 및 WCF에서 사용 되는 기본 SOAPAction 값을 사용 하지 않아도 됩니다.  
  
- SOAP 확장을 사용하지 마세요. SOAP 확장이 필요한 경우 해당 항목이 고려 되 고 있는 목적이 이미 WCF에서 제공 하는 기능 인지 여부를 확인 합니다. 실제로이 경우 WCF를 즉시 채택 하지 않도록 선택 합니다.  
  
## <a name="state-management"></a>상태 관리  
 서비스의 상태를 유지하지 마세요. 상태를 유지 관리 하는 것은 응용 프로그램의 확장성을 손상 시키는 경향이 있지만 ASP.NET 및 WCF의 상태 관리 메커니즘은 매우 다릅니다. 하지만 WCF는 ASP.NET 호환 모드에서 ASP.NET 메커니즘을 지원 합니다.  
  
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
  
 이러한 예외 클래스는 WCF 클래스에서 쉽게 다시 사용할 수 있습니다. <xref:System.ServiceModel.FaultException%601>`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>보안  
 다음은 몇 가지 보안 권장 사항입니다.  
  
- ASP.NET 2.0 프로필을 사용 하지 마세요 .이 프로필을 사용 하면 서비스가 WCF로 마이그레이션된 경우 ASP.NET 통합 모드의 사용이 제한 됩니다.  
  
- ASP.NET 웹 서비스는 iis (인터넷 정보 서비스)를 사용 하 여 Acl을 지원 하므로 WCF는 그렇지 않습니다. ASP.NET 웹 서비스는 호스팅을 위해 IIS에 의존 하 고 WCF는 IIS에서 호스팅될 필요가 없기 때문에 서비스에 대 한 액세스를 제어 하기 위해 Acl을 사용 하지 않습니다.  
  
- 서비스 리소스에 대한 액세스 권한을 부여할 때 ASP.NET 2.0 역할 공급자를 사용할 것을 고려해 보세요.  
  
## <a name="see-also"></a>참고 항목

- [Windows Communication Foundation 채택에 대한 기대: 향후 통합 간소화](anticipating-adopting-the-wcf-easing-future-integration.md)
