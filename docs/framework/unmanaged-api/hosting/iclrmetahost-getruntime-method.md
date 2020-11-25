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
ms.openlocfilehash: 093fa64a7d51e0c2fdc304d2bb4f1c9f7b03e2ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730411"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime 메서드

특정 버전의 CLR (공용 언어 런타임)에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스를 가져옵니다. 이 메서드는 [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) 플래그와 함께 사용 되는 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 함수를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pwzVersion`  
 진행 메타 데이터에 저장 된 .NET Framework 컴파일 버전 ("v *A*" 형식)입니다. *B*[.*X*] ". *A*, *B* 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.  
  
> [!NOTE]
> 이 매개 변수는 C:\windows\ microsoft.net \framework 또는 C:\Windows\Microsoft.NET\Framework64. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 해야 합니다.  
  
 예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *X*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다. "V" 접두사는 필수입니다.  
  
 `riid`  
 진행 원하는 인터페이스의 식별자입니다. 현재이 매개 변수에 사용할 수 있는 유일한 값은 IID_ICLRRuntimeInfo입니다.  
  
 `ppRuntime`  
 제한이 요청 된 런타임에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pwzVersion` 또는 `ppRuntime`가 null입니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 [ICorRuntimeHost](icorruntimehost-interface.md) 인터페이스 및 사용 되지 않는 함수와 같은 레거시 함수와 같은 레거시 인터페이스와 일관 되 게 상호 작용 `CorBindTo*` 합니다 (.NET FRAMEWORK 2.0 호스팅 API에서 [사용 되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md) 참조). 즉, 레거시 API를 사용 하 여 로드 된 런타임이 새 API에 표시 되 고 새 API를 사용 하 여 로드 된 런타임이 레거시 API에 표시 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRMetaHost 인터페이스](iclrmetahost-interface.md)
- [사용되지 않는 CLR 호스팅 인터페이스 및 Coclass](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [CLR 호스팅 인터페이스](clr-hosting-interfaces.md)
- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
- [호스팅](index.md)
