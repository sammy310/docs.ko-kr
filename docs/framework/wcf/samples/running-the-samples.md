---
title: Windows Communication Foundation 샘플 실행
ms.date: 03/30/2017
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
ms.openlocfilehash: f4c7a7fa759d7339dee3d189540fb85f3883f828
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594571"
---
# <a name="running-the-windows-communication-foundation-samples"></a><span data-ttu-id="eac0c-102">Windows Communication Foundation 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="eac0c-102">Running the Windows Communication Foundation Samples</span></span>
<span data-ttu-id="eac0c-103">단일 컴퓨터 또는 다중 컴퓨터 구성에서 WCF (Windows Communication Foundation) 샘플을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-103">The Windows Communication Foundation (WCF) samples can be run in a single-machine or cross-machine configuration.</span></span> <span data-ttu-id="eac0c-104">샘플은 단일 컴퓨터 구성에서 실행할 준비가 된 상태로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-104">As supplied, the samples are ready for running on a single machine.</span></span> <span data-ttu-id="eac0c-105">다중 컴퓨터 구성에서는 샘플의 구성 파일 설정을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-105">In a cross-machine configuration, it is necessary to modify a sample's configuration file settings.</span></span> <span data-ttu-id="eac0c-106">다음 절차에서는 단일 컴퓨터 및 다중 컴퓨터 구성에서 샘플을 실행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-106">The following procedures explain how to run a sample in same-machine and cross-machine configurations.</span></span> <span data-ttu-id="eac0c-107">IIS(인터넷 정보 서비스) 및 자체 호스팅 샘플에서 호스트되는 서비스에 적용되는 단계가 약간씩 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-107">Note that there are variations in the steps for services hosted in Internet Information Services (IIS) and the self-hosted samples.</span></span> <span data-ttu-id="eac0c-108">대부분의 샘플은 IIS에서 호스트됩니다. 이러한 샘플이 호스트되는 방법에 대한 자세한 내용은 샘플 추가 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eac0c-108">Most samples are hosted in IIS; see the sample readme information to determine how it is hosted.</span></span>  
  
 <span data-ttu-id="eac0c-109">Windows Vista에서 IIS에 호스트 되지 않은 샘플에는 Http.sys를 사용 하 여 수신기를 등록 하는 데 상승 된 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-109">On Windows Vista, samples that are not hosted in IIS require elevated privileges to register a listener with Http.sys.</span></span> <span data-ttu-id="eac0c-110">Httpcfg.exe를 사용하여 서비스가 수신 대기 중인 계정에 서비스의 수신 대기 주소를 등록하거나 관리자 권한으로 실행 중인 명령 프롬프트에서 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-110">Use Httpcfg.exe to register the service's listening addresses with the account the service is running under, or launch the service from a command prompt running with administrator privileges.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eac0c-111">WCF 샘플을 빌드하거나 실행 하기 전에 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-111">Before building or running any of the WCF samples, be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="eac0c-112">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="eac0c-112">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="eac0c-113">서비스가 IIS에서 호스트 되는 경우 다음 주소를 입력 하 여 브라우저를 사용 하 여 서비스에 액세스할 수 있는지 확인 `http://localhost/servicemodelsamples/service.svc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-113">If the service is hosted by IIS, ensure that you can access the service using a browser by entering the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="eac0c-114">확인 페이지가 응답으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-114">A confirmation page should be displayed in response.</span></span> <span data-ttu-id="eac0c-115">확인 페이지가 표시 되지 않으면 [WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eac0c-115">If the confirmation page is not displayed, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
2. <span data-ttu-id="eac0c-116">서비스가 자체 호스트될 경우 언어별 폴더의 \service\bin에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-116">If the service is self-hosted, run Service.exe from \service\bin, from under the language-specific folder.</span></span> <span data-ttu-id="eac0c-117">서비스 콘솔 창에 서비스 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-117">Service activity is displayed on the service console window.</span></span>  
  
3. <span data-ttu-id="eac0c-118">언어별 폴더의 \client\bin에서 setup.exe를 실행 \\ 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-118">Run Client.exe from \client\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="eac0c-119">클라이언트 콘솔 창에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-119">Client activity is displayed on the client console window.</span></span>  
  
4. <span data-ttu-id="eac0c-120">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eac0c-120">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="eac0c-121">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="eac0c-121">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="eac0c-122">서비스가 IIS에서 호스트될 경우</span><span class="sxs-lookup"><span data-stu-id="eac0c-122">If the service is hosted in IIS:</span></span>  
  
    1. <span data-ttu-id="eac0c-123">서비스 컴퓨터에서 ServiceModelSamples라는 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-123">On the service machine, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="eac0c-124">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md) 에 포함 된 배치 파일 setupvroot를 사용 하 여 디스크 디렉터리와 가상 디렉터리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-124">The batch file Setupvroot.bat included with [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) can be used to create the disk directory and virtual directory.</span></span>  
  
    2. <span data-ttu-id="eac0c-125">%SystemDrive%\Inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 ServiceModelSamples 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-125">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service machine.</span></span> <span data-ttu-id="eac0c-126">\bin 디렉터리에 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-126">Ensure that you include the files in the \bin directory.</span></span>  
  
    3. <span data-ttu-id="eac0c-127">클라이언트 컴퓨터에서 브라우저를 사용하여 서비스에 액세스할 수 있는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-127">Test that you can access the service from the client machine using a browser.</span></span>  
  
     <span data-ttu-id="eac0c-128">서비스가 자체 호스트될 경우</span><span class="sxs-lookup"><span data-stu-id="eac0c-128">If the service is self-hosted:</span></span>  
  
    1. <span data-ttu-id="eac0c-129">서비스 컴퓨터에서 서비스 파일을 포함할 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-129">On the service machine, create a directory to hold the service files.</span></span>  
  
    2. <span data-ttu-id="eac0c-130">언어별 폴더의 \service\bin\ 폴더에서 서비스 컴퓨터로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-130">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service machine.</span></span>  
  
    3. <span data-ttu-id="eac0c-131">서비스 구성 파일에서 엔드포인트 정의의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-131">In the service configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="eac0c-132">주소에서 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-132">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
    4. <span data-ttu-id="eac0c-133">명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-133">Launch Service.exe from a command prompt.</span></span>  
  
2. <span data-ttu-id="eac0c-134">언어별 폴더의 \client\bin\ 폴더에서 클라이언트 컴퓨터로 클라이언트 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-134">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
3. <span data-ttu-id="eac0c-135">엔드포인트 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-135">Set the endpoint address.</span></span>  
  
    1. <span data-ttu-id="eac0c-136">서비스가 도메인 계정으로 실행 중이 아닌 경우 클라이언트 구성 파일을 열고 엔드포인트 정의의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-136">If the service is not running under a domain account, open the client configuration file and change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="eac0c-137">주소에서 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-137">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
    2. <span data-ttu-id="eac0c-138">서비스가 도메인 계정으로 실행 중인 경우 서비스에 대해 Svcutil.exe를 실행하여 클라이언트 구성을 다시 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-138">If the service is running under a domain account, regenerate the client configuration by running Svcutil.exe against the service.</span></span> <span data-ttu-id="eac0c-139">Svcutil.exe를 실행 하는 방법에 대 한 자세한 내용은 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eac0c-139">For more information about running Svcutil.exe, see [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span> <span data-ttu-id="eac0c-140">샘플의 구성 파일 대신에 생성된 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-140">Use the generated file instead of the configuration file in the sample.</span></span> <span data-ttu-id="eac0c-141">생성된 구성 파일에는 추가 ID 정보가 포함되어 있고 기본 설정이기는 하지만 서비스 엔드포인트에 연결하는 데 필요한 모든 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-141">The generated configuration file has additional identity information, and contains all settings necessary to connect to the service endpoint even though they are the default settings.</span></span> <span data-ttu-id="eac0c-142">Id 정보에 대 한 자세한 내용은 [서비스 id 및 인증](../feature-details/service-identity-and-authentication.md)및를 참조 하세요 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) .</span><span class="sxs-lookup"><span data-stu-id="eac0c-142">For more information about identity information, see [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md), and [\<identity>](../../configure-apps/file-schema/wcf/identity.md).</span></span>  
  
4. <span data-ttu-id="eac0c-143">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-143">On the client machine, launch Client.exe from a command prompt.</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="eac0c-144">서비스를 디버깅하려면</span><span class="sxs-lookup"><span data-stu-id="eac0c-144">To debug a service</span></span>  
  
1. <span data-ttu-id="eac0c-145">**빌드** 메뉴 또는 CTRL + SHIFT + B를 사용 하 여 솔루션 (클라이언트와 서비스 모두)을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-145">Build the solution (both client and service) using the **Build** menu or CTRL+SHIFT+B.</span></span>  
  
2. <span data-ttu-id="eac0c-146">서비스가 IIS에서 호스트될 경우</span><span class="sxs-lookup"><span data-stu-id="eac0c-146">If the service is hosted in IIS:</span></span>  
  
    1. <span data-ttu-id="eac0c-147">주소를 입력 하 여 브라우저를 사용 하 여 서비스를 활성화 합니다 `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="eac0c-147">Activate the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
    2. <span data-ttu-id="eac0c-148">솔루션에서 **디버그** 메뉴를 선택 하 고 **프로세스에 연결** 메뉴 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-148">In the solution, choose the **Debug** menu and the **Attach to Process** menu item.</span></span>  
  
    3. <span data-ttu-id="eac0c-149">**모든 사용자의 프로세스 표시** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-149">Select the **Show processes from all users** check box.</span></span>  
  
    4. <span data-ttu-id="eac0c-150">디버깅할 호스트 작업자 프로세스 W3wp.exe를 선택합니다(Windows XP에서는 select ASPNet_wp.exe 선택).</span><span class="sxs-lookup"><span data-stu-id="eac0c-150">Select the host worker process W3wp.exe to debug (select ASPNet_wp.exe on Windows XP).</span></span>  
  
3. <span data-ttu-id="eac0c-151">이제 서비스 코드에서 중단점을 설정하고 예외에 중단점을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-151">You can now set breakpoints in the service code and enable breakpoints on exceptions.</span></span>  
  
4. <span data-ttu-id="eac0c-152">클라이언트 프로젝트 항목을 마우스 오른쪽 단추로 클릭 하 고 **디버그**, **새 인스턴스 시작**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-152">Right-click the client project item and choose **Debug**, **Start new instance**.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="eac0c-153">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="eac0c-153">To clean up after the sample</span></span>  
  
- <span data-ttu-id="eac0c-154">보안을 위해 서비스가 IIS에서 호스트될 경우 샘플 사용이 끝나면 설정 단계에서 부여된 가상 디렉터리 정의와 사용 권한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eac0c-154">If the service is hosted in IIS for security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac0c-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eac0c-155">See also</span></span>

- [<span data-ttu-id="eac0c-156">Windows Communication Foundation 샘플 빌드</span><span class="sxs-lookup"><span data-stu-id="eac0c-156">Building the Windows Communication Foundation Samples</span></span>](building-the-samples.md)
- <span data-ttu-id="eac0c-157">[WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eac0c-157">[Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span></span>
