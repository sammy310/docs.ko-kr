---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: d40cb424306535cc502d930dd61e6a1e254667da
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496180"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a>ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 메서드
관리 되는 함수의 [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 후크에 대해 호출 되는 프로파일러 구현 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFuncEnter3`  
 진행 콜백으로 사용할 구현에 대 한 포인터 `FunctionEnter3WithInfo` 입니다.  
  
 `pFuncLeave3`  
 진행 콜백으로 사용할 구현에 대 한 포인터 `FunctionLeave3WithInfo` 입니다.  
  
 `pFuncTailcall3`  
 진행 콜백으로 사용할 구현에 대 한 포인터 `FunctionTailcall3WithInfo` 입니다.  
  
## <a name="remarks"></a>설명  
 [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 후크는 스택 프레임 및 인수 검사를 제공 합니다. 이 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_ARGS` , `COR_PRF_ENABLE_FUNCTION_RETVAL` 및/또는 플래그를 `COR_PRF_ENABLE_FRAME_INFO` 설정 해야 합니다. 프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정한 다음 메서드를 사용 하 여 `SetEnterLeaveFunctionHooks3WithInfo` 이 함수의 구현을 등록할 수 있습니다.  
  
 한 번에 하나의 콜백 집합만 활성 상태일 수 있으며 최신 버전이 우선적으로 적용 됩니다. 따라서 프로파일러가 [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) 및를 모두 호출 하면 `SetEnterLeaveFunctionHooks3WithInfo` `SetEnterLeaveFunctionHooks3WithInfo` 이 사용 됩니다.  
  
 `SetEnterLeaveFunctionHooks3WithInfo`메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
- [ICorProfilerInfo3 인터페이스](icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
