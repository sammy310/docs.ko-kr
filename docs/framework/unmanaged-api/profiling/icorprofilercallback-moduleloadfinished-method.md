---
title: ICorProfilerCallback::ModuleLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 5a29507ca56cac4ab800845e3a88706dc7a25379
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683994"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>ICorProfilerCallback::ModuleLoadFinished 메서드

모듈의 로드가 완료 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleId`  
 진행 로드가 완료 된 모듈의 ID입니다.  
  
 `hrStatus`  
 진행 모듈이 성공적으로 로드 되었는지 여부를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  

 `moduleId`메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다 `ModuleLoadFinished` .  
  
 모듈 로드의 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ModuleLoadFinished` . 의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다. 그러나의 성공 HRESULT는 `hrStatus` 모듈을 로드 한 첫 번째 부분이 성공 했다는 것을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ModuleLoadStarted 메서드](icorprofilercallback-moduleloadstarted-method.md)
