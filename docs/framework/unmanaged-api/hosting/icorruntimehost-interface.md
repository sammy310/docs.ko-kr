---
title: ICorRuntimeHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: e66e1468a864ec85d88f759c481c7a9707d37f7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139540"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost 인터페이스
호스트에서 CLR (공용 언어 런타임)을 명시적으로 시작 및 중지 하 고, 응용 프로그램 도메인을 만들고 구성 하 고, 기본 도메인에 액세스 하 고, 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 .NET Framework 버전 2.0에서이 인터페이스는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)에 의해 대체 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CloseEnum 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|도메인 열거자를 도메인 목록의 시작 부분으로 다시 설정 합니다.|  
|[CreateDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|응용 프로그램 도메인을 만듭니다. 호출자는 <xref:System.AppDomain?displayProperty=nameWithType>형식의 인스턴스에 <xref:System._AppDomain> 형식의 인터페이스 포인터를 받습니다.|  
|[CreateDomainEx 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|응용 프로그램 도메인을 만듭니다. 이 메서드를 사용 하면 호출자가 IAppDomainSetup 인스턴스를 전달 하 여 반환 된 <xref:System._AppDomain> 인스턴스의 추가 기능을 구성할 수 있습니다.|  
|[CreateDomainSetup 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|<xref:System.AppDomainSetup> 인스턴스에 `IAppDomainSetup` 형식의 인터페이스 포인터를 가져옵니다. `IAppDomainSetup`는 응용 프로그램 도메인을 만들기 전에 요소를 구성 하는 메서드를 제공 합니다.|  
|[CreateEvidence 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|호스트가 [Createdomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 또는 [createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)에 전달할 보안 증명 정보를 만들 수 있도록 하는 <xref:System.Security.Principal.IIdentity>형식의 인터페이스 포인터를 가져옵니다.|  
|[CreateLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|사용하지 마십시오.|  
|[CurrentDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|현재 스레드에 로드 된 도메인을 나타내는 <xref:System._AppDomain> 형식의 인터페이스 포인터를 가져옵니다.|  
|[DeleteLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|사용하지 마십시오.|  
|[EnumDomains 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|현재 프로세스의 도메인에 대 한 열거자를 가져옵니다.|  
|[GetConfiguration 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|호스트가 CLR의 콜백 구성을 지정할 수 있도록 하는 개체를 가져옵니다.|  
|[GetDefaultDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|현재 프로세스에 대 한 기본 도메인을 나타내는 <xref:System._AppDomain> 형식의 인터페이스 포인터를 가져옵니다.|  
|[LocksHeldByLogicalThread 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|사용하지 마십시오.|  
|[MapFile 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|지정 된 파일을 메모리에 매핑합니다. 이 메서드는 사용되지 않습니다.|  
|[NextDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|열거형의 다음 도메인에 대 한 인터페이스 포인터를 가져옵니다.|  
|[Start 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|CLR을 시작 합니다.|  
|[Stop 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|런타임에 현재 프로세스에 대 한 코드의 실행을 중지 합니다.|  
|[SwitchInLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|사용하지 마십시오.|  
|[SwitchOutLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|사용하지 마십시오.|  
|[UnloadDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|현재 프로세스에서 지정 된 응용 프로그램 도메인을 언로드합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참조

- <xref:System.AppDomain>
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [런타임 호스트](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
