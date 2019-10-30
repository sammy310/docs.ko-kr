---
title: ICorDebugController::Detach 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: b98077914d680c908587649fdd517aca9c8dcd40
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125435"
---
# <a name="icordebugcontrollerdetach-method"></a>ICorDebugController::Detach 메서드
프로세스 또는 응용 프로그램 도메인에서 디버거를 분리 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>주의  
 프로세스 또는 응용 프로그램 도메인은 계속 정상적으로 실행 되지만 "ICorDebugProcess" 또는 "ICorDebugAppDomain" 개체는 더 이상 유효 하지 않으며 추가 콜백이 발생 하지 않습니다.  
  
 .NET Framework 버전 2.0에서는 관리 되지 않는 디버깅을 사용 하도록 설정한 경우 운영 체제 제한으로 인해이 메서드가 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
