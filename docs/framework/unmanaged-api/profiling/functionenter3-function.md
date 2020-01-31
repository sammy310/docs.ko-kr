---
title: FunctionEnter3 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: 0ed7a0619816caab64361d7922d28b18c60ed453
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790266"
---
# <a name="functionenter3-function"></a>FunctionEnter3 함수
컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a>매개 변수

- `functionOrRemappedID`

  \[] 컨트롤을 전달할 함수의 식별자입니다.

## <a name="remarks"></a>주의  
 `FunctionEnter3` 콜백 함수는 함수가 호출 될 때 프로파일러에 알립니다. 하지만 인수 검사는 지원 하지 않습니다. [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 를 사용 하 여이 함수의 구현을 등록 합니다.  
  
 `FunctionEnter3` 함수는 콜백입니다. 구현 해야 합니다. 구현에서 `__declspec(naked)` 저장소 클래스 특성을 사용 해야 합니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.  
  
- 항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
- 종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
