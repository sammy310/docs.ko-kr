---
title: '자습서: Windows 통신 재단 서비스 계약 정의'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184088"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>자습서: Windows 통신 재단 서비스 계약 정의

이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 첫 번째 작업에 대해 설명합니다. 자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.

WCF 서비스를 만들 때 첫 번째 작업은 서비스 계약을 정의하는 것입니다. 서비스 계약은 서비스에서 지원하는 작업을 지정합니다. 작업은 웹 서비스 메서드로 간주될 수 있습니다. C# 또는 Visual Basic 인터페이스를 정의하여 서비스 계약을 만듭니다. 인터페이스에는 다음과 같은 특성이 있습니다.

- 인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다.
- 각 인터페이스에 대해 특성을 <xref:System.ServiceModel.ServiceContractAttribute> 적용해야 합니다.
- 각 작업/메서드에 대해 특성을 <xref:System.ServiceModel.OperationContractAttribute> 적용해야 합니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - **WCF 서비스 라이브러리** 프로젝트를 만듭니다.
> - 서비스 계약 인터페이스를 정의합니다.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>WCF 서비스 라이브러리 프로젝트 만들기 및 서비스 계약 인터페이스 정의

1. 관리자 권한으로 Visual Studio를 엽니다. 이렇게 하려면 **시작** 메뉴에서 Visual Studio 프로그램을 선택한 다음 바로 가기 메뉴에서**관리자로** **더 실행 을** > 선택합니다.

2. **WCF 서비스 라이브러리** 프로젝트를 만듭니다.

   1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다.

   2. 새 **프로젝트** 대화 상자왼쪽에서 **Visual C#** 또는 Visual **Basic을**확장한 다음 **WCF** 범주를 선택합니다. Visual Studio는 창의 가운데 섹션에 프로젝트 템플릿 목록을 표시합니다. **WCF 서비스 라이브러리를**선택합니다.

      > [!NOTE]
      > **WCF** 프로젝트 템플릿 범주가 표시되지 않으면 Visual Studio의 **Windows 통신 재단** 구성 요소를 설치해야 할 수 있습니다. 새 **프로젝트** 대화 상자에서 왼쪽에 있는 **시각적 스튜디오 설치 관리자 열기** 링크를 선택합니다. 개별 **구성 요소** 탭을 선택한 다음 **개발 활동** 범주에서 Windows **통신 재단을** 찾아 선택합니다. 구성 요소 설치를 시작하려면 **수정을** 선택합니다.

   3. 창의 아래쪽 섹션에서 **이름에** 대해 *시작 Lib* 을 입력하고 **솔루션 이름에**대해 *시작하기 를* 입력합니다.

   4. **확인**을 선택합니다.

      Visual Studio는 *IService1.cs(또는* Visual Basic 프로젝트의 *경우 IService1.vb),* *Service1.cs(또는* Visual Basic 프로젝트의 *Service1.vb)* 및 *App.config의*세 가지 파일이 있는 프로젝트를 만듭니다. Visual Studio는 이러한 파일을 다음과 같이 정의합니다.
      - *IService1* 파일에는 서비스 계약의 기본 정의가 포함되어 있습니다.
      - *Service1* 파일에는 서비스 계약의 기본 구현이 포함되어 있습니다.
      - *App.config* 파일에는 Visual Studio WCF 서비스 호스트 도구를 사용하여 기본 서비스를 로드하는 데 필요한 구성 정보가 포함되어 있습니다. WCF 서비스 호스트 도구에 대한 자세한 내용은 [WCF 서비스 호스트(WcfSvcHost.exe)를](wcf-service-host-wcfsvchost-exe.md)참조하십시오.

      > [!NOTE]
      > Visual Basic 개발자 환경 설정을 사용 하 고 Visual Studio를 설치 한 경우 솔루션이 숨질 수 있습니다. 이 경우 **도구** 메뉴에서 **옵션을** 선택한 다음 **옵션** 창에서 **프로젝트 및 솔루션** > **일반을** 선택합니다. **항상 솔루션 표시를**선택합니다. 또한 만들 **때 새 프로젝트 저장이** 선택되었는지 확인합니다.

3. **솔루션 탐색기에서** **IService1.cs** 또는 **IService1.vb** 파일을 열고 해당 코드를 다음 코드로 바꿉니다.

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     이 계약은 온라인 계약을 정의합니다. 인터페이스가 `ICalculator` <xref:System.ServiceModel.ServiceContractAttribute> 특성(단순화)으로 `ServiceContract`표시됩니다. 이 특성은 계약 이름을 모호하게 하는 네임스페이스를 정의합니다. 코드는 각 계산기 작업을 <xref:System.ServiceModel.OperationContractAttribute> 특성(단순화)으로 `OperationContract`표시합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 작업 방법을 알아보았습니다.
> [!div class="checklist"]
>
> - WCF 서비스 라이브러리 프로젝트를 만듭니다.
> - 서비스 계약 인터페이스를 정의합니다.

WCF 서비스 계약을 구현하는 방법을 알아보려면 다음 자습서로 이동합니다.

> [!div class="nextstepaction"]
> [자습서: WCF 서비스 계약 구현](how-to-implement-a-wcf-contract.md)
