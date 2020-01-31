---
title: ICorDebugFunction3::GetActiveReJitRequestILCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777735"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>ICorDebugFunction3::GetActiveReJitRequestILCode 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 활성 ReJIT 요청에서 IL을 포함 하는 [ICorDebugILCode](icordebugilcode-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppReJitedILCode`  
 활성 ReJIT 요청의 IL에 대한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 `ICorDebugFunction3` 개체가 나타내는 메서드에 활성 ReJIT 요청이 있으면 `ppReJitedILCode`는 해당 IL에 대한 포인터를 반환합니다. 활성 요청이 없는 경우 (일반적인 경우) `ppReJitedILCode`은 **null**입니다.  
  
 ReJIT 요청은 실행이 [ICorProfilerCallback4:: GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 메서드 호출에서 반환 된 후에만 활성화 됩니다. 이 요청에서는 JIT가 아직 컴파일되지 않았을 수 있으며 원래 코드 버전에서 스레드가 계속 실행 중일 수 있습니다. ReJIT 요청은 프로파일러에서 [ICorProfilerInfo4:: RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) 메서드를 호출 하는 동안 비활성화 됩니다. IL이 되돌려진 후에도 스레드는 JIT가 다시 컴파일된(ReJIT) 코드를 계속 실행할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugFunction3 인터페이스](icordebugfunction3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [ReJIT: 방법 가이드](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
