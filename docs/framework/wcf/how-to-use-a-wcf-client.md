---
title: '자습서: Windows 통신 파운데이션 클라이언트 사용'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184020"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>자습서: Windows 통신 파운데이션 클라이언트 사용

이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 마지막 에 대해 설명합니다. 자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.

WCF(Windows 통신 재단) 프록시를 만들고 구성한 후 클라이언트 인스턴스를 만들고 클라이언트 응용 프로그램을 컴파일합니다. 그런 다음 WCF 서비스와 통신하는 데 사용합니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - WCF 클라이언트를 사용할 코드를 추가합니다.
> - WCF 클라이언트를 테스트합니다.

## <a name="add-code-to-use-the-wcf-client"></a>WCF 클라이언트를 사용할 코드 추가

클라이언트 코드는 다음 단계를 수행합니다.

- WCF 클라이언트를 인스턴스화합니다.
- 생성된 프록시에서 서비스 작업 호출
- 작업 호출이 완료된 후 클라이언트를 닫습니다.

**GettingStartedClient** 프로젝트에서 **Program.cs** 또는 **Module1.vb** 파일을 열고 코드를 다음 코드로 바꿉니다.

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

`using` (Visual C#) 또는 `Imports` (Visual Basic) 문을 가져오는 지 확인합니다. `GettingStartedClient.ServiceReference1` 이 문은 Visual Studio에서 서비스 참조 추가 기능을 통해 생성한 코드를 가져오고 **있습니다.** 코드는 WCF 프록시를 인스턴스화하고 계산기 서비스가 노출하는 각 서비스 작업을 호출합니다. 그런 다음 프록시를 닫고 프로그램을 종료합니다.

## <a name="test-the-wcf-client"></a>WCF 클라이언트 테스트

### <a name="test-the-application-from-visual-studio"></a>비주얼 스튜디오에서 응용 프로그램 테스트

1. 솔루션을 저장하고 빌드합니다.

2. **GettingStartedLib** 폴더를 선택한 다음 바로 가기 메뉴에서 **시작 프로젝트로 설정을** 선택합니다.

3. **시작 프로젝트에서**드롭다운 목록에서 **GettingStartedLib을** 선택한 다음 **실행** 또는 **F5를**누릅니다.

### <a name="test-the-application-from-a-command-prompt"></a>명령 프롬프트에서 응용 프로그램 테스트

1. 관리자로 명령 프롬프트를 열고 Visual Studio 솔루션 디렉터리로 이동합니다.

2. 서비스를 시작하려면: *GettingStartedHost\bin\디버그\GettingStartedHost.exe*를 입력합니다.

3. 클라이언트를 시작하려면: 다른 명령 프롬프트를 열고 Visual Studio 솔루션 디렉터리로 이동한 다음 *GettingStartedClient\bin\Debug\GettingStartedClient.exe를*입력합니다.

   *GettingStartedHost.exe는* 다음과 같은 출력을 생성합니다.

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

   *GettingStartedClient.exe는* 다음 출력을 생성합니다.

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>다음 단계

이제 WCF의 모든 작업을 완료했습니다 시작 자습서. 이 자습서에서는 다음 작업 방법을 알아보았습니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - WCF 클라이언트를 사용할 코드를 추가합니다.
> - WCF 클라이언트를 테스트합니다.

단계에 문제가 있거나 오류가 있는 경우 문제 해결 문서의 단계를 수행하여 문제를 해결합니다.

> [!div class="nextstepaction"]
> [WCF 자습서 시작 문제 해결](troubleshooting-the-getting-started-tutorial.md)
