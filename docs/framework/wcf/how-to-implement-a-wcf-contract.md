---
title: '자습서: Windows Communication Foundation 서비스 계약 구현'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fa8c5457c636d7f37215f0d4b4fdbb1c96c9481e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929055"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="e5558-102">자습서: Windows Communication Foundation 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="e5558-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="e5558-103">이 자습서에서는 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 두 번째를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="e5558-104">자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="e5558-105">WCF 응용 프로그램을 만드는 다음 단계는 이전 단계에서 만든 WCF 서비스 인터페이스를 구현 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="e5558-106">이 단계에서는 라는 클래스를 만듭니다 `CalculatorService` 를 구현 하는 사용자 정의 `ICalculator` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="e5558-107">다음 코드에서 각 메서드는 계산기 작업을 호출 하 고 테스트 하려면 콘솔에 텍스트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="e5558-108">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="e5558-109">WCF 서비스 계약을 구현 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="e5558-110">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="e5558-111">WCF 서비스 계약을 구현 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="e5558-112">**GettingStartedLib**오픈 합니다 **Service1.cs** 또는 **Service1.vb** 파일과 해당 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="e5558-113">App.config 편집</span><span class="sxs-lookup"><span data-stu-id="e5558-113">Edit App.config</span></span>

<span data-ttu-id="e5558-114">편집할 **App.config** 에 **GettingStartedLib** 코드에 적용 된 변경 내용을 반영 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>
- <span data-ttu-id="e5558-115">시각적 개체에 대해 C# 프로젝트:</span><span class="sxs-lookup"><span data-stu-id="e5558-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="e5558-116">줄 14를 변경 합니다. `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="e5558-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="e5558-117">줄 17을 변경 합니다. `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="e5558-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="e5558-118">22 줄을 변경 합니다. `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="e5558-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="e5558-119">Visual Basic 프로젝트의 경우</span><span class="sxs-lookup"><span data-stu-id="e5558-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="e5558-120">줄 14를 변경 합니다. `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="e5558-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="e5558-121">줄 17을 변경 합니다. `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="e5558-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="e5558-122">22 줄을 변경 합니다. `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="e5558-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="e5558-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e5558-123">Compile the code</span></span>

<span data-ttu-id="e5558-124">컴파일 오류가 있는지 확인 하려면 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5558-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="e5558-125">Visual Studio를 사용 하는 경우는 **빌드합니다** 메뉴 선택 **솔루션 빌드** (누르거나 **Ctrl**+**Shift** + **B**).</span><span class="sxs-lookup"><span data-stu-id="e5558-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5558-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e5558-126">Next steps</span></span>

<span data-ttu-id="e5558-127">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="e5558-128">WCF 서비스 계약을 구현 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="e5558-129">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-129">Build the solution.</span></span>

<span data-ttu-id="e5558-130">WCF 서비스를 실행 하는 방법을 알아보려면 다음 자습서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5558-131">자습서: 호스트 및 기본 WCF 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5558-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
