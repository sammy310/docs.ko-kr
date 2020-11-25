---
title: ICLRRuntimeInfo::GetDefaultStartupFlags 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 2f828a3720f7313ee9cb851c6adae78bd5ea4fe8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732096"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags 메서드

런타임을 시작 하는 데 사용 되는 시작 플래그 및 호스트 구성 파일을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pdwStartupFlags`  
 제한이 현재 설정 된 호스트 시작 플래그에 대 한 포인터입니다.  
  
 `pwzHostConfigFile`  
 제한이 현재 호스트 구성 파일의 디렉터리 경로에 대 한 포인터입니다.  
  
 `pcchHostConfigFile`  
 [in, out] 입력 시 `pwzHostConfigFile` 버퍼 오버런을 방지 하기 위한의 크기입니다. `pwzHostConfigFile`가 null 인 경우 메서드는 `pwzHostConfigFile` 미리 할당을 위해의 필수 크기를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 다음과 같은 특정 HRESULT 및 메서드 오류를 나타내는 HRESULT 오류를 반환 합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 기본 플래그 값 ( `STARTUP_CONCURRENT_GC` 및 `NULL` )을 반환 하거나, [ICLRRuntimeInfo:: SetDefaultStartupFlags 메서드에](iclrruntimeinfo-setdefaultstartupflags-method.md)대 한 이전 호출에서 제공 된 값을 반환 하거나, `CorBind*` 이 런타임에 바인딩된 경우 메서드에 의해 설정 된 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
