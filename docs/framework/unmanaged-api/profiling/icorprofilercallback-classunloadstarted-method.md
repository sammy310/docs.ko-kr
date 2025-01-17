---
description: '자세히 알아보기: ICorProfilerCallback:: ClassUnloadStarted 메서드'
title: ICorProfilerCallback::ClassUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 91de255b2214ad0c6ce6911d9533df593142a191
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760679"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a>ICorProfilerCallback::ClassUnloadStarted 메서드

클래스가 언로드되고 있음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>매개 변수

`classId` 진행 언로드될 클래스를 식별 합니다.

## <a name="remarks"></a>설명  

 메서드가 반환 된 후에는 값이 `classId` 유효 하지 않습니다 .이는 `ClassUnloadStarted` 프로파일러에서이 클래스에 대 한 정보를 가져올 수 있는 마지막 기회입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ClassUnloadFinished 메서드](icorprofilercallback-classunloadfinished-method.md)
