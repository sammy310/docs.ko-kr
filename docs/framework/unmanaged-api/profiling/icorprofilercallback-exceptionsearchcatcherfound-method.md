---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionSearchCatcherFound 메서드'
title: ICorProfilerCallback::ExceptionSearchCatcherFound 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
ms.openlocfilehash: b222e629cbfce2fde27c2d266b3a343466a1419c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706320"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a>ICorProfilerCallback::ExceptionSearchCatcherFound 메서드

예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기를 찾을 때 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 예외 처리기를 포함 하는 함수의 ID입니다.

## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
