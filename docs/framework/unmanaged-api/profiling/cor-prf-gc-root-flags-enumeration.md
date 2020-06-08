---
title: COR_PRF_GC_ROOT_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: bbc163c71b47e6fee0db89284d6e3fd27e882768
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500893"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS 열거형
가비지 컬렉션 루트의 속성을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|Root를 설정 하면 가비지 수집에서 개체를 이동할 수 없습니다.|  
|`COR_PRF_GC_ROOT_WEAKREF`|루트는 가비지 수집을 방지 하지 않습니다.|  
|`COR_PRF_GC_ROOT_INTERIOR`|루트는 개체 자체가 아니라 개체의 필드를 참조 합니다.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|개체의 참조 횟수가 특정 값 이면 루트는 가비지 수집을 방지 합니다.|  
  
## <a name="remarks"></a>설명  
 `COR_PRF_GC_ROOT_FLAGS`는 특정 루트에 대 한 추가 정보를 제공 하는 비트 마스크입니다. 그러나 모든 루트가 특수 한 것은 아닙니다. 예를 들어 일부 루트는 약한 참조, 내부 포인터, 고정 또는 참조 횟수가 계산 되지 않습니다. 이러한 루트의 경우 전달할 플래그가 없습니다. 따라서 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 메서드와 같이이 열거형을 사용 하는 메서드는 플래그 비트 마스크에 대해 0을 보내 모든 플래그가 해제 되어 있음을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](profiling-enumerations.md)
