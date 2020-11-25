---
title: ICorProfilerFunctionControl::SetCodegenFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 3593b07759b4d6feee239042e5aabaf0876fdd1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716306"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags 메서드

JIT (just in time) 컴파일 함수의 코드 생성을 제어 하기 위해 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 열거형에서 하나 이상의 플래그를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>매개 변수  

 `flags`  
 진행 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 열거형의 하나 이상의 플래그입니다.  
  
## <a name="remarks"></a>설명  

 프로파일러는 [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) 콜백을 통해이 인터페이스의 인스턴스를 가져옵니다. `SetCodegenFlags` 프로파일러가 다시 컴파일된 함수에 대 한 코드 생성을 제어할 수 있습니다. 다른 모든 JIT 재컴파일 매개 변수와 마찬가지로 코드 생성 플래그는 함수의 모든 인스턴스에 적용 됩니다.  
  
 JIT 컴파일러는 함수를 컴파일할 때 다른 원본에서 지정 된 다른 플래그와 함께 이러한 컴파일 플래그를 고려 합니다.  다른 원본에는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드 (값 `COR_PRF_DISABLE_INLINING` 및 `COR_PRF_DISABLE_OPTIMIZATIONS` )와 프로파일러의 [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) callback을 사용 하 여 시작 시 프로파일러에서 설정한 디버거, 전역 플래그가 포함 됩니다.  JIT 컴파일러는 최소한의 최적화를 요청 하는 소스에 우선 순위를 부여 합니다.  예를 들어 프로파일러가 `COR_PRF_DISABLE_INLINING` 시작 시를 지정 하지만 `COR_PRF_CODEGEN_DISABLE_INLINING` [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) 콜백에서를 지정 하지 않는 경우에도 인라이닝을 사용할 수 없습니다.  마찬가지로 프로파일러가에서을 지정 하지 않고 `COR_PRF_CODEGEN_DISABLE_INLINING` `SetCodegenFlags` [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) 콜백을 사용 하 여 인라이닝을 사용 하지 않도록 설정 하면 인라이닝을 사용 하지 않도록 설정 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerFunctionControl 인터페이스](icorprofilerfunctioncontrol-interface.md)
