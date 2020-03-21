---
title: CorBindToRuntimeHost 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176489"
---
# <a name="corbindtoruntimehost-function"></a>CorBindToRuntimeHost 함수
호스트가 지정된 버전의 공통 언어 런타임(CLR)을 프로세스에 로드할 수 있습니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwszVersion`  
 【인】 로드할 CLR 버전을 설명하는 문자열입니다.  
  
 .NET Framework의 버전 번호는 마침표로 구분되는 네 부분으로 *구성됩니다.* 문자열은 문자 `pwszVersion` "v"로 시작하고 버전 번호의 처음 세 부분(예: "v1.0.1529")으로 시작해야 합니다.  
  
 일부 CLR 버전은 이전 CLR 버전과의 호환성을 지정하는 정책 설명과 함께 설치됩니다. 기본적으로 시작 심은 `pwszVersion` 정책 문에 대해 평가하고 요청되는 버전과 호환되는 런타임의 최신 버전을 로드합니다. 호스트는 shim을 강제로 정책 평가를 건너뛰고 매개 `pwszVersion` 변수에 대한 STARTUP_LOADER_SAFEMODE 값을 `startupFlags` 전달하여 지정된 정확한 버전을 로드할 수 있습니다.  
  
 이 `pwszVersion` `null,` 경우 메서드는 CLR의 모든 버전을 로드하지 않습니다. 대신 런타임을 로드하지 못했음을 나타내는 CLR_E_SHIM_RUNTIMELOAD 반환합니다.  
  
 `pwszBuildFlavor`  
 【인】 서버를 로드할지 또는 CLR의 워크스테이션 빌드를 로드할지 여부를 지정하는 문자열입니다. 유효한 값은 `svr` 및 `wks`입니다. 서버 빌드는 가비지 수집을 위해 여러 프로세서를 활용하도록 최적화되었으며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행되는 클라이언트 응용 프로그램에 최적화되어 있습니다.  
  
 null로 설정된 경우 `pwszBuildFlavor` 워크스테이션 빌드가 로드됩니다. 단일 프로세서 컴퓨터에서 실행할 때 워크스테이션 빌드는 로 설정되어 `pwszBuildFlavor` 있더라도 `svr`항상 로드됩니다. 그러나 `pwszBuildFlavor` `svr` 설정되어 있고 동시 가비지 수집이 `startupFlags` 지정되면(매개 변수 설명 참조) 서버 빌드가 로드됩니다.  
  
> [!NOTE]
> 인텔 이타늄 아키텍처(이전의 IA-64)를 구현하는 64비트 시스템에서 WOW64 x86 에뮬레이터를 실행하는 응용 프로그램에서는 동시 가비지 수집이 지원되지 않습니다. 64비트 Windows 시스템에서 WOW64를 사용하는 방법에 대한 자세한 내용은 [32비트 응용 프로그램 실행을](/windows/desktop/WinProg64/running-32-bit-applications)참조하십시오.  
  
 `pwszHostConfigFile`  
 【인】 로드할 CLR 버전을 지정하는 호스트 구성 파일의 이름입니다. 파일 이름에 정규화된 경로가 포함되지 않은 경우 파일은 호출하는 실행 파일과 동일한 디렉터리에 있는 것으로 가정합니다.  
  
 `pReserved`  
 【인】 향후 확장성을 위해 예약되었습니다.  
  
 `startupFlags`  
 【인】 동시 가비지 수집, 도메인 중립 코드 및 매개 변수의 `pwszVersion` 동작을 제어하는 플래그 집합입니다. 플래그가 설정되지 않은 경우 기본값은 단일 도메인입니다. 지원되는 값 목록은 STARTUP_FLAGS [열거형](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)을 참조하십시오.  
  
 `rclsid`  
 진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다. 지원되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost.  
  
 `riid`  
 【인】 요청하는 `IID` 인터페이스의 입니다. 지원되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost.  
  
 `ppv`  
 【아웃】 로드된 런타임 버전에 대한 인터페이스 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
