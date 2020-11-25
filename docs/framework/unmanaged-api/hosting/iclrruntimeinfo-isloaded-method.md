---
title: ICLRRuntimeInfo::IsLoaded 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 66ae74deba9ceab9d1ea6b2c0b96a87bf44f32ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714928"
---
# <a name="iclrruntimeinfoisloaded-method"></a>ICLRRuntimeInfo::IsLoaded 메서드

[ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스와 연결 된 CLR (공용 언어 런타임)이 프로세스에 로드 되는지 여부를 나타냅니다. 런타임을 시작 하지 않고도 로드할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>매개 변수  

 `hndProcess`  
 진행 프로세스에 대 한 핸들입니다.  
  
 `pbLoaded`  
 [out] `true` CLR이 프로세스에 로드 되 면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pbLoaded`가 null입니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 다음 함수와 인터페이스와 이전 버전과 호환 됩니다.  
  
- [ICorRuntimeHost](icorruntimehost-interface.md) 인터페이스 (.NET Framework 버전 1 호스팅 API)  
  
- [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스 (.NET Framework 2.0 호스팅 API)  
  
- 사용 되지 않는 `CorBindTo*` 함수 (.NET Framework 2.0 호스팅 API에서 [사용 되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md) 참조)  
  
 호스트는 CorBindToRuntime 함수와 같은 사용 되지 않는 함수 중 하나를 호출 `CorBindTo*` 하 여 특정 버전의 CLR을 인스턴스화할 수 있습니다. [CorBindToRuntime](corbindtoruntime-function.md) 그러면 호스트에서 [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) 메서드를 호출 하 고 동일한 버전 번호를 지정 하 여 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스를 가져올 수 있습니다.  
  
 그런 다음 호스트에서 반환 된 `IsLoaded` [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스에 대해 메서드를 호출 하면 `pbLoaded` 이 반환 되 고, `true` 그렇지 않으면를 반환 `false` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
