---
title: FunctionEnter2 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440857"
---
# <a name="functionenter2-function"></a>FunctionEnter2 함수
컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다. 이 함수는 [Functionenter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) 함수를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `funcId`  
 진행 제어가 전달 되는 함수의 식별자입니다.  
  
 `clientData`  
 진행 이전에 [Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 함수를 사용 하 여 지정한 프로파일러에서 다시 매핑된 함수 식별자입니다.  
  
 `func`  
 진행 스택 프레임에 대 한 정보를 가리키는 `COR_PRF_FRAME_INFO` 값입니다.  
  
 프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.  
  
 `argumentInfo`  
 진행 함수의 인수 메모리에서 위치를 지정 하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) 구조체에 대 한 포인터입니다.  
  
 인수 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_ARGS` 플래그를 설정 해야 합니다. 프로파일러는 [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 값이 변경 되거나 제거 될 수 있으므로 `FunctionEnter2` 함수가 반환 된 후에는 `func` 및 `argumentInfo` 매개 변수의 값이 유효 하지 않습니다.  
  
 `FunctionEnter2` 함수는 콜백입니다. 구현 해야 합니다. 구현은 `__declspec`(`naked`) 저장소 클래스 특성을 사용 해야 합니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.  
  
- 항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
- 종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.  
  
 `FunctionEnter2` 구현은 가비지 수집을 지연 시킬 수 있으므로 차단 하면 안 됩니다. 스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다. 가비지 수집을 시도 하면 `FunctionEnter2` 반환 될 때까지 런타임이 차단 됩니다.  
  
 또한 `FunctionEnter2` 함수는 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
