---
description: '자세한 정보: 설치 문제 해결'
title: 설치 문제 해결
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 8beb404040c15ade8f435772fe1b947eef766702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703473"
---
# <a name="troubleshoot-setup-issues"></a><span data-ttu-id="6bd60-103">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6bd60-103">Troubleshoot setup issues</span></span>

<span data-ttu-id="6bd60-104">이 문서에서는 WCF (Windows Communication Foundation) 설치 문제를 해결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-104">This article describes how to troubleshoot Windows Communication Foundation (WCF) setup issues.</span></span>  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a><span data-ttu-id="6bd60-105">일부 Windows Communication Foundation 레지스트리 키를 .NET Framework 3.0에서 MSI 복구 작업을 수행하여 복구할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6bd60-105">Some Windows Communication Foundation Registry Keys are not Repaired by Performing an MSI Repair Operation on the .NET Framework 3.0</span></span>  

 <span data-ttu-id="6bd60-106">다음과 같은 레지스트리 키를 삭제한 경우 이 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-106">If you delete any of the following registry keys:</span></span>  
  
- <span data-ttu-id="6bd60-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6bd60-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span></span>  
  
- <span data-ttu-id="6bd60-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6bd60-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span></span>  
  
- <span data-ttu-id="6bd60-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6bd60-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span></span>  
  
- <span data-ttu-id="6bd60-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6bd60-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span></span>  
  
- <span data-ttu-id="6bd60-111">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6bd60-111">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span></span>  
  
 <span data-ttu-id="6bd60-112">제어판의 [ **프로그램 추가/제거** **]** 에서 시작 된 .NET Framework 3.0 설치 관리자를 사용 하 여 복구를 실행 하는 경우 키가 다시 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-112">The keys are not re-created if you run repair by using the .NET Framework 3.0 installer launched from the **Add/Remove Programs** applet in **Control Panel**.</span></span> <span data-ttu-id="6bd60-113">해당 키를 다시 만들려면 .NET Framework 3.0을 제거하고 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-113">To recreate these keys correctly, the user must uninstall and reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-wmi-provider"></a><span data-ttu-id="6bd60-114">Wmi 서비스 손상으로 인해 WMI 공급자 설치 차단</span><span class="sxs-lookup"><span data-stu-id="6bd60-114">WMI Service Corruption Blocks Installation of the WMI provider</span></span>

 <span data-ttu-id="6bd60-115">.NET Framework 3.0 패키지를 설치할 때 WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자 설치가 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-115">WMI Service Corruption may block the installation of the Windows Communication Foundation WMI provider when installing the .NET Framework 3.0 package.</span></span> <span data-ttu-id="6bd60-116">설치 하는 동안 Windows Communication Foundation 설치 관리자는 *mofcomp.exe* 구성 요소를 사용 하 여 WCF *.mof* 파일을 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-116">During installation, the Windows Communication Foundation installer is unable to register the WCF *.mof* file using the *mofcomp.exe* component.</span></span> <span data-ttu-id="6bd60-117">다음과 같은 증상이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-117">The following is a list of symptoms:</span></span>  
  
1. <span data-ttu-id="6bd60-118">.NET Framework 3.0 설치를 완료했지만 WCF WMI 공급자가 등록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-118">.NET Framework 3.0 installation completes successfully, but the WCF WMI provider is not registered.</span></span>  
  
2. <span data-ttu-id="6bd60-119">오류 이벤트가 WCF의 WMI 공급자 등록이나 mofcomp.exe 실행에 관련된 문제를 참조하는 애플리케이션 이벤트 로그에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-119">An error event appears in the application event log that references problems registering the WMI provider for WCF, or running mofcomp.exe.</span></span>  
  
3. <span data-ttu-id="6bd60-120">사용자의 %temp% 디렉터리에 있는 이름이 dd_wcf_retCA\*인 설치 로그 파일에 WCF WMI 공급자 등록 실패에 대한 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-120">The setup log file named dd_wcf_retCA\* in the user's %temp% directory contains references to failure to register the WCF WMI provider.</span></span>  
  
4. <span data-ttu-id="6bd60-121">다음과 같은 예외가 이벤트 로그나 설치 추적 로그 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-121">An exception such as one the following may be listed in the event log or setup trace log file:</span></span>  
  
     <span data-ttu-id="6bd60-122">ServiceModelReg [11:09:59:046]: System.ApplicationException: "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"을(를) 통해 E:\WINDOWS\system32\wbem\mofcomp.exe을(를) 실행하는 동안 예기치 않은 3 결과가 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-122">ServiceModelReg [11:09:59:046]: System.ApplicationException: Unexpected result 3 executing E:\WINDOWS\system32\wbem\mofcomp.exe with "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"</span></span>  
  
     <span data-ttu-id="6bd60-123">또는</span><span class="sxs-lookup"><span data-stu-id="6bd60-123">or:</span></span>  
  
     <span data-ttu-id="6bd60-124">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: 'System.Management.ManagementPath'의 형식 이니셜라이저에서 예외를 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-124">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: The type initializer for 'System.Management.ManagementPath' threw an exception.</span></span> <span data-ttu-id="6bd60-125">---> COMException (0x80040154): 80040154 오류가 발생 하 여 CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA}의 구성 요소에 대 한 COM 클래스 팩터리를 검색 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-125">---> System.Runtime.InteropServices.COMException (0x80040154): Retrieving the COM class factory for component with CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} failed due to the following error: 80040154.</span></span>  
  
     <span data-ttu-id="6bd60-126">또는</span><span class="sxs-lookup"><span data-stu-id="6bd60-126">or:</span></span>  
  
     <span data-ttu-id="6bd60-127">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: 파일이나 어셈블리 'C:\WINDOWS\system32\wbem\mofcomp.exe' 또는 여기에 종속되어 있는 파일이나 어셈블리 중 하나를 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-127">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Could not load file or assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' or one of its dependencies.</span></span> <span data-ttu-id="6bd60-128">시스템은 지정된 파일을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-128">The system cannot find the file specified.</span></span>  
  
     <span data-ttu-id="6bd60-129">파일 이름: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span><span class="sxs-lookup"><span data-stu-id="6bd60-129">File name: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span></span>  
  
 <span data-ttu-id="6bd60-130">위에 설명한 문제를 해결하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-130">The following steps must be followed to resolve the problem described previously.</span></span>  
  
1. <span data-ttu-id="6bd60-131">WMI Diagnosis Utility를 실행 하 여 WMI 서비스를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-131">Run the WMI Diagnosis Utility to repair the WMI service.</span></span> <span data-ttu-id="6bd60-132">이 도구를 사용 하는 방법에 대 한 자세한 내용은 [WMI Diagnosis Utility](/previous-versions/tn-archive/ff404265(v%3dmsdn.10))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6bd60-132">For more information about using this tool, see [WMI Diagnosis Utility](/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).</span></span>  
  
 <span data-ttu-id="6bd60-133">**제어판** 에 있는 **프로그램 추가/제거** 애플릿을 사용 하 여 .NET Framework 3.0 설치를 복구 하거나 .NET Framework 3.0를 제거/다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-133">Repair the .NET Framework 3.0 installation by using the **Add/Remove Programs** applet located in **Control Panel**, or uninstall/reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="repair-net-framework-30-after-net-framework-35-installation"></a><span data-ttu-id="6bd60-134">.NET Framework 3.5 설치 후 .NET Framework 3.0 복구</span><span class="sxs-lookup"><span data-stu-id="6bd60-134">Repair .NET Framework 3.0 after .NET Framework 3.5 Installation</span></span>

 <span data-ttu-id="6bd60-135">.NET Framework 3.5를 설치한 후 .NET Framework 3.0를 복구 하는 경우 *machine.config* 에서 .NET Framework 3.5에 의해 도입 된 구성 요소가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-135">If you do a repair of .NET Framework 3.0 after you installed .NET Framework 3.5, configuration elements introduced by .NET Framework 3.5 in *machine.config* are removed.</span></span> <span data-ttu-id="6bd60-136">그러나 *web.config* 파일은 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-136">However, the *web.config* file remains intact.</span></span> <span data-ttu-id="6bd60-137">해결 방법은 ARP를 통해이 후 .NET Framework 3.5를 복구 하거나 스위치와 함께 [WFServicesReg.exe (워크플로 서비스 등록 도구)](workflow-service-registration-tool-wfservicesreg-exe.md) 를 사용 하는 것입니다 `/c` .</span><span class="sxs-lookup"><span data-stu-id="6bd60-137">The workaround is to repair .NET Framework 3.5 after this via ARP, or use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch.</span></span>  
  
 <span data-ttu-id="6bd60-138">\Framework\v3.5\ 또는%windir%\Microsoft.NET\framework64\v3.5\에서 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) 를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-138">[WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5\</span></span>  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a><span data-ttu-id="6bd60-139">.NET Framework 3.5 설치 후 WCF/WF Webhost에 대해 IIS를 올바로 구성</span><span class="sxs-lookup"><span data-stu-id="6bd60-139">Configure IIS Properly for WCF/WF Webhost after Installing .NET Framework 3.5</span></span>  

 <span data-ttu-id="6bd60-140">.NET Framework 3.5 설치에서 추가 WCF 관련 IIS 구성 설정을 구성 하지 못하면 설치 로그에 오류를 기록 하 고 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-140">When .NET Framework 3.5 installation fails to configure additional WCF-related IIS configuration settings, it logs an error in the installation log and continues.</span></span> <span data-ttu-id="6bd60-141">필요한 구성 설정이 없기 때문에 WorkflowServices 애플리케이션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-141">Any attempt to run WorkflowServices applications will fail, since the required configuration settings are missing.</span></span> <span data-ttu-id="6bd60-142">예를 들어 xoml 또는 규칙 서비스를 로드하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-142">For example, loading xoml or rules service can fail.</span></span>  
  
 <span data-ttu-id="6bd60-143">이 문제를 해결 하려면 해당 스위치와 함께 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) 를 사용 `/c` 하 여 컴퓨터에서 IIS 스크립트 맵을 제대로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-143">To workaround this problem, use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch to properly configure IIS script maps on the machine.</span></span> <span data-ttu-id="6bd60-144">\Framework\v3.5\ 또는%windir%\Microsoft.NET\framework64\v3.5\에서 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) 를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-144">[WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5\</span></span>  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule"></a><span data-ttu-id="6bd60-145">' System.servicemodel ' 형식을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-145">Could not load type 'System.ServiceModel.Activation.HttpModule'</span></span>

<span data-ttu-id="6bd60-146">**' System.servicemodel, Version 3.0.0.0, Culture = 중립, PublicKeyToken = b77a5c561934e089 ' 어셈블리에서 ' System.servicemodel ' 형식을 로드할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="6bd60-146">**Could not load type 'System.ServiceModel.Activation.HttpModule' from assembly 'System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'**</span></span>

 <span data-ttu-id="6bd60-147">이 오류는 .NET Framework 4가 설치 된 다음 WCF HTTP 활성화를 사용 하도록 설정 된 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-147">This error occurs if .NET Framework 4 is installed and then WCF HTTP Activation is enabled.</span></span> <span data-ttu-id="6bd60-148">이 문제를 해결 하려면 Visual Studio에 대 한 개발자 명령 프롬프트 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd60-148">To resolve the issue, run the following command from inside the Developer Command Prompt for Visual Studio:</span></span>  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a><span data-ttu-id="6bd60-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bd60-149">See also</span></span>

- [<span data-ttu-id="6bd60-150">설치 지침</span><span class="sxs-lookup"><span data-stu-id="6bd60-150">Set-Up Instructions</span></span>](./samples/set-up-instructions.md)
