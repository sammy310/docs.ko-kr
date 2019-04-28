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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293ad30ebf47ca8684d158b1ae1772ab245d7981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775091"
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO 구조체
왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`numRanges`|인수는 블록의 수입니다. 즉,이 값은 수가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 구조는 `ranges` 배열입니다.|  
|`totalArgumentSize`|모든 인수가의 총 크기입니다. 즉,이 값은 인수 길이 합계입니다.|  
|`ranges`|배열을 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 하나 함수 인수 블록을 각각 나타내는 구조입니다.|  
  
## <a name="remarks"></a>설명  
 함수에는 많은 인수가 있을 수 있습니다. 메모리에 연속적으로 이러한 인수를 저장할 수 있습니다. 블록을 한 곳에서 세 개의 인수, 다른 위치에서 두 개의 인수 블록 및 다른 위치에 인수의 최종 블록을 배치 해야 합니다. 이 인수는 모두 동일한 함수의; 방금 다른 위치에 저장 합니다.  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO` 구조 단일 함수의 모든 인수를 나타냅니다. 배열을 사용 하 여 모든 함수 인수 블록 참조. 따라서 단일 있는 단일 함수에 대 한 `COR_PRF_FUNCTION_ARGUMENT_INFO` 여러 참조 하는 구조 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 구조를 각각 하나 이상의 함수 인수를 가리킵니다.  
  
 레지스터에 저장 되는 인수는 구조체를 메모리로 유출 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [프로파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
