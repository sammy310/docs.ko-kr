---
title: ICorProfilerCallback::ThreadCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a26faf4f648107e7062a723663877b5b6a8e76e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497160"
---
# <a name="icorprofilercallbackthreadcreated-method"></a>ICorProfilerCallback::ThreadCreated 메서드
스레드 생성 되어 있는지를 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a>매개 변수  
 `threadId`  
 [in] 만들어진 스레드의 ID입니다.  
  
## <a name="remarks"></a>설명  
 `threadId` 값이 즉시 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ThreadDestroyed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
