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
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="07ff9-102">자습서: Windows 통신 재단 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="07ff9-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="07ff9-103">이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 두 번째 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="07ff9-104">자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.</span><span class="sxs-lookup"><span data-stu-id="07ff9-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="07ff9-105">WCF 응용 프로그램을 만드는 다음 단계는 이전 단계에서 만든 WCF 서비스 인터페이스를 구현하는 코드를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="07ff9-106">이 단계에서는 사용자 정의 `CalculatorService` `ICalculator` 인터페이스를 구현하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="07ff9-107">다음 코드의 각 메서드는 계산기 작업을 호출하고 콘솔에 텍스트를 사용하여 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="07ff9-108">이 자습서에서는 다음 작업 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="07ff9-109">WCF 서비스 계약을 구현하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="07ff9-110">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="07ff9-111">WCF 서비스 계약을 구현하는 코드 추가</span><span class="sxs-lookup"><span data-stu-id="07ff9-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="07ff9-112">**GettingStartedLib에서** **Service1.cs** 또는 **Service1.vb** 파일을 열고 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="07ff9-113">App.config 편집</span><span class="sxs-lookup"><span data-stu-id="07ff9-113">Edit App.config</span></span>

<span data-ttu-id="07ff9-114">**GettingStartedLib에서** **App.config를** 편집하여 코드에 대한 변경 사항을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="07ff9-115">비주얼 C# 프로젝트의 경우:</span><span class="sxs-lookup"><span data-stu-id="07ff9-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="07ff9-116">줄 14를 14로 변경`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="07ff9-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="07ff9-117">줄 17을 17로 변경`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="07ff9-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="07ff9-118">줄 22를 로 변경`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="07ff9-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="07ff9-119">Visual Basic 프로젝트의 경우</span><span class="sxs-lookup"><span data-stu-id="07ff9-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="07ff9-120">줄 14를 14로 변경`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="07ff9-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="07ff9-121">줄 17을 17로 변경`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="07ff9-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="07ff9-122">줄 22를 로 변경`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="07ff9-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="07ff9-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="07ff9-123">Compile the code</span></span>

<span data-ttu-id="07ff9-124">컴파일 오류가 없는지 확인 하려면 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="07ff9-125">Visual Studio를 사용하는 경우 **빌드** 메뉴에서 **솔루션 빌드(또는** **Ctrl**+**Shift**+**B)를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="07ff9-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="07ff9-126">Next steps</span></span>

<span data-ttu-id="07ff9-127">이 자습서에서는 다음 작업 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="07ff9-128">WCF 서비스 계약을 구현하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="07ff9-129">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-129">Build the solution.</span></span>

<span data-ttu-id="07ff9-130">WCF 서비스를 실행하는 방법을 알아보려면 다음 자습서로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="07ff9-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="07ff9-131">자습서: 기본 WCF 서비스 호스트 및 실행</span><span class="sxs-lookup"><span data-stu-id="07ff9-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
