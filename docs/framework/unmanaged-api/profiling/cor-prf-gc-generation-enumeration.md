---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_GC_GENERATION'
title: COR_PRF_GC_GENERATION 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: 108bb4b2b4cba57235d354efe3b815a0e0df17ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648937"
---
# <a name="cor_prf_gc_generation-enumeration"></a>COR_PRF_GC_GENERATION 열거형

가비지 컬렉션 생성을 식별 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|개체는 0 세대로 저장 됩니다.|  
|`COR_PRF_GC_GEN_1`|개체는 1 세대로 저장 됩니다.|  
|`COR_PRF_GC_GEN_2`|개체는 2 세대로 저장 됩니다.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|개체가 대량 개체 힙에 저장 됩니다.|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|개체는 고정 개체 힙에 저장 됩니다.|  
  
## <a name="remarks"></a>설명  

 가비지 수집기는 개체를 age를 기반으로 하는 세대로 분할 하 여 메모리 관리 성능을 향상 시킵니다. 가비지 수집기는 현재 세 세대 (0, 1, 2) 및 두 개의 특수 힙 세그먼트를 사용 합니다. 하나는 큰 개체이 고 다른 하나는 고정 된 개체에 대 한 것입니다.
  
 크기가 임계값 보다 큰 개체는 큰 개체 힙에 저장 됩니다. 고정 된 개체는 고정 개체 힙에 할당 되어 일반 힙에 할당 되는 성능 비용을 피할 수 있습니다. 할당 된 다른 개체는 0 세대에 속하는 것으로 시작 합니다. 0 세대에서 가비지 수집 후에 존재 하는 모든 개체는 1 세대로 승격 됩니다. 1 세대에서 가비지 수집이 수행 된 후 존재 하는 개체는 2 세대로 이동 합니다.  
  
 세대를 사용 하면 가비지 수집기에서 한 번에 할당 된 개체의 하위 집합만 작업 해야 합니다.  
  
 `COR_PRF_GC_GENERATION`열거형은 [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) 구조에서 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](profiling-enumerations.md)
