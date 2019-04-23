---
title: ICorProfilerInfo::SetFunctionIDMapper 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cbbe85a99d0c78bd3d95ee654bdc13e376d017d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125226"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a>ICorProfilerInfo::SetFunctionIDMapper 메서드
`FunctionID` 값을 대체 값에 매핑하기 위해 호출되는 프로파일러 구현 함수를 지정합니다. 대체 값은 프로파일러의 함수 진입점/종료점 후크에 전달됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFunc`  
 [in] 에 대 한 포인터를 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 매핑할 호출 되는 구현 된 `FunctionID` 대체 값으로 값.  
  
## <a name="remarks"></a>설명  
 에 대 한 대안을 `FunctionID` 값은 프로파일러의 함수 항목/종료 점 후크에 전달 됩니다 ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)를 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), 및 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) 지정 된 된 [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) 메서드.  
  
 합니다 `FunctionIDMapper` 한 번만 설정할 수 있으며 설정 하는 것이 좋습니다. 합니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
