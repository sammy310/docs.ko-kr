---
title: '자습서: Windows 통신 재단 서비스 계약 구현'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184062"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>자습서: Windows 통신 재단 서비스 계약 구현

이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 두 번째 작업을 설명합니다. 자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.

WCF 응용 프로그램을 만드는 다음 단계는 이전 단계에서 만든 WCF 서비스 인터페이스를 구현하는 코드를 추가하는 것입니다. 이 단계에서는 사용자 정의 `CalculatorService` `ICalculator` 인터페이스를 구현하는 클래스를 만듭니다. 다음 코드의 각 메서드는 계산기 작업을 호출하고 콘솔에 텍스트를 사용하여 테스트합니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - WCF 서비스 계약을 구현하는 코드를 추가합니다.
> - 솔루션을 빌드합니다.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>WCF 서비스 계약을 구현하는 코드 추가

**GettingStartedLib에서** **Service1.cs** 또는 **Service1.vb** 파일을 열고 코드를 다음 코드로 바꿉니다.

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

**GettingStartedLib에서** **App.config를** 편집하여 코드에 대한 변경 사항을 반영합니다.

- 비주얼 C# 프로젝트의 경우:
  - 줄 14를 14로 변경`<service name="GettingStartedLib.CalculatorService">`
  - 줄 17을 17로 변경`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - 줄 22를 로 변경`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Visual Basic 프로젝트의 경우
  - 줄 14를 14로 변경`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - 줄 17을 17로 변경`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - 줄 22를 로 변경`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>코드 컴파일

컴파일 오류가 없는지 확인 하려면 솔루션을 빌드합니다. Visual Studio를 사용하는 경우 **빌드** 메뉴에서 **솔루션 빌드(또는** **Ctrl**+**Shift**+**B)를**누릅니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 작업 방법을 알아보았습니다.
> [!div class="checklist"]
>
> - WCF 서비스 계약을 구현하는 코드를 추가합니다.
> - 솔루션을 빌드합니다.

WCF 서비스를 실행하는 방법을 알아보려면 다음 자습서로 이동합니다.

> [!div class="nextstepaction"]
> [자습서: 기본 WCF 서비스 호스트 및 실행](how-to-host-and-run-a-basic-wcf-service.md)
