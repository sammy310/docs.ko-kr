---
title: CorBindToRuntime 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176515"
---
# <a name="corbindtoruntime-function"></a>CorBindToRuntime 함수
관리되지 않는 호스트가 공통 언어 런타임(CLR)을 프로세스에 로드할 수 있도록 합니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwszVersion`  
 【인】 로드할 CLR 버전을 설명하는 문자열입니다.  
  
 .NET Framework의 버전 번호는 마침표로 구분되는 네 부분으로 *구성됩니다.* 문자열은 문자 `pwszVersion` "v"로 시작하고 버전 번호의 처음 세 부분(예: "v1.0.1529")으로 시작해야 합니다.  
  
 일부 CLR 버전은 이전 CLR 버전과의 호환성을 지정하는 정책 설명과 함께 설치됩니다. 기본적으로 시작 심은 `pwszVersion` 정책 문에 대해 평가하고 요청되는 버전과 호환되는 런타임의 최신 버전을 로드합니다. 호스트는 shim을 강제로 정책 평가를 건너뛰고 아래에 `pwszVersion` 설명된 대로 `STARTUP_LOADER_SAFEMODE` `flags` 매개 변수에 대한 값을 전달하여 지정된 정확한 버전을 로드할 수 있습니다.  
  
 호출자에게 null을 `pwszVersion`지정하는 경우 최신 버전의 런타임이 로드됩니다. null을 전달하면 호스트가 로드되는 런타임 버전을 제어할 수 없습니다. 이 방법은 일부 시나리오에서 적절할 수 있지만 호스트가 로드할 특정 버전을 제공하는 것이 좋습니다.  
  
 `pwszBuildFlavor`  
 【인】 서버를 로드할지 또는 CLR의 워크스테이션 빌드를 로드할지 여부를 지정하는 문자열입니다. 유효한 값은 `svr` 및 `wks`입니다. 서버 빌드는 가비지 수집을 위해 여러 프로세서를 활용하도록 최적화되었으며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행되는 클라이언트 응용 프로그램에 최적화되어 있습니다.  
  
 null로 설정된 경우 `pwszBuildFlavor` 워크스테이션 빌드가 로드됩니다. 단일 프로세서 컴퓨터에서 실행할 때 워크스테이션 빌드는 로 설정되어 `pwszBuildFlavor` 있더라도 `svr`항상 로드됩니다. 그러나 `pwszBuildFlavor` `svr` 설정되어 있고 동시 가비지 수집이 `flags` 지정되면(매개 변수 설명 참조) 서버 빌드가 로드됩니다.  
  
 `rclsid`  
 진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다. 지원되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost.  
  
 `riid`  
 【인】 에서 `IID` `rclsid`요청된 인터페이스의 지원되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost.  
  
 `ppv`  
 【아웃】 반환된 인터페이스 `riid`포인터에 대해 .  
  
## <a name="remarks"></a>설명  
 존재하지 `pwszVersion` 않는 런타임 버전을 지정하면 CLR_E_SHIM_RUNTIMELOAD `CorBindToRuntimeEx` HRESULT 값을 반환합니다.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Windows ID의 실행 컨텍스트 및 흐름  
 CLR의 버전 1에서 <xref:System.Security.Principal.WindowsIdentity> 개체는 새 스레드, 스레드 풀 또는 타이머 콜백과 같은 비동기 지점에서 흐르지 않습니다. CLR의 버전 2.0에서 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대한 일부 정보를 래핑하고 응용 프로그램 도메인 경계를 넘지 않고 비동기 지점을 가로질러 흐릅니다. 마찬가지로 개체는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점을 가로질러흐기도 합니다. 따라서 스레드의 현재 가장(있는 경우)도 흐릅니다.  
  
 다음 두 가지 방법으로 흐름을 변경할 수 있습니다.  
  
1. <xref:System.Threading.ExecutionContext> 스레드별로 흐름을 억제하도록 설정을 수정합니다(의 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 이 및 메서드 참조). <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A>  
  
2. 프로세스 기본 모드를 버전 1 호환성 모드로 <xref:System.Security.Principal.WindowsIdentity> 변경하여 현재 스레드의 <xref:System.Threading.ExecutionContext> 설정에 관계없이 개체가 비동기 지점을 가로질러 흐르지 않습니다. 기본 모드를 변경하는 방법은 관리되는 실행 관리 항목 또는 관리되지 않는 호스팅 인터페이스를 사용하여 CLR을 로드할지 여부에 따라 달라집니다.  
  
    1. 관리되는 실행 경우 `enabled` [ \<레거시 사칭정책>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 요소의 특성을 `true`로 설정해야 합니다.  
  
    2. 관리되지 않는 호스팅 인터페이스의 `STARTUP_LEGACY_IMPERSONATION` 경우 `flags` 함수를 호출할 때 매개 변수에 플래그를 설정합니다. `CorBindToRuntimeEx`  
  
     버전 1 호환성 모드는 전체 프로세스및 프로세스의 모든 응용 프로그램 도메인에 적용됩니다.  
  
## <a name="remarks"></a>설명  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime` 및 동일한 작업을 수행하지만 이 `CorBindToRuntimeEx` 기능을 사용하면 플래그를 설정하여 CLR의 동작을 지정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeByCfg 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
