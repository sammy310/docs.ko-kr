---
title: 설치 문제 해결
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 358897917fff7097bc2907456f295d98ad6d431f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645169"
---
# <a name="troubleshooting-setup-issues"></a>설치 문제 해결
이 항목에서는 Windows Communication Foundation (WCF)가 설치 문제를 해결 하는 방법을 설명 합니다.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>일부 Windows Communication Foundation 레지스트리 키를 .NET Framework 3.0에서 MSI 복구 작업을 수행하여 복구할 수 없음  
 다음과 같은 레지스트리 키를 삭제한 경우 이 문제가 발생합니다.  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 시작 하는.NET Framework 3.0 설치 관리자를 사용 하 여 복구를 실행 하는 경우 키를 다시 생성 되지 않습니다 합니다 **프로그램 추가/제거** 애플릿에서 **제어판**합니다. 해당 키를 다시 만들려면 .NET Framework 3.0을 제거하고 다시 설치해야 합니다.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>.NET Framework 3.0 패키지 설치 시 WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자가 설치되지 않음  
 WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자가 설치되지 않을 수 있습니다. 설치 시 Windows Communication Foundation 설치 관리자가 mofcomp.exe 구성 요소를 사용하여 WCF .mof 파일을 등록할 수 없습니다. 다음과 같은 증상이 있습니다.  
  
1. .NET Framework 3.0 설치를 완료했지만 WCF WMI 공급자가 등록되지 않습니다.  
  
2. 오류 이벤트가 WCF의 WMI 공급자 등록이나 mofcomp.exe 실행에 관련된 문제를 참조하는 애플리케이션 이벤트 로그에 표시됩니다.  
  
3. 사용자의 %temp% 디렉터리에 있는 이름이 dd_wcf_retCA*인 설치 로그 파일에 WCF WMI 공급자 등록 실패에 대한 참조가 있습니다.  
  
4. 다음과 같은 예외가 이벤트 로그나 설치 추적 로그 파일에 표시됩니다.  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Unexpected result 3 executing E:\WINDOWS\system32\wbem\mofcomp.exe with "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     또는  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: 형식 이니셜라이저 'System.Management.ManagementPath'에 대 한 예외가 발생 했습니다. System.Runtime.InteropServices.COMException (0x80040154)--->: 다음 오류로 인해 실패 한 구성 요소의 CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA}를 사용 하 여 COM 클래스 팩터리를 검색 합니다. 80040154.  
  
     또는  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: 파일이 나 어셈블리 'C:\WINDOWS\system32\wbem\mofcomp.exe' 또는 해당 종속성 중 하나를 로드할 수 없습니다. 지정한 파일을 찾을 수 없습니다.  
  
     파일 이름 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 위에 설명한 문제를 해결하려면 다음 단계를 수행해야 합니다.  
  
1. 실행할 [WMI Diagnosis Utility의 버전 2.0](https://go.microsoft.com/fwlink/?LinkId=94685) WMI 서비스를 복구 합니다. 이 도구를 사용 하는 방법에 대 한 자세한 내용은 참조는 [WMI Diagnosis Utility](https://go.microsoft.com/fwlink/?LinkId=94686) 항목입니다.  
  
 사용 하 여.NET Framework 3.0 설치를 복구 합니다 **프로그램 추가/제거** 애플릿을에 있는 **제어판**, 또는.NET Framework 3.0를 제거/다시 설치 하 합니다.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>.NET Framework 3.5 설치 후 .NET Framework 3.0을 복구하면 machine.config에서 .NET Framework 3.5에 의해 추가된 구성 요소가 제거됨  
 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치한 후 .NET Framework 3.0을 복구하면 machine.config에서 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에 의해 추가된 구성 요소가 제거됩니다. 그러나 web.config는 그대로 유지됩니다. 복구 하려면이 문제를 해결 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] ARP, 또는 사용을 통해이 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) 사용 하 여는 `/c` 전환 합니다.  
  
 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) %windir%\Microsoft.NET\framework\v3.5\ 또는 %windir%\Microsoft.NET\framework64\v3.5\에서 찾을 수 있습니다  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>.NET Framework 3.5 설치 후 WCF/WF Webhost에 대해 IIS를 올바로 구성  
 때 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 추가 WCF 관련 IIS 구성 설정을 구성 하려면 설치 실패, 설치 로그에서 오류를 기록 하 고 계속 합니다. 필요한 구성 설정이 없기 때문에 WorkflowServices 애플리케이션을 실행할 수 없습니다. 예를 들어 xoml 또는 규칙 서비스를 로드하지 못할 수 있습니다.  
  
 문제를 해결 하려면이 문제를 사용 하 여는 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) 사용 하 여는 `/c` 제대로 컴퓨터에 IIS 스크립트 맵을 구성으로 전환 합니다. [워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) %windir%\Microsoft.NET\framework\v3.5\ 또는 %windir%\Microsoft.NET\framework64\v3.5\에서 찾을 수 있습니다  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’ 어셈블리에서 ‘System.ServiceModel.Activation.HttpModule’ 형식을 로드할 수 없습니다.  
 이 오류가 발생 하는 경우 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 되어 및 WCF HTTP 활성화가 사용 하는 다음입니다. 다음 명령줄을 실행에서 개발자 명령 프롬프트 내에서 Visual Studio에 대 한이 문제를 해결 하려면  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>참고자료

- [설치 지침](../../../docs/framework/wcf/samples/set-up-instructions.md)
