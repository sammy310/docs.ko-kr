---
title: COR_PRF_EX_CLAUSE_INFO 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: 5c764031f709eefe61022d0662f37bc5d3f3e281
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501003"
---
# <a name="cor_prf_ex_clause_info-structure"></a>COR_PRF_EX_CLAUSE_INFO 구조체
특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`clauseType`|코드에서 방금 입력 하거나 남겨진 예외 절의 유형을 지정 하는 [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) 열거형의 값입니다.|  
|`programCounter`|절 처리기의 기본 진입점입니다 (예: X86 EIP 레지스터의 내용).|  
|`framePointer`|절 처리기의 논리적 프레임에 대 한 포인터입니다 (예: X86 EBP 레지스터의 내용).|  
|`shadowStackPointer`|그림자 스택에 대 한 포인터입니다. 이 값은 BSP 레지스터의 내용이 며 IA64에만 적용 됩니다.|  
  
## <a name="remarks"></a>설명  
 예외 알림이 수신 되 면 [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) 를 사용 하 여 `catch` / `finally` 실행 되거나 방금 실행 된 예외 절 (/profilter)의 기본 주소 및 프레임 정보를 가져올 수 있습니다.  
  
 예외 절의 실행은 CLR (공용 언어 런타임)의 이러한 콜백과 관련이 있습니다.  
  
- [ICorProfilerCallback:: ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 구조체](profiling-structures.md)
