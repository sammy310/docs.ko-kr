---
description: '자세히 알아보기: ICorProfilerCallback:: ModuleAttachedToAssembly 메서드'
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
ms.openlocfilehash: cc6a83188a8bdc4826232aa6ff6e416cbb8ae893
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705582"
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
  
## <a name="remarks"></a>설명  

 모듈은 IAT (가져오기 주소 테이블)를 통해 또는 호출을 통해 `LoadLibrary` 또는 메타 데이터 참조를 통해 로드할 수 있습니다. 결과적으로 CLR (공용 언어 런타임) 로더는 모듈이 있는 어셈블리를 확인 하기 위한 여러 코드 경로를 포함 합니다. 따라서 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 를 호출한 후 모듈에서 해당 어셈블리를 인식 하지 못하면 부모 어셈블리 ID를 가져올 수 없습니다. `ModuleAttachedToAssembly`모듈을 부모 어셈블리에 연결 하 고 부모 어셈블리 ID를 가져올 수 있는 경우 메서드가 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
