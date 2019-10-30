---
title: ICLRRuntimeHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: 568c63681b84d0ab3642d84e4a6715ad230582db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120385"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost 인터페이스
.NET Framework 버전 1에서 제공 하는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 인터페이스와 유사한 기능을 제공 하며 다음과 같이 변경 합니다.  
  
- [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) 메서드를 추가 하 여 호스트 컨트롤 인터페이스를 설정 합니다.  
  
- `ICorRuntimeHost`에서 제공 하는 일부 메서드를 생략 하는 것입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ExecuteApplication 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|매니페스트 기반 ClickOnce 배포 시나리오에서 새 도메인에 활성화 될 응용 프로그램을 지정 하는 데 사용 됩니다.|  
|[ExecuteInAppDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|지정 된 관리 코드를 실행할 <xref:System.AppDomain>를 지정 합니다.|  
|[ExecuteInDefaultAppDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|지정 된 어셈블리에서 지정 된 형식의 지정 된 메서드를 호출 합니다.|  
|[GetCLRControl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|호스트가 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 형식의 인터페이스 포인터를 가져옵니다.|  
|[GetCurrentAppDomainId 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|현재 실행 중인 <xref:System.AppDomain>의 숫자 식별자를 가져옵니다.|  
|[SetHostControl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|호스트 컨트롤 인터페이스를 설정 합니다. `Start`를 호출 하기 전에 `SetHostControl`를 호출 해야 합니다.|  
|[Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|CLR을 프로세스로 초기화 합니다.|  
|[Stop 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|런타임에의 한 코드 실행을 중지 합니다.|  
|[UnloadAppDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|지정 된 숫자 식별자에 해당 하는 <xref:System.AppDomain>를 언로드합니다.|  
  
## <a name="remarks"></a>주의  
 .NET Framework 4부터 [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) 인터페이스를 사용 하 여 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터를 가져온 다음 [ICLRRuntimeInfo:: getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드를 호출 하 여 `ICLRRuntimeHost`에 대 한 포인터를 가져옵니다. 이전 버전의 .NET Framework에서 호스트 `ICLRRuntimeHost` [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)를 호출 하 여 해당 인스턴스에 대 한 포인터를 가져옵니다. .NET Framework 버전 2.0에 제공 된 기술의 구현을 제공 하려면 `ICorRuntimeHost`대신 `ICLRRuntimeHost`를 사용 해야 합니다.  
  
> [!IMPORTANT]
> 매니페스트 기반 응용 프로그램을 활성화 하기 위해 [Executeapplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) 메서드를 호출 하기 전에 [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드를 호출 하지 마세요. `Start` 메서드를 먼저 호출 하면 `ExecuteApplication` 메서드 호출이 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
