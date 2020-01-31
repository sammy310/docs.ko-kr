---
title: ICorProfilerCallback::ModuleAttachedToAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: cb342b1c328daca5b3cfc0440e6f276ae54e3ed8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866184"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly 메서드
모듈이 부모 어셈블리에 연결 되 고 있음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 진행 연결 되는 모듈의 ID입니다.  
  
 `AssemblyId`  
 진행 모듈이 연결 된 부모 어셈블리의 ID입니다.  
  
## <a name="remarks"></a>주의  
 모듈은 IAT (가져오기 주소 테이블)를 통해, `LoadLibrary`에 대 한 호출 또는 메타 데이터 참조를 통해 로드할 수 있습니다. 결과적으로 CLR (공용 언어 런타임) 로더는 모듈이 있는 어셈블리를 확인 하기 위한 여러 코드 경로를 포함 합니다. 따라서 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 를 호출한 후 모듈에서 해당 어셈블리를 인식 하지 못하면 부모 어셈블리 ID를 가져올 수 없습니다. `ModuleAttachedToAssembly` 메서드는 모듈이 부모 어셈블리에 연결 되 고 부모 어셈블리 ID를 가져올 수 있을 때 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
