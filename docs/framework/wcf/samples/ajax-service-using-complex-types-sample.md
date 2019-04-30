---
title: AJAX Service Using Complex Types 샘플
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: cde7e48d0f0c44d68266d60399ac197d322a42cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002887"
---
# <a name="ajax-service-using-complex-types-sample"></a>AJAX Service Using Complex Types 샘플
이 샘플에는 Windows Communication Foundation (WCF)를 사용 하 여 복합 형식의 인스턴스를 만들고 간에 서비스 및 클라이언트 JavaScript 개체 표기법 (JSON)으로 전송 하는 ASP.NET Asynchronous JavaScript and XML (AJAX) 서비스를 만드는 방법을 보여 줍니다. 웹 브라우저 클라이언트에서 JavaScript 코드를 사용하여 AJAX 서비스에 액세스할 수 있습니다. 이 샘플을 기반으로 합니다 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플입니다.  
  
 WCF의 AJAX 지원 ASP.NET AJAX를 통해 사용에 최적화 된는 <xref:System.Web.UI.ScriptManager> 제어 합니다. ASP.NET AJAX와 함께 WCF를 사용 하 여 예제를 참조 합니다 [AJAX 샘플](ajax.md)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 다음 샘플의 서비스는 AJAX 특정 코드가 없는 WCF 서비스. <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용되지 않으므로 기본 HTTP 동사("POST")가 사용됩니다. 서비스에는 `DoMath`라는 복합 형식을 반환하는 단일 작업인 `MathResult`가 있습니다. 복합 형식은 마찬가지로 AJAX 특정 코드가 없는 표준 데이터 계약 형식입니다.  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 엔드포인트를 만듭니다.  
  
 클라이언트 웹 페이지 ComplexTypeClientPage.aspx를 클릭할 때 서비스를 호출 하는 ASP.NET 및 JavaScript 코드를 포함 합니다 **계산을 수행할** 페이지의 단추입니다. 서비스를 호출 하는 코드는 JSON 본문을 생성 하 고 비슷한 HTTP POST를 사용 하 여 전송 합니다 [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) 샘플입니다.  
  
 서비스 호출에 성공한 후 결과 JavaScript 개체에서 개별 데이터 멤버(`sum`, `difference`, `product` 및 `quotient`)에 액세스할 수 있습니다.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2. 에 설명 된 대로 ComplexTypeAjaxService.sln 솔루션을 빌드합니다 [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
3. 이동할 `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (열지 마십시오 ComplexTypeClientPage.aspx 브라우저의 프로젝트 디렉터리에서).  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>참고자료

- [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
