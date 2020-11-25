---
title: COR_TYPE_LAYOUT 구조체
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: f33c8f5cf218979404063342d9b1cc5123839f83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726329"
---
# <a name="cor_type_layout-structure"></a>COR_TYPE_LAYOUT 구조체

메모리 내 개체의 레이아웃에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`parentID`|이 형식에 대 한 부모 형식의 식별자입니다. 유형 id가에 해당 하는 경우 NULL 유형 id (token1 = 0, token2 = 0)가 됩니다 <xref:System.Object?displayProperty=nameWithType> .|  
|`objectSize`|이 형식의 개체에 대 한 기본 크기입니다. 가변 크기가 아닌 개체의 총 크기입니다.|  
|`numFields`|이 형식의 개체에 포함 된 필드 수입니다.|  
|`boxOffset`|이 형식이 boxed 이면 개체 필드의 시작 오프셋입니다. 이 필드는 기본 형식 및 구조체와 같은 값 형식에만 유효 합니다.|  
|`type`|이 형식이 속한 CorElementType입니다.|  
  
## <a name="remarks"></a>설명  

 `numFields`가 0 보다 큰 경우 [ICorDebugProcess5:: gettypefields](icordebugprocess5-gettypefields-method.md) 메서드를 호출 하 여이 형식의 필드에 대 한 정보를 가져올 수 있습니다. `type`가 `ELEMENT_TYPE_STRING` , 또는 이면 `ELEMENT_TYPE_ARRAY` `ELEMENT_TYPE_SZARRAY` 이 형식의 개체 크기는 변수이 고 [COR_TYPEID](cor-typeid-structure.md) 구조체를 [ICorDebugProcess5:: getarraylayout](icordebugprocess5-getarraylayout-method.md) 메서드에 전달할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
