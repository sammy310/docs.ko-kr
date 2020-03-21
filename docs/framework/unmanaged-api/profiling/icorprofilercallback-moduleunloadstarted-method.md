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
ms.openlocfilehash: fcfdddbd5316c098754ea7b0d4714b050c64fe55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175150"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a>ICorProfilerCallback::ModuleUnloadStarted 메서드
프로파일러에 모듈이 언로드되고 있음을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 【인】 언로드 중인 모듈의 ID입니다.  
  
## <a name="remarks"></a>설명  
 메서드가 `moduleId` 반환된 후 정보 요청에 대한 값은 유효하지 않습니다. `ModuleUnloadStarted`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ModuleUnloadFinished 메서드](icorprofilercallback-moduleunloadfinished-method.md)
