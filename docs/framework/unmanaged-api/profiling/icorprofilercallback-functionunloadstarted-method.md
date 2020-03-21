---
title: ICorProfilerCallback::FunctionUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: 988843559e55cc4cacd2a40bb3e6ac51721e99b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175163"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a>ICorProfilerCallback::FunctionUnloadStarted 메서드
런타임이 함수를 언로드하기 시작했다는 프로파일러를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 언로드 중인 함수의 ID입니다.

## <a name="remarks"></a>설명  
 이 메서드가 `functionId` 호출자에게 반환된 후 매개 변수 값이 더 이상 유효하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
