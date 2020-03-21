---
title: Impersonating the Client
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: 10a8d243b3f053879f183864e955d9260c07865b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183607"
---
# <a name="impersonating-the-client"></a><span data-ttu-id="35fb4-102">Impersonating the Client</span><span class="sxs-lookup"><span data-stu-id="35fb4-102">Impersonating the Client</span></span>
<span data-ttu-id="35fb4-103">Impersonation 샘플에서는 서비스가 호출자를 대신하여 시스템 리소스에 액세스할 수 있도록 서비스에서 호출자 애플리케이션을 가장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-103">The Impersonation sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>  
  
 <span data-ttu-id="35fb4-104">이 샘플은 [자체 호스트](../../../../docs/framework/wcf/samples/self-host.md) 샘플을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-104">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span> <span data-ttu-id="35fb4-105">서비스 및 클라이언트 구성 파일은 셀프 [호스트](../../../../docs/framework/wcf/samples/self-host.md) 샘플의 파일과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-105">The service and client configuration files are the same as that of the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35fb4-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="35fb4-107">다음 샘플 코드와 같이 서비스 코드는 `Add`를 사용하여 서비스의 <xref:System.ServiceModel.OperationBehaviorAttribute> 메서드가 호출자를 가장하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-107">The service code has been modified such that the `Add` method on the service impersonates the caller using the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="35fb4-108">결과적으로 실행 스레드의 보안 컨텍스트는 `Add` 메서드에 들어가기 전에 호출자를 가장하기 위해 전환되고 메서드 종료 시에 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-108">As a result, the security context of the executing thread is switched to impersonate the caller before entering the `Add` method and reverted on exiting the method.</span></span>  
  
 <span data-ttu-id="35fb4-109">다음 샘플 코드에 표시된 `DisplayIdentityInformation` 메서드는 호출자의 ID를 표시하는 유틸리티 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-109">The `DisplayIdentityInformation` method shown in the following sample code is a utility function that displays the caller's identity.</span></span>  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 <span data-ttu-id="35fb4-110">다음 샘플 코드와 같이 서비스의 `Subtract` 메서드는 명령적 호출을 사용하여 호출자를 가장합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-110">The `Subtract` method on the service impersonates the caller using imperative calls as shown in the following sample code.</span></span>  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs
            // on the system resource are enforced in the caller's context.
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="35fb4-111">이 경우 호출자는 전체 호출에 대해 가장되지 않고 호출의 일부에 대해서만 가장됩니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-111">Note that in this case the caller is not impersonated for the entire call but is only impersonated for a portion of the call.</span></span> <span data-ttu-id="35fb4-112">일반적으로 전체 작업에 대해 가장하는 것보다 가장 작은 범위에 대해 가장하는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-112">In general, impersonating for the smallest scope is preferable to impersonating for the entire operation.</span></span>  
  
 <span data-ttu-id="35fb4-113">다른 메서드는 호출자를 가장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-113">The other methods do not impersonate the caller.</span></span>  
  
 <span data-ttu-id="35fb4-114">클라이언트 코드는 가장 레벨을 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>으로 설정하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-114">The client code has been modified to set the impersonation level to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span></span> <span data-ttu-id="35fb4-115">클라이언트는 <xref:System.Security.Principal.TokenImpersonationLevel> 열거형을 사용하여 서비스에 사용되는 가장 레벨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-115">The client specifies the impersonation level to be used by the service, by using the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration.</span></span> <span data-ttu-id="35fb4-116">이 열거형에서는 <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> 및 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation> 값이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-116">The enumeration supports the following values: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> and <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span> <span data-ttu-id="35fb4-117">Windows ACL을 사용하여 보호되는 로컬 컴퓨터의 시스템 리소스 액세스 시에 액세스 검사를 수행하기 위해 다음 샘플 코드와 같이 가장 레벨은 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>으로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-117">To perform an access check when accessing a system resource on the local machine that is protected using Windows ACLs, the impersonation level must be set to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, as shown in the following sample code.</span></span>  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 <span data-ttu-id="35fb4-118">샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-118">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="35fb4-119">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-119">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35fb4-120">서비스는 관리 계정에서 실행되거나 HTTP 계층에 `http://localhost:8000/ServiceModelSamples` URI를 등록할 수 있는 권한이 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-120">The service must either run under an administrative account or the account it runs under must be granted rights to register the `http://localhost:8000/ServiceModelSamples` URI with the HTTP layer.</span></span> <span data-ttu-id="35fb4-121">이러한 권한은 [Httpcfg.exe 도구를](/windows/win32/http/httpcfg-exe)사용하여 [네임스페이스 예약을](/windows/win32/http/namespace-reservations-registrations-and-routing) 설정하여 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-121">Such rights can be granted by setting up a [Namespace Reservation](/windows/win32/http/namespace-reservations-registrations-and-routing) using the [Httpcfg.exe tool](/windows/win32/http/httpcfg-exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35fb4-122">Windows Server 2003을 실행하는 컴퓨터에서는 Host.exe 응용 프로그램에 가장 권한이 있는 경우에만 가장이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-122">On computers running Windows Server 2003, impersonation is supported only if the Host.exe application has the Impersonation privilege.</span></span> <span data-ttu-id="35fb4-123">(기본적으로 관리자만 이 권한이 있습니다.) 서비스가 실행 중인 계정에 이 권한을 추가하려면 **관리 도구,** **로컬 보안 정책**열기, 로컬 **정책**열기, 사용자 **권한 할당**을 클릭하고 인증 후 클라이언트 를 **가장하고** **속성을** 두 번 클릭하여 사용자 또는 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-123">(By default, only administrators have this permission.) To add this privilege to an account the service is running as, go to **Administrative Tools**, open **Local Security Policy**, open **Local Policies**, click **User Rights Assignment**, and select **Impersonate a Client after Authentication** and double-click **Properties** to add a user or group.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="35fb4-124">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="35fb4-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="35fb4-125">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="35fb4-126">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="35fb4-127">단일 또는 교차 컴퓨터 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="35fb4-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="35fb4-128">서비스가 호출자를 가장하는 것을 보기 위해 서비스가 실행 중인 계정이 아닌 다른 계정으로 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-128">To demonstrate that the service impersonates the caller, run the client under a different account than the one the service is running under.</span></span> <span data-ttu-id="35fb4-129">이렇게 하려면 명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-129">To do so, at the command prompt, type:</span></span>  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     <span data-ttu-id="35fb4-130">그런 다음 암호를 묻는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-130">You are then prompted for a password.</span></span> <span data-ttu-id="35fb4-131">이전에 지정한 계정에 대한 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-131">Enter the password for the account you previously specified.</span></span>  
  
5. <span data-ttu-id="35fb4-132">클라이언트를 다른 자격 증명으로 실행하기 전과 후의 ID에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="35fb4-132">When you run the client, note the identity before and after running it with different credentials.</span></span>  
