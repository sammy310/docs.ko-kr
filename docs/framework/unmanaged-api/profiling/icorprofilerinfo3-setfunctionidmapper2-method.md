---
title: ICorProfilerInfo3::SetFunctionIDMapper2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 107f596801832809e64088c85540c441e66189cf
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868475"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>ICorProfilerInfo3::SetFunctionIDMapper2 메서드
`FunctionID` 값을 대체 값에 매핑하기 위해 호출되는 프로파일러 구현 함수를 지정합니다. 대체 값은 프로파일러의 함수 진입점/종료점 후크에 전달됩니다. 이 메서드는 추가 데이터 매개 변수를 사용 하 여 [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) 메서드를 확장 합니다 .이 메서드는 프로파일러를 사용 하 여 런타임을 명확 하 게 구분할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFunc`  
 진행 `FunctionID` 값을 대체 값으로 매핑하기 위해 호출 되는 [FunctionIDMapper2](functionidmapper2-function.md) 구현에 대 한 포인터입니다.  
  
 `clientData`  
 진행 현재 런타임에서 만든 모든 [FunctionIDMapper2](functionidmapper2-function.md) 함수 호출에 전달 되는 포인터입니다. 프로파일러는이 정보를 사용 하 여 런타임 중에 구분할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>주의  
 FunctionID 값의 대안은 [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 또는 [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 메서드에서 지정 하는 프로파일러의 함수 진입/종료 후크 ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md) 및 [FunctionTailcall3](functiontailcall3-function.md) 또는 [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md) 및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md))에 전달 됩니다.  
  
 `FunctionIDMapper2` 메서드는 한 번만 설정할 수 있습니다. [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서 설정 하는 것이 좋습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3 인터페이스](icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
