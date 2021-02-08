---
description: '자세히 알아보기: ICorDebugModule:: EnableClassLoadCallbacks 메서드'
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
ms.openlocfilehash: 16516cceae9a10288f8660fa69d8e0c018953777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801087"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks 메서드

이 모듈에 대해 [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) 콜백이 호출 되는지 여부를 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `bClassLoadCallbacks`  
 진행 `true` `ICorDebugManagedCallback::LoadClass` 연결 된 이벤트가 발생할 때 CLR (공용 언어 런타임)에서 및 메서드를 호출할 수 있도록 하려면이 값을로 설정 `ICorDebugManagedCallback::UnloadClass` 합니다.  
  
 동적이 아닌 모듈의 경우 기본값은입니다 `false` . 동적 모듈의 경우이 값은 항상 이며 `true` 변경할 수 없습니다.  
  
## <a name="remarks"></a>설명  

 `ICorDebugManagedCallback::LoadClass`및 `ICorDebugManagedCallback::UnloadClass` 콜백은 동적 모듈에 대해 항상 사용할 수 있으며 비활성화할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목
