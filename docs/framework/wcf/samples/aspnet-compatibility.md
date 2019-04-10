---
title: ASP.NET 호환성
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 01381dc579f5ae3eadd2f913a0e09d7d259794a1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304224"
---
# <a name="aspnet-compatibility"></a>ASP.NET 호환성
이 샘플에는 Windows Communication Foundation (WCF)에서 ASP.NET 호환성 모드를 사용 하도록 설정 하는 방법을 보여 줍니다. ASP.NET 등의 기능 파일/URL 권한 부여, 세션 상태를 사용 하 여 ASP.NET 호환성 모드 ASP.NET 응용 프로그램 파이프라인에 완전히 참여 하 고 가능에서 실행 되는 서비스 및 <xref:System.Web.HttpContext> 클래스입니다. <xref:System.Web.HttpContext> 클래스에는 쿠키, 세션 및 다른 ASP.NET 기능에 액세스할 수 있습니다. 이 모드에서는 바인딩에 HTTP 전송이 사용되고 서비스 자체가 IIS에서 호스트되어야 합니다.  
  
 이 샘플에서 클라이언트는 콘솔 응용 프로그램(실행 파일)이고 서비스는 IIS(인터넷 정보 서비스)에서 호스트됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
이 샘플을 실행하려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 응용 프로그램 풀이 필요합니다. 새 응용 프로그램 풀을 만들거나 기본 응용 프로그램 풀을 수정하려면 다음 단계를 따릅니다.  

1. **제어판**을 엽니다.  열기는 **관리 도구** 애플릿 아래 합니다 **시스템 및 보안** 제목입니다. 엽니다는 **인터넷 정보 서비스 (IIS) 관리자** 애플릿을 합니다.  

2. treeview를 확장 합니다 **연결** 창입니다. 선택 된 **응용 프로그램 풀** 노드.  

3. 사용 하 여 기본 응용 프로그램 풀을 설정 하려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (기존 사이트를 사용 하 여 비 호환성 문제가 발생할 수 있는)를 마우스 오른쪽 단추로 클릭 합니다 **DefaultAppPool** 목록 항목을 선택 **기본 설정...** . 설정 된 **.NET Framework 버전** 풀다운을 **.NET Framework v4.0.30128** (또는 이상).  

4. 사용 하는 새 응용 프로그램 풀을 만들려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (호환성 유지 하기 위해 다른 응용 프로그램)를 마우스 오른쪽 단추로 클릭 합니다 **응용 프로그램 풀** 노드를 선택 **응용 프로그램 풀 추가...** . 새 응용 프로그램 풀의 이름을 지정 하 고 설정 합니다 **.NET Framework 버전** 풀다운을 **.NET Framework v4.0.30128** (또는 이상). 아래 단계는 설치 프로그램을 실행, 한 후 마우스 오른쪽 단추로 클릭 합니다 **ServiceModelSamples** 응용 프로그램 및 선택 **응용 프로그램 관리**, **고급 설정...** . 설정 된 **응용 프로그램 풀** 새 응용 프로그램 풀.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 이 샘플은 기반 합니다 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 계산기 서비스를 구현 하는 합니다. 실행 결과를 유지하면서 일련의 작업을 수행할 수 있도록 `ICalculator` 계약은 `ICalculatorSession` 계약으로 수정되었습니다.  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 계산을 수행하기 위해 여러 서비스 작업이 호출될 때 서비스는 이 기능을 사용하여 각 클라이언트에 대한 상태를 유지 관리합니다. 클라이언트는 `Result`를 호출하여 현재 결과를 검색하고 `Clear`를 호출하여 결과를 0으로 지울 수 있습니다.  
  
 서비스는 결과를 저장할 각 클라이언트 세션에 대 한 ASP.NET 세션을 사용 합니다. 따라서 서비스는 여러 서비스 호출에서 각 클라이언트에 대한 실행 결과를 유지 관리할 수 있습니다.  
  
> [!NOTE]
> ASP.NET 세션 상태 및 WCF 세션은 전혀 다릅니다. 참조 [세션](../../../../docs/framework/wcf/samples/session.md) WCF 세션에 대 한 자세한 내용은 합니다.
  
 서비스는 ASP.NET 세션 상태에 의존 있고 제대로 작동 하려면 ASP.NET 호환 모드가 필요 합니다. 이러한 요구 사항은 `AspNetCompatibilityRequirements` 특성을 적용하여 선언적으로 표현됩니다.  
  
```csharp  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```console
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 수행 해야 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3. 솔루션을 빌드한 후 Setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다. 이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.  
  
4. 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [AppFabric 호스팅 및 지속성 샘플](https://go.microsoft.com/fwlink/?LinkId=193961)
