---
title: Windows Communication Foundation 샘플 빌드
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: ee1c8101e31464fa203341d53137525433782c18
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253839"
---
# <a name="building-the-windows-communication-foundation-samples"></a><span data-ttu-id="7d569-102">Windows Communication Foundation 샘플 빌드</span><span class="sxs-lookup"><span data-stu-id="7d569-102">Building the Windows Communication Foundation Samples</span></span>

<span data-ttu-id="7d569-103">WCF (Windows Communication Foundation) 샘플은 Visual Studio IDE를 사용 하거나 명령줄에서 **msbuild** 명령을 사용 하 여 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-103">The Windows Communication Foundation (WCF) samples can be built using the Visual Studio IDE or using the **msbuild** command from the command line.</span></span> <span data-ttu-id="7d569-104">이 항목에서는 이 두 절차를 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-104">Both procedures are described in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="7d569-105">WCF 샘플을 빌드하거나 실행 하기 전에 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-105">Before building or running any of the WCF samples, ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

## <a name="to-build-the-sample-using-a-command-prompt"></a><span data-ttu-id="7d569-106">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="7d569-106">To build the sample using a command prompt</span></span>

1. <span data-ttu-id="7d569-107">Visual Studio에 대 한 개발자 명령 프롬프트를 열고 샘플을 설치한 디렉터리 위치 아래의 언어별 하위 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-107">Open Developer Command Prompt for Visual Studio and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="7d569-108">`msbuild`명령줄에를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-108">Type `msbuild` at the command line.</span></span> <span data-ttu-id="7d569-109">클라이언트 프로그램 파일은 *client\bin* 에 빌드되고 서비스 프로그램 파일은 *service\bin* 에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-109">The client program files are built to *client\bin* and the service program files are built to *service\bin*.</span></span> <span data-ttu-id="7d569-110">인터넷 정보 서비스 (IIS)에서 서비스를 호스팅하는 경우 서비스 프로그램 파일도 *servicemodelsamples* 디렉터리와 *\bin* 하위 디렉터리에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-110">If the service is hosted by Internet Information Services (IIS), the service program files are also copied to the *servicemodelsamples* directory and its *\bin* subdirectory.</span></span>

> [!NOTE]
> <span data-ttu-id="7d569-111">*%Systemdrive%\inetpub\wwwroot* 에서 acl을 설정 하 여를 실행 하는 계정에 대 한 수정 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-111">You must set the ACLs on *%systemdrive%\inetpub\wwwroot* to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="7d569-112">그러지 않으면 일부 빌드 후 이벤트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-112">Otherwise some post build events fail.</span></span> <span data-ttu-id="7d569-113">또는 ACL을 그대로 두고 관리자로 SDK 명령 프롬프트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-113">Alternatively, you can leave the ACLs as they are and run the SDK command prompt as administrator.</span></span>

## <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="7d569-114">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="7d569-114">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="7d569-115">Visual Studio의 **파일** 메뉴에서 **Open**  >  **프로젝트/솔루션** 열기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-115">From the **File** menu in Visual Studio, select **Open** > **Project/Solution**.</span></span> <span data-ttu-id="7d569-116">샘플을 설치한 디렉터리 아래의 언어별 하위 디렉터리로 이동 하 고 .sln 파일 아이콘을 두 번 클릭 하 여 Visual Studio에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-116">Navigate to the language-specific subdirectory under the directory in which you installed the sample, and double-click the .sln file icon to open the solution in Visual Studio.</span></span>

1. <span data-ttu-id="7d569-117">**빌드** 메뉴에서 **솔루션 다시 빌드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-117">From the **Build** menu, select **Rebuild Solution**.</span></span>

   <span data-ttu-id="7d569-118">클라이언트 프로그램 파일이 client\bin에 빌드되고 서비스 프로그램 파일이 service\bin에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-118">The client program files are built to client\bin and the service program files are built to service\bin.</span></span> <span data-ttu-id="7d569-119">서비스가 IIS에서 호스트 되는 경우 서비스 프로그램 파일도 *servicemodelsamples* 디렉터리와 *\bin* 하위 디렉터리에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-119">If the service is hosted in IIS, the service program files are also copied to the *servicemodelsamples* directory and its *\bin* subdirectory.</span></span>

> [!NOTE]
> <span data-ttu-id="7d569-120">실행에 사용하는 계정에 수정 권한을 부여하도록 %systemdrive%\inetpub\wwwroot의 ACL을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-120">You must set the ACLs on %systemdrive%\inetpub\wwwroot to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="7d569-121">그러지 않으면 일부 빌드 후 이벤트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-121">Otherwise some post build events fail.</span></span> <span data-ttu-id="7d569-122">또는 ACL을 그대로 두고 관리자로 SDK 명령 프롬프트 또는 Visual Studio를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-122">Alternatively, you can leave the ACLs as they are and run the SDK command prompt or Visual Studio as administrator.</span></span> <span data-ttu-id="7d569-123">일부 Visual Studio 작업 (예: 디버거를 ASP.NET worker 프로세스에 연결)에도 관리 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-123">Some Visual Studio actions (such as attaching a debugger to the ASP.NET worker process) also require administrative privileges.</span></span>

## <a name="setup-batch-files-and-scripts"></a><span data-ttu-id="7d569-124">배치 파일 및 스크립트 설치</span><span class="sxs-lookup"><span data-stu-id="7d569-124">Setup Batch Files and Scripts</span></span>

 <span data-ttu-id="7d569-125">Visual Studio 용 개발자 명령 프롬프트에서 Setup.exe 및 Cleanup.exe 배치 파일과 스크립트를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-125">Setup.exe and Cleanup.exe batch files and scripts should be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="7d569-126">일부 설치 및 정리 파일은 관리자 권한이 필요한 작업을 수행하므로 관리자 권한으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-126">Several set up and clean up files perform tasks that require administrative privileges and should be launched with administrator privileges.</span></span>

## <a name="important-security-information-about-metadata-endpoints"></a><span data-ttu-id="7d569-127">메타데이터 엔드포인트에 대한 중요한 보안 정보</span><span class="sxs-lookup"><span data-stu-id="7d569-127">Important Security Information about Metadata Endpoints</span></span>

 <span data-ttu-id="7d569-128">잠재적으로 중요 한 서비스 메타 데이터가 실수로 공개 되지 않도록 하기 위해 WCF (Windows Communication Foundation) 서비스의 기본 구성에서는 메타 데이터 게시를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-128">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="7d569-129">이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-129">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="7d569-130">샘플로 보다 쉽게 작업할 수 있도록 거의 모든 샘플에서는 보안되지 않은 메타데이터 게시 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-130">To make experimenting with the samples easier, almost all samples expose an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="7d569-131">이러한 엔드포인트는 인증되지 않은 익명의 소비자가 사용할 수 있으므로 이러한 엔드포인트를 배포하기 전에 서비스의 메타데이터를 공개하는 것이 적절한지 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-131">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="7d569-132">서비스 메타 데이터 게시에 대 한 자세한 내용은 [메타 데이터 게시 동작](metadata-publishing-behavior.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d569-132">For more information about publishing service metadata, see the [Metadata Publishing Behavior](metadata-publishing-behavior.md) sample.</span></span> <span data-ttu-id="7d569-133">메타 데이터 끝점에 보안을 설정 하는 샘플은 [사용자 지정 보안 메타 데이터 끝점](custom-secure-metadata-endpoint.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d569-133">See the [Custom Secure Metadata Endpoint](custom-secure-metadata-endpoint.md) sample for a sample securing a metadata endpoint.</span></span>

## <a name="exception-handling"></a><span data-ttu-id="7d569-134">예외 처리</span><span class="sxs-lookup"><span data-stu-id="7d569-134">Exception Handling</span></span>

 <span data-ttu-id="7d569-135">일반적으로 이러한 샘플에는 코드가 샘플의 주제 위주로 작동하도록 예외 처리가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-135">Generally speaking these samples do not include exception handling to keep the code focused on the subject of the sample.</span></span> <span data-ttu-id="7d569-136">예외 처리에 대 한 자세한 내용은 예상 된 [예외](expected-exceptions.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d569-136">For more information about exception handling, see the [Expected Exceptions](expected-exceptions.md) sample.</span></span>

## <a name="regenerating-clients-and-configuration-with-svcutil"></a><span data-ttu-id="7d569-137">Svcutil을 사용하여 클라이언트 및 구성 다시 생성</span><span class="sxs-lookup"><span data-stu-id="7d569-137">Regenerating Clients and Configuration with Svcutil</span></span>

 <span data-ttu-id="7d569-138">[ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 대부분의 샘플에 대 한 클라이언트 코드 및 구성을 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-138">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to regenerate client code and configuration for most of the samples.</span></span> <span data-ttu-id="7d569-139">일부 샘플에서는 구성을 수동으로 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-139">Some samples require manually edited configuration.</span></span> <span data-ttu-id="7d569-140">예를 들어, Svcutil.exe를 사용하여 클라이언트 인증서 자격 증명을 사용하는 샘플의 구성을 다시 생성하는 경우 이전에 구성된 자격 증명을 수동으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-140">For example, if you use Svcutil.exe to regenerate the configuration for a sample that uses client certificate credentials, you must manually specify the credentials previously configured.</span></span> <span data-ttu-id="7d569-141">일부 샘플에서는 생성된 코드에 영향을 주기 위해 특정 Svcutil.exe 옵션을 사용하며, 이러한 옵션은 특정 샘플 항목에 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-141">Some samples use specific Svcutil.exe options to affect the generated code, these options are specified in the specific sample topics.</span></span>

### <a name="to-regenerate-the-client-and-configuration-files"></a><span data-ttu-id="7d569-142">클라이언트 및 구성 파일을 다시 생성하려면</span><span class="sxs-lookup"><span data-stu-id="7d569-142">To regenerate the client and configuration files</span></span>

1. <span data-ttu-id="7d569-143">SDK 명령 프롬프트를 열고 샘플을 설치한 디렉터리 위치 아래의 언어별 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-143">Open an SDK command prompt and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="7d569-144">웹 호스팅 서비스의 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-144">If the service is a Web-hosted type, use the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     <span data-ttu-id="7d569-145">자체 호스팅 서비스의 경우 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-145">If the service is a self-hosted type the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     <span data-ttu-id="7d569-146">`http://localhost:8000/ServiceModelSamples/service.svc/mex`을 자체 호스팅 서비스의 mex 끝점 주소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-146">Replace `http://localhost:8000/ServiceModelSamples/service.svc/mex` with the address of the self-hosted service's mex endpoint.</span></span>

     <span data-ttu-id="7d569-147">Visual Basic 형식에서 클라이언트를 생성하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-147">To generate the client in a Visual Basic type, use the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     <span data-ttu-id="7d569-148">자체 호스팅 서비스의 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-148">If the service is a self-hosted type, use the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > <span data-ttu-id="7d569-149">클라이언트 구성의 생성을 건너뛰려면 **/Noconfig** 옵션을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d569-149">To skip the generation of client configuration add the **/noConfig** option.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d569-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d569-150">See also</span></span>

- [<span data-ttu-id="7d569-151">Windows Communication Foundation 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="7d569-151">Running the Windows Communication Foundation Samples</span></span>](running-the-samples.md)
- [<span data-ttu-id="7d569-152">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="7d569-152">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
