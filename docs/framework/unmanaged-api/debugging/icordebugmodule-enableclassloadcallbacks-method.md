---
title: ICorDebugModule::EnableClassLoadCallbacks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139215"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks 메서드
이 모듈에 대해 [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 콜백이 호출 되는지 여부를 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bClassLoadCallbacks`  
 진행 이 값을 `true` 설정 하 여 CLR (공용 언어 런타임)에서 `ICorDebugManagedCallback::LoadClass`를 호출 하 고 연결 된 이벤트가 발생할 때 메서드를 `ICorDebugManagedCallback::UnloadClass` 수 있도록 합니다.  
  
 비동적 모듈의 기본값은 `false`입니다. 동적 모듈의 경우 값이 항상 `true` 되며 변경할 수 없습니다.  
  
## <a name="remarks"></a>주의  
 `ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 콜백은 항상 동적 모듈에 대해 사용 하도록 설정 되며 사용 하지 않도록 설정할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조
