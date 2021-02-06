---
description: '자세히 알아보기: FunctionTailcall3WithInfo 함수'
title: FunctionTailcall3WithInfo 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: efa8b2e965ba4a365bbd72db4c5af69db006f6d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648508"
---
# <a name="functiontailcall3withinfo-function"></a>FunctionTailcall3WithInfo 함수

현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 [ICorProfilerInfo3:: GetFunctionTailcall3Info 메서드에](icorprofilerinfo3-getfunctiontailcall3info-method.md) 전달 하 여 스택 프레임을 검색 하는 핸들을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>매개 변수  

- `functionIDOrClientID`

  \[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.

- `eltInfo`

  \[in] 지정 된 스택 프레임에 대 한 정보를 나타내는 불투명 핸들입니다. 이 핸들은 전달 되는 콜백 중에만 유효 합니다.

## <a name="remarks"></a>설명  

 `FunctionTailcall3WithInfo`콜백 메서드는 함수가 호출 될 때 프로파일러에 게 알리고 [ICorProfilerInfo3:: GetFunctionTailcall3Info 메서드](icorprofilerinfo3-getfunctiontailcall3info-method.md) 를 사용 하 여 스택 프레임을 검사할 수 있습니다. 스택 프레임 정보에 액세스 하려면 `COR_PRF_ENABLE_FRAME_INFO` 플래그를 설정 해야 합니다. 프로파일러는 [ICorProfilerInfo:: SetEventMask 메서드](icorprofilerinfo-seteventmask-method.md) 를 사용 하 여 이벤트 플래그를 설정한 다음 [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo 메서드](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 를 사용 하 여이 함수의 구현을 등록할 수 있습니다.  
  
 `FunctionTailcall3WithInfo`함수는 콜백입니다. 함수를 구현 해야 합니다. 구현에서는 저장소 클래스 특성을 사용 해야 합니다 `__declspec(naked)` .  
  
 실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.  
  
- 항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
- 종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.  
  
 의 구현은 `FunctionTailcall3WithInfo` 가비지 수집을 지연 하므로를 차단 하면 안 됩니다. 스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다. 가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionTailcall3WithInfo` .  
  
 또한 FunctionTailcall3WithInfo 함수는 관리 코드를 호출 하거나 다른 방식으로 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functiontailcall3-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
