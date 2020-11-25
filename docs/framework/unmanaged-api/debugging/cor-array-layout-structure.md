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
ms.openlocfilehash: 2ca6c89a671c4d7882e7cefdb820d07ac5636530
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727408"
---
# <a name="cor_array_layout-structure"></a>COR_ARRAY_LAYOUT 구조체

메모리 내 배열 개체의 레이아웃에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
|`componentType`|구성 요소가 가비지 컬렉션 참조, 값 클래스 또는 기본 형식 인지 여부를 나타내는 CorElementType 열거형 값입니다.|  
|`firstElementOffset`|배열의 첫 번째 요소에 대 한 오프셋입니다.|  
|`elementSize`|각 요소의 크기입니다.|  
|`countOffset`|배열의 요소 수에 대 한 오프셋입니다.|  
|`rankSize`|순위 크기 (바이트)입니다.|  
|`numRanks`|배열의 순위 수입니다.|  
|`rankOffset`|순위가 시작 되는 오프셋입니다.|  
  
## <a name="remarks"></a>설명  

 `rankSize`필드는 다차원 배열에서 순위 크기를 지정 합니다. 1 차원 배열에 대해서도 정확 합니다.  
  
 값은 `numRanks` 1 차원 배열 및 `N` 차원의 다차원 배열에 대해 1입니다 `N` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
