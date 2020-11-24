---
title: COR_PRF_GC_ROOT_KIND 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: e86074031b8fc2c82636e7aef2177eaf04a9db14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682369"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a>COR_PRF_GC_ROOT_KIND 열거형

[ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 콜백에서 노출 하는 가비지 수집 루트의 종류를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|루트는 스택의 변수입니다.|  
|`COR_PRF_GC_ROOT_FINALIZER`|루트는 종료자 큐의 항목입니다.|  
|`COR_PRF_GC_ROOT_HANDLE`|루트가 가비지 수집 핸들입니다.|  
|`COR_PRF_GC_ROOT_OTHER`|Root 종류가 지정 되지 않았습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
