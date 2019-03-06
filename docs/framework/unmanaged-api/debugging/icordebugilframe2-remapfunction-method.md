---
title: ICorDebugILFrame2::RemapFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92885d2a6514839a864d6a345dd8af8b07b90c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489815"
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction 메서드
새 Microsoft MSIL (intermediate language) 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `newILOffset`  
 [in] 스택 프레임의 새 MSIL 오프셋 명령 포인터를 배치할입니다. 이 값에 시퀀스 포인트가 있어야 합니다.  
  
 이 값의 유효성을 확인 해야 하는 호출자의 경우 예를 들어, MSIL 오프셋 함수의 범위를 벗어난 경우에 올바르지 않습니다.  
  
## <a name="remarks"></a>설명  
 디버거에서 호출 프레임의 함수를 편집한 후에 `RemapFunction` 실행할 수 있도록 최신 버전의 프레임의 함수에서 교환 하는 방법입니다. 코드 실행의 지정 된 MSIL 오프셋에서 시작 됩니다.  
  
> [!NOTE]
>  호출 `RemapFunction`같은 호출 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), 스레드의 스택 추적을 생성 하려면 관련 된 모든 디버깅 인터페이스를 즉시 무효화 됩니다. 이러한 인터페이스를 포함 [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, 및 ICorDebugNativeFrame 합니다.  
  
 `RemapFunction` 현재 프레임의 컨텍스트에서만에서 및 다음 경우 중 하나에 메서드를 호출할 수 있습니다.  
  
-   수신 후는 [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) 계속 하지 아직 콜백입니다.  
  
-   때문에 코드 실행이 중지 된 동안는 [icordebugmanagedcallback:: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) 이 프레임에 대 한 이벤트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
