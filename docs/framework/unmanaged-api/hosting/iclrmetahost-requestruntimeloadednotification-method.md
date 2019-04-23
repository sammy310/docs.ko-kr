---
title: ICLRMetaHost::RequestRuntimeLoadedNotification 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61fce3e06b5245872f7061716e8d995dd5f5043c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224886"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification 메서드
공용 언어 런타임 (CLR) 버전을 처음 로드 되었지만 아직 시작 하지 않은 경우 호출할 보장 되는 콜백 함수를 제공 합니다. 이 메서드를 대체 합니다 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pCallbackFunction`  
 [in] 새 런타임을 로드 되었을 때 호출 되는 콜백 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pCallbackFunction`가 null입니다.|  
  
## <a name="remarks"></a>설명  
 콜백은 다음과 같이 작동합니다.  
  
-   콜백은은 런타임을 처음 로드 될 때에 호출 됩니다.  
  
-   동일한 런타임 재진입 로드에 대 한 콜백이 호출 되지 않습니다.  
  
-   재진입 런타임 로드에 대 한 콜백 함수 호출에 serialize 됩니다.  
  
 콜백 함수에는 다음과 같은 프로토타입을 있습니다.  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 콜백 함수 프로토타입에 다음과 같습니다.  
  
-   `pfnCallbackThreadSet`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   `pfnCallbackThreadUnset`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 로드 하거나 다른 런타임이 재진입 방식으로 로드를 호스트 하려는 경우는 `pfnCallbackThreadSet` 고 `pfnCallbackThreadUnset` 콜백에서 함수는 다음과 같이 사용 해야 하는 제공 되는 매개 변수:  
  
-   `pfnCallbackThreadSet` 로드를 시도 되기 전에 런타임 부하를 일으킬 수 있는 스레드에서 호출 해야 합니다.  
  
-   `pfnCallbackThreadUnset` 스레드가 더 이상 이러한 런타임 로드 하면 때와 초기 콜백에서 반환 하기 전에 호출 해야 합니다.  
  
-   `pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 재진입은 모두입니다.  
  
> [!NOTE]
>  호스트 응용 프로그램을 호출 하지 않아야 `pfnCallbackThreadSet` 하 고 `pfnCallbackThreadUnset` 범위 밖에 서는 `pCallbackFunction` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRMetaHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
