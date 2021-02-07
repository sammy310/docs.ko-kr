---
description: 'ICorProfilerCallback2:: HandleDestroyed 메서드에 대해 자세히 알아보세요.'
title: ICorProfilerCallback2::HandleDestroyed 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
ms.openlocfilehash: d583a2170efbb4ebe72d7eacdd60af1a089a518f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705584"
---
# <a name="icorprofilercallback2handledestroyed-method"></a>ICorProfilerCallback2::HandleDestroyed 메서드

가비지 수집 핸들이 소멸 되었음을 코드 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a>매개 변수  

 `handleId`  
 진행 가비지 컬렉션에 대 한 핸들의 ID입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 인터페이스](icorprofilercallback2-interface.md)
