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
ms.openlocfilehash: 8c88e97f8187ac347f4ff39890c8d87ee80c8f9e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500717"
---
# <a name="functionenter2-function"></a>FunctionEnter2 함수
컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다. 이 함수는 [Functionenter](functionenter-function.md) 함수를 대체 합니다.  
  
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

- `funcId`

  \[in] 컨트롤이 전달 되는 함수의 식별자입니다.

- `clientData`

  \[in] 이전에 [Functionidmapper](functionidmapper-function.md) 함수를 사용 하 여 지정한 프로파일러에서 다시 매핑된 함수 식별자입니다.
  
- `func`

  \[in] `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.
  
  프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.  
  
- `argumentInfo`

  \[in] 함수 인수의 메모리에서 위치를 지정 하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조체에 대 한 포인터입니다.

  인수 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_ARGS` 플래그를 설정 해야 합니다. 프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.

## <a name="remarks"></a>설명  
 `func` `argumentInfo` `FunctionEnter2` 값이 변경 되거나 제거 될 수 있으므로 함수에서를 반환한 후에는 및 매개 변수의 값이 유효 하지 않습니다.  
  
 `FunctionEnter2`함수는 콜백입니다. 함수를 구현 해야 합니다. 구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.  
  
- 항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
- 종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.  
  
 의 구현은 `FunctionEnter2` 가비지 수집을 지연 하므로 차단 하면 안 됩니다. 스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다. 가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionEnter2` .  
  
 또한 함수는 관리 `FunctionEnter2` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [FunctionLeave2 함수](functionleave2-function.md)
- [FunctionTailcall2 함수](functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
