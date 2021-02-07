---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionSearchFunctionEnter 메서드'
title: ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: 6e77ab5dc8c15a1d0785fb83310183c0a4693225
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706190"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a>ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드

예외 처리의 검색 단계가 함수를 검색 하 여 현재 예외에 대 한 처리기를 시작 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 입력 한 함수의 ID입니다.
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ExceptionSearchFunctionLeave 메서드](icorprofilercallback-exceptionsearchfunctionleave-method.md)
