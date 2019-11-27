---
title: ICorProfilerInfo3::GetFunctionLeave3Info 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: bacb50520df9f1553226ec6bf1e878238b64bb17
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449713"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a>ICorProfilerInfo3::GetFunctionLeave3Info 메서드
[FunctionLeave3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) 함수를 통해 프로파일러에 보고 하는 함수의 스택 프레임 및 반환 값을 제공 합니다. 이 함수는 `FunctionLeave3WithInfo` 콜백 중에만 호출할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 진행 을 반환 하는 함수의 `FunctionID`입니다.  
  
 `eltInfo`  
 [in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다. 프로파일러는 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) 함수에 의해 프로파일러에 지정 된 것과 동일한 `eltInfo`를 제공 해야 합니다.  
  
 `pFrameInfo`  
 [out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다. 이 핸들은 프로파일러가 `FunctionLeave3WithInfo` 메서드를 호출한 `GetFunctionLeave3Info` 콜백 중에만 유효합니다.  
  
 `pRetvalRange`  
 제한이 함수에서 반환 되는 값을 포함 하는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 구조체에 대 한 포인터입니다. 반환 값 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다. 프로파일러는 [ICorProfilerInfo:: SetEventMask 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.  
  
## <a name="remarks"></a>주의  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
