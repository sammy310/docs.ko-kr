---
title: '자습서: Windows Communication Foundation 서비스 계약 정의'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228395"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>자습서: Windows Communication Foundation 서비스 계약 정의

이 자습서에서는 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 첫 번째를 설명 합니다. 자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.

WCF 서비스를 만든 경우 첫 번째 작업 서비스 계약을 정의 하는 것입니다. 서비스 계약은 서비스가 지원하는 작업을 지정합니다. 작업은 웹 서비스 메서드로 간주될 수 있습니다. 시각적 개체를 정의 하 여 서비스 계약을 만드는 C# 또는 Visual Basic (VB) 인터페이스입니다. 인터페이스에는 다음과 같은 특징이 있습니다.

- 인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다. 
- 각 인터페이스에 대해 적용 해야 합니다는 <xref:System.ServiceModel.ServiceContractAttribute> 특성입니다.
- 각 작업/메서드를 적용 해야 합니다는 <xref:System.ServiceModel.OperationContractAttribute> 특성입니다. 

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
> - 만들기는 **WCF 서비스 라이브러리** 프로젝트입니다.
> - 서비스 계약 인터페이스를 정의 합니다.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>WCF 서비스 라이브러리 프로젝트를 만들고 서비스 계약 인터페이스를 정의 합니다.

1. 관리자 권한으로 Visual Studio를 엽니다. 이렇게 하려면 Visual Studio 프로그램을 선택 합니다 **시작** 메뉴를 선택한 후 **자세한** > **관리자 권한으로 실행** 바로 가기 메뉴에서.

2. 만들기는 **WCF 서비스 라이브러리** 프로젝트입니다.

   1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다.

   2. 에 **새 프로젝트** 대화 상자의 왼쪽에서 확장 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **WCF** 범주입니다. Visual Studio 창의 가운데에 프로젝트 템플릿 목록을 표시합니다. 선택 **WCF 서비스 라이브러리**합니다.

      > [!NOTE]
      > 표시 되지 않는 경우는 **WCF** 프로젝트 템플릿 범주를 설치 해야 할 수 있습니다 합니다 **Windows Communication Foundation** Visual Studio의 구성 요소입니다. 에 **새 프로젝트** 대화 상자에서를 **Visual Studio 설치 관리자 열기** 왼쪽에 링크 합니다. 선택 합니다 **개별 구성 요소** 탭 한 다음 찾아서 선택 **Windows Communication Foundation** 아래 합니다 **개발 작업** 범주입니다. 선택할 **수정** 구성 요소 설치를 시작 합니다.

   3. 창의 아래쪽 섹션에서 입력 *GettingStartedLib* 에 대 한 합니다 **이름** 및 *GettingStarted* 에 대 한 합니다 **솔루션 이름**합니다. 

   4. **확인**을 선택합니다.

      Visual Studio에 세 개의 파일이 있는 프로젝트를 만듭니다. *IService1.cs* (또는 *IService1.vb* Visual Basic 프로젝트에 대 한), *Service1.cs* (또는 *Service1.vb* Visual Basic 프로젝트에 대 한), 및  *App.config*합니다. Visual Studio는 이러한 파일을 다음과 같이 정의합니다. 
      - 합니다 *IService1* 파일 서비스 계약의 기본 정의 포함 합니다. 
      - 합니다 *Service1* 파일에는 서비스 계약의 기본 구현이 포함 됩니다. 
      - 합니다 *App.config* 파일 Visual Studio WCF 서비스 호스트 도구를 사용 하 여 기본 서비스를 로드 하는 데 필요한 구성 정보를 포함 합니다. WCF 서비스 호스트 도구에 대 한 자세한 내용은 참조 하세요. [WCF 서비스 호스트 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)합니다.

      > [!NOTE]
      > Visual Basic 개발자 환경 설정을 사용 하 여 Visual Studio를 설치한 경우 솔루션을 숨길 수 있습니다. 이 경우 선택 **옵션** 에서 합니다 **도구** 메뉴에서 선택한 **프로젝트 및 솔루션** > **일반** 에서 합니다 **옵션** 창입니다. 선택 **솔루션 항상 표시**합니다. 또한 확인 **만들어질 때 새 프로젝트 저장** 을 선택 합니다.

3. **솔루션 탐색기**오픈 합니다 **IService1.cs** 또는 **IService1.vb** 파일과 해당 코드를 다음 코드로 바꿉니다.

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

     이 계약은 온라인 계약을 정의합니다. 알림을 `ICalculator` 으로 표시 된 인터페이스를 <xref:System.ServiceModel.ServiceContractAttribute> 특성 (으로 간소화 된 `ServiceContract`). 이 특성은 계약 이름을 명확히 구분 하는 네임 스페이스를 정의 합니다. 코드를 사용 하 여 각 계산기 작업을 표시 합니다 <xref:System.ServiceModel.OperationContractAttribute> 특성 (으로 간소화 된 `OperationContract`).

## <a name="next-steps"></a>다음 단계

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
> - WCF 서비스 라이브러리 프로젝트를 만듭니다.
> - 서비스 계약 인터페이스를 정의 합니다.

WCF 서비스 계약을 구현 하는 방법을 알아보려면 다음 자습서로 이동 합니다.

> [!div class="nextstepaction"]
> [자습서: WCF 서비스 계약 구현](how-to-implement-a-wcf-contract.md)
