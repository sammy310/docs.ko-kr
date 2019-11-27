---
title: '자습서: Windows Communication Foundation 클라이언트 사용'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d0ef525db16b2b2cedeea5fa03376fb4f3489a4a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346765"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="89843-102">자습서: Windows Communication Foundation 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="89843-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="89843-103">이 자습서에서는 WCF (기본 Windows Communication Foundation) 응용 프로그램을 만드는 데 필요한 5 가지 작업 중 마지막 작업을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="89843-104">자습서에 대 한 개요는 [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89843-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="89843-105">WCF (Windows Communication Foundation) 프록시를 만들고 구성한 후 클라이언트 인스턴스를 만들고 클라이언트 응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="89843-106">그런 다음이를 사용 하 여 WCF 서비스와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-106">You then use it to communicate with the WCF service.</span></span> 

<span data-ttu-id="89843-107">이 자습서에서는 다음 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="89843-108">WCF 클라이언트를 사용 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="89843-109">WCF 클라이언트를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="89843-110">WCF 클라이언트를 사용 하는 코드 추가</span><span class="sxs-lookup"><span data-stu-id="89843-110">Add code to use the WCF client</span></span>

<span data-ttu-id="89843-111">클라이언트 코드는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-111">The client code does the following steps:</span></span>

- <span data-ttu-id="89843-112">WCF 클라이언트를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="89843-113">생성된 프록시에서 서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="89843-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="89843-114">작업 호출이 완료 된 후 클라이언트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="89843-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="89843-115">**GettingStartedClient** 프로젝트에서 **Program.cs** 또는 module1.vb 파일을 열고 해당 코드를 다음 코드로 **바꿉니다.**</span><span class="sxs-lookup"><span data-stu-id="89843-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

<span data-ttu-id="89843-116">`GettingStartedClient.ServiceReference1`를 가져오는 `using` (시각적 C#개체) 또는 `Imports` (Visual Basic) 문을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="89843-117">이 문은 **서비스 참조 추가** 함수를 사용 하 여 Visual Studio에서 생성 한 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89843-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="89843-118">이 코드는 WCF 프록시를 인스턴스화하고 계산기 서비스가 노출 하는 각 서비스 작업을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="89843-119">그런 다음 프록시를 닫고 프로그램을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="89843-120">WCF 클라이언트 테스트</span><span class="sxs-lookup"><span data-stu-id="89843-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="89843-121">Visual Studio에서 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="89843-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="89843-122">솔루션을 저장 하 고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-122">Save and build the solution.</span></span>

2. <span data-ttu-id="89843-123">**GettingStartedLib** 폴더를 선택 하 고 바로 가기 메뉴에서 **시작 프로젝트로 설정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="89843-124">**시작 프로젝트**의 드롭다운 목록 **에서 GettingStartedLib** 를 선택 하 고 **실행** 을 선택 하거나 **f5**키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="89843-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="89843-125">명령 프롬프트에서 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="89843-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="89843-126">관리자 권한으로 명령 프롬프트를 연 다음 Visual Studio 솔루션 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span> 

2. <span data-ttu-id="89843-127">서비스를 시작 하려면: *GettingStartedHost\bin\Debug\GettingStartedHost.exe*을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="89843-128">클라이언트를 시작 하려면: 다른 명령 프롬프트를 열고 Visual Studio 솔루션 디렉터리로 이동한 다음 *GettingStartedClient\bin\Debug\GettingStartedClient.exe*를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="89843-129">*GettingStartedHost* 는 다음과 같은 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-129">*GettingStartedHost.exe* produces the following output:</span></span>

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   <span data-ttu-id="89843-130">*GettingStartedClient* 는 다음과 같은 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="89843-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="89843-131">Next steps</span></span>

<span data-ttu-id="89843-132">이제 WCF 시작 자습서의 모든 작업을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89843-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="89843-133">이 자습서에서는 다음 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="89843-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="89843-134">이 자습서에서는 다음 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="89843-135">WCF 클라이언트를 사용 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="89843-136">WCF 클라이언트를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-136">Test the WCF client.</span></span>

<span data-ttu-id="89843-137">모든 단계에서 문제나 오류가 발생 한 경우 문제 해결 문서의 단계를 수행 하 여 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="89843-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="89843-138">WCF 시작 자습서 문제 해결</span><span class="sxs-lookup"><span data-stu-id="89843-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
