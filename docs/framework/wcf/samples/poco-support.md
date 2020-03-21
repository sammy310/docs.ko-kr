---
title: POCO 지원
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: e94f6d9576ed96613d975a66c1965820002f94ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183421"
---
# <a name="poco-support"></a>POCO 지원
이 샘플에서는 표시되지 않은 형식, 즉 serialization 특성이 적용되지 않은 형식을 소개합니다. 이러한 형식을 POCO(Plain Old CLR Object) 형식이라고도 합니다. 매개 <xref:System.Runtime.Serialization.DataContractSerializer> 변수 없는 생성자가 있는 모든 공용 표시되지 않은 형식에 대한 데이터 계약을 추론합니다. 데이터 계약을 사용하면 서비스와 구조적 데이터를 주고 받을 수 있습니다. 표시되지 않은 형식에 대한 자세한 내용은 [Serializable 형식](../../../../docs/framework/wcf/feature-details/serializable-types.md)을 참조하십시오.  
  
 이 샘플은 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 기반으로 하지만 기본 숫자 형식 대신 복잡한 숫자를 사용합니다. <xref:System.Runtime.Serialization.DataContractAttribute> 및<xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 사용하지 않는 경우를 제외하고는 [기본 데이터 계약](../../../../docs/framework/wcf/samples/basic-data-contract.md) 샘플과도 유사합니다.  
  
 서비스는 IIS(인터넷 정보 서비스)를 통해 호스팅되고 클라이언트는 콘솔 애플리케이션(.exe)입니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 `ComplexNumber` 클래스는 `ServiceContract`에서 사용됩니다. 다음 샘플 코드에 나온 것처럼 `ComplexNumber` 형식에는 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성이 없습니다. 기본적으로 모든 public 속성과 필드가 serialize됩니다.  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3. 단일 또는 교차 컴퓨터 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md)
