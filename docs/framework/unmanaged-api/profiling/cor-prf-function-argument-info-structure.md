---
title: COR_PRF_FUNCTION_ARGUMENT_INFO 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: 5feda2ce6dc97576d0b1d4f16ca2b9dd5f3fb05e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718563"
---
# <a name="cor_prf_function_argument_info-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO 구조체

왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`numRanges`|인수의 블록 수입니다. 즉,이 값은 배열에 있는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) 구조체의 수입니다 `ranges` .|  
|`totalArgumentSize`|모든 인수의 전체 크기입니다. 즉,이 값은 인수 길이의 합계입니다.|  
|`ranges`|`COR_PRF_FUNCTION_ARGUMENT_RANGE`각각 하나의 함수 인수 블록을 나타내는 구조체의 배열입니다.|  
  
## <a name="remarks"></a>설명  

 함수에는 여러 개의 인수가 있을 수 있습니다. 이러한 인수는 메모리에 연속적으로 저장 되지 않을 수도 있습니다. 한 곳에 세 개의 인수 블록, 다른 위치의 두 인수 블록, 다른 위치의 한 인수에 대 한 최종 블록이 있을 수 있습니다. 이러한 인수는 모두 동일한 함수에 대해입니다. 다른 위치에 저장 됩니다.  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO`구조체는 단일 함수의 모든 인수를 나타냅니다. 배열을 사용 하 여 함수 인수의 모든 블록을 참조 합니다. 따라서 단일 함수의 경우 `COR_PRF_FUNCTION_ARGUMENT_INFO` `COR_PRF_FUNCTION_ARGUMENT_RANGE` 하나 이상의 함수 인수를 가리키는 여러 구조체를 참조 하는 단일 구조체가 있습니다.  
  
 레지스터에 저장 된 인수는 메모리에 분산 되어 구조를 작성 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 구조체](profiling-structures.md)
