---
title: ICLRMetaHost::GetRuntime 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9889ddf1c03f14835101f31d0a3b264f0016267
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676553"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime 메서드
가져옵니다 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 는 CLR (공용 언어 런타임)의 특정 버전에 해당 하는 인터페이스입니다. 이 메서드를 대체 합니다 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수를 사용 합니다 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwzVersion`  
 [in] .NET Framework 컴파일 버전 메타 데이터 형식으로 저장 "v*A*. *B*[. *X*] "입니다. *A*, *B*, 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.  
  
> [!NOTE]
>  이 매개 변수는 C:\Windows\Microsoft.NET\Framework 또는 C:\Windows\Microsoft.NET\Framework64 아래 표시 된 대로.NET Framework 버전의 경우 디렉터리 이름이 일치 해야 합니다.  
  
 예제 값은 "v1.0.3705", "v1.1.4322", "v2.0.50727" 및 "v4.0"입니다. *X*", 여기서 *X* 설치 빌드 번호에 따라 달라 집니다. "V" 접두사는 필수입니다.  
  
 `riid`  
 [in] 원하는 인터페이스의 식별자입니다. 현재이 매개 변수에 대 한 유일한 유효 값은 IID_ICLRRuntimeInfo 합니다.  
  
 `ppRuntime`  
 [out] 에 대 한 포인터를 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 요청된 된 런타임을에 해당 하는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pwzVersion` 또는 `ppRuntime`이 null입니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드가 상호 작용 하는 일관 되 게 레거시 인터페이스를 사용 하 여 같은 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 사용 되지 않는 등의 인터페이스 및 레거시 기능 `CorBindTo*` 함수 (참조 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 호스팅 API는.NET Framework 2.0에서). 즉, 기존 API를 사용 하 여 로드 된 런타임을 새 API에 표시 되며 새 API를 사용 하 여 로드 된 런타임을 레거시 API에 표시 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICLRMetaHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [사용되지 않는 CLR 호스팅 인터페이스 및 Coclass](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
