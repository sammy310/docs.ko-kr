---
title: ICLRRuntimeInfo::GetProcAddress 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 2690a5c2e7c499d68ef9e903c62bff8f85e72e8e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703872"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a>ICLRRuntimeInfo::GetProcAddress 메서드
이 인터페이스와 연결 된 CLR (공용 언어 런타임)에서 내보낸 지정 된 함수의 주소를 가져옵니다.  
  
 이 메서드는 [GetRealProcAddress](getrealprocaddress-function.md) 함수를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pszProcName`  
 진행 내보낸 함수의 이름입니다.  
  
 `ppProc`  
 제한이 내보낸 함수의 주소입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pszProcName` 또는 `ppProc` 이 null입니다.|  
|CLR_E_SHIM_RUNTIMEEXPORT|지정한 함수는 내보낸 함수가 아닙니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드로 인해 CLR이 로드 되지만 초기화 되지는 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
