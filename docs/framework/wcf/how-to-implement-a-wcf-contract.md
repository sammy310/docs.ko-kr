---
title: '자습서: Windows Communication Foundation 서비스 계약 구현'
description: Wcf 응용 프로그램을 만들기 시작 하는 데 도움이 되는 일련의 문서에서 WCF 서비스 인터페이스를 구현 하는 코드를 추가 하는 방법을 알아봅니다.
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 89f97610cccd42c2a5d298baa667327d077fd472
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244649"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="57d67-103">자습서: Windows Communication Foundation 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="57d67-103">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="57d67-104">이 자습서에서는 WCF (기본 Windows Communication Foundation) 응용 프로그램을 만드는 데 필요한 5 가지 작업 중 두 번째 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-104">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="57d67-105">자습서에 대 한 개요는 [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57d67-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="57d67-106">WCF 응용 프로그램을 만들기 위한 다음 단계는 이전 단계에서 만든 WCF 서비스 인터페이스를 구현 하는 코드를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-106">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="57d67-107">이 단계에서는 `CalculatorService` 사용자 정의 인터페이스를 구현 하는 라는 클래스를 만듭니다 `ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="57d67-107">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="57d67-108">다음 코드의 각 메서드는 계산기 작업을 호출 하 고 콘솔에 텍스트를 기록 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-108">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="57d67-109">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="57d67-110">WCF 서비스 계약을 구현 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-110">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="57d67-111">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-111">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="57d67-112">WCF 서비스 계약을 구현 하는 코드 추가</span><span class="sxs-lookup"><span data-stu-id="57d67-112">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="57d67-113">**GettingStartedLib**에서 **Service1.cs** 또는 **Service1 .vb** 파일을 열고 해당 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-113">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="57d67-114">편집 App.config</span><span class="sxs-lookup"><span data-stu-id="57d67-114">Edit App.config</span></span>

<span data-ttu-id="57d67-115">코드에 대 한 변경 내용을 반영 하도록 **GettingStartedLib** 에서 **App.config** 를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-115">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="57d67-116">Visual c # 프로젝트의 경우:</span><span class="sxs-lookup"><span data-stu-id="57d67-116">For Visual C# projects:</span></span>
  - <span data-ttu-id="57d67-117">줄 14를 다음으로 변경`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="57d67-117">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="57d67-118">줄 17을 다음으로 변경`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="57d67-118">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="57d67-119">줄 22를 다음으로 변경`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="57d67-119">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="57d67-120">Visual Basic 프로젝트의 경우</span><span class="sxs-lookup"><span data-stu-id="57d67-120">For Visual Basic projects:</span></span>
  - <span data-ttu-id="57d67-121">줄 14를 다음으로 변경`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="57d67-121">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="57d67-122">줄 17을 다음으로 변경`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="57d67-122">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="57d67-123">줄 22를 다음으로 변경`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="57d67-123">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="57d67-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="57d67-124">Compile the code</span></span>

<span data-ttu-id="57d67-125">솔루션을 빌드하여 컴파일 오류가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-125">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="57d67-126">Visual Studio를 사용 하는 경우 **빌드** 메뉴에서 **솔루션 빌드** 를 선택 하거나 **ctrl** + **Shift** + **B**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-126">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="57d67-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="57d67-127">Next steps</span></span>

<span data-ttu-id="57d67-128">이 자습서에서는 다음 작업 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-128">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="57d67-129">WCF 서비스 계약을 구현 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-129">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="57d67-130">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="57d67-130">Build the solution.</span></span>

<span data-ttu-id="57d67-131">다음 자습서로 이동 하 여 WCF 서비스를 실행 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="57d67-131">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="57d67-132">자습서: 기본 WCF 서비스 호스팅 및 실행</span><span class="sxs-lookup"><span data-stu-id="57d67-132">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
