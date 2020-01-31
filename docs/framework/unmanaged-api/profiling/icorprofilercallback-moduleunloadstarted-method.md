---
title: ICorProfilerCallback::ModuleUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: 7e43f58f619aaa63fa2294dd3e989026dcdfc604
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866132"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a>ICorProfilerCallback::ModuleUnloadStarted 메서드
모듈이 언로드되고 있음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 진행 언로드될 모듈의 ID입니다.  
  
## <a name="remarks"></a>주의  
 `moduleId` 값은 `ModuleUnloadStarted` 메서드가 반환 된 후 정보 요청에 대해 유효 하지 않습니다 .이는이 모듈에 대 한 정보를 가져올 수 있는 프로파일러의 마지막 기회입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ModuleUnloadFinished 메서드](icorprofilercallback-moduleunloadfinished-method.md)
