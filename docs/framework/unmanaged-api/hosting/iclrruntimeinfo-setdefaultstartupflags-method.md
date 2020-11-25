---
title: ICLRRuntimeInfo::SetDefaultStartupFlags 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 8020db491c3b66be38a9f6cbcb7551721859dcd5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723118"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>ICLRRuntimeInfo::SetDefaultStartupFlags 메서드

런타임을 시작 하는 데 사용 되는 시작 플래그와 호스트 구성 파일을 설정 합니다. 이 메서드는 `startupFlags` [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 및 [CorBindToRuntimeHost](corbindtoruntimehost-function.md) 함수에서 매개 변수의 사용을 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwStartupFlags`  
 진행 설정할 호스트 시작 플래그입니다. [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 및 [CorBindToRuntimeHost](corbindtoruntimehost-function.md) 함수와 동일한 플래그를 사용 합니다.  
  
 `pwzHostConfigFile`  
 진행 설정할 호스트 구성 파일의 디렉터리 경로입니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 다음과 같은 특정 HRESULT 및 메서드 오류를 나타내는 HRESULT 오류를 반환 합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
  
## <a name="remarks"></a>설명  

 다중 스레드 호스트는이 메서드에 대 한 호출을 동기화 해야 합니다. 그렇지 않으면 스레드 `SetStartupFlags` b가에 대 한 호출을 완료 하 `SetStartupFlags` 고 스레드 b가 런타임을 시작 하기 전에 메서드를 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
