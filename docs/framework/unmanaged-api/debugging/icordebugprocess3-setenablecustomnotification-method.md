---
title: ICorDebugProcess3::SetEnableCustomNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: ec60274648315c4fa38f3832d8d39c1a269956b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129701"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification 메서드
지정 된 형식의 사용자 지정 디버거 알림을 사용 하거나 사용 하지 않도록 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pClass`  
 진행 사용자 지정 디버거 알림을 지정 하는 형식입니다.  
  
 `fEnable`  
 [in] 사용자 지정 디버거 알림을 사용 하도록 설정 하는 `true` 알림을 사용 하지 않도록 설정 하려면 `false` 합니다. 기본값은 `false`여야 합니다.  
  
## <a name="remarks"></a>주의  
 `fEnable`을 `true`로 설정 하면 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드를 호출 하 여 [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 콜백을 트리거합니다. 알림은 기본적으로 사용 하지 않도록 설정 되어 있습니다. 따라서 디버거가 인식 하 고 처리 하려는 알림 유형을 지정 해야 합니다. [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 클래스의 범위는 응용 프로그램 도메인에 따라 결정 되기 때문에 디버거는 전체 프로세스에서 알림을 받으려는 경우 프로세스의 모든 응용 프로그램 도메인에 대해 `SetEnableCustomNotification`를 호출 해야 합니다.  
  
 .NET Framework 4부터 유일 하 게 지원 되는 알림은 크로스 스레드 종속성 알림입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugProcess3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
