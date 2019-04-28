---
title: COR_ARRAY_LAYOUT 구조체
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a5a5bb26912c87cdf37ba0d8f0cee1cf1ffa97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609570"
---
# <a name="corarraylayout-structure"></a>COR_ARRAY_LAYOUT 구조체
메모리 내 배열 개체의 레이아웃에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`componentID`|배열에 포함 된 개체 형식의 식별자입니다.|  
|`componentType`|가비지 컬렉션 참조, 값 클래스 또는 기본 구성 요소 인지 여부를 나타내는 CorElementType 열거형 값입니다.|  
|`firstElementOffset`|배열의 첫 번째 요소 오프셋입니다.|  
|`elementSize`|각 요소의 크기입니다.|  
|`countOffset`|오프셋 배열에서 요소의 수입니다.|  
|`rankSize`|크기 (바이트)에서 순위입니다.|  
|`numRanks`|배열의 순위 횟수입니다.|  
|`rankOffset`|순위는 시작 오프셋입니다.|  
  
## <a name="remarks"></a>설명  
 `rankSize` 필드 다차원 배열의 순위의 크기를 지정 합니다. 것도 1 차원 배열에 대해 정확 합니다.  
  
 변수의 `numRanks` 는 1 차원 배열에 대 한 1 및 `N` 다차원 배열에 `N` 차원입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
