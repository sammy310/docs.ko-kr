---
description: '자세히 알아보기: ICorProfilerCallback:: AssemblyUnloadStarted 메서드'
title: ICorProfilerCallback::AssemblyUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 91c0b6a600a1c7c12905a7a9817e6e7e9601c3c0
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759471"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a>ICorProfilerCallback::AssemblyUnloadStarted 메서드

어셈블리가 언로드되고 있음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a>매개 변수

`assemblyId` 진행 언로드되고 있는 어셈블리를 식별 합니다.

## <a name="remarks"></a>설명  

 메서드가 반환 된 후의 값은 `assemblyId` 정보 요청에 적합 하지 않습니다 .이는 `AssemblyUnloadStarted` 프로파일러에서이 어셈블리에 대 한 정보를 가져올 수 있는 마지막 기회입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [AssemblyUnloadFinished 메서드](icorprofilercallback-assemblyunloadfinished-method.md)
