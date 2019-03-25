---
title: '자습서: Windows Communication Foundation 서비스 계약 구현'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fcf96af11bae701585acd92001c8000125858449
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410084"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>자습서: Windows Communication Foundation 서비스 계약 구현

이 자습서에서는 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 두 번째를 설명 합니다. 자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.

WCF 응용 프로그램을 만드는 다음 단계는 이전 단계에서 만든 WCF 서비스 인터페이스를 구현 하는 코드를 추가 합니다. 이 단계에서는 라는 클래스를 만듭니다 `CalculatorService` 를 구현 하는 사용자 정의 `ICalculator` 인터페이스입니다. 다음 코드에서 각 메서드는 계산기 작업을 호출 하 고 테스트 하려면 콘솔에 텍스트를 씁니다. 

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
> - WCF 서비스 계약을 구현 하는 코드를 추가 합니다.
> - 솔루션을 빌드합니다.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>WCF 서비스 계약을 구현 하는 코드를 추가 합니다.

**GettingStartedLib**오픈 합니다 **Service1.cs** 또는 **Service1.vb** 파일과 해당 코드를 다음 코드로 바꿉니다.

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a>App.config 편집

편집할 **App.config** 에 **GettingStartedLib** 코드에 적용 된 변경 내용을 반영 하도록 합니다.
   - 시각적 개체에 대해 C# 프로젝트:
       - 줄 14를 변경 합니다. `<service name="GettingStartedLib.CalculatorService">`
       - 줄 17을 변경 합니다. `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
       - 22 줄을 변경 합니다. `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

   - Visual Basic 프로젝트의 경우
       - 줄 14를 변경 합니다. `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
       - 줄 17을 변경 합니다. `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
       - 22 줄을 변경 합니다. `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`


## <a name="compile-the-code"></a>코드 컴파일

컴파일 오류가 있는지 확인 하려면 솔루션을 빌드하십시오. Visual Studio를 사용 하는 경우는 **빌드합니다** 메뉴 선택 **솔루션 빌드** (누르거나 **Ctrl**+**Shift** + **B**).

## <a name="next-steps"></a>다음 단계

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
> - WCF 서비스 계약을 구현 하는 코드를 추가 합니다.
> - 솔루션을 빌드합니다.

WCF 서비스를 실행 하는 방법을 알아보려면 다음 자습서로 이동 합니다.

> [!div class="nextstepaction"]
> [자습서: 호스트 및 기본 WCF 서비스를 실행 합니다.](how-to-host-and-run-a-basic-wcf-service.md)
