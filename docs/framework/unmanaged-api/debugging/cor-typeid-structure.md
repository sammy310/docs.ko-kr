---
title: COR_TYPEID 구조체
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51104516008ffee0694c72733cb5f82b5ba6d8cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109865"
---
# <a name="cortypeid-structure"></a>COR_TYPEID 구조체
유형 식별자를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`token1`|첫 번째 토큰입니다.|  
|`token2`|두 번째 토큰입니다.|  
  
## <a name="remarks"></a>설명  
 `COR_TYPEID` 다양 한 개체를 가비지 수집에 대 한 정보를 제공 하는 방법 디버깅에서 반환 합니다. 그 다음 전달할 수 있습니다 인수로 서 해당 항목에 대 한 추가 정보를 제공 하는 다른 디버깅 방법. 예를 들어, 열거 하 여는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 개체를 개별 검색할 수 있습니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개별 관리 되는 힙의 개체를 나타내는 개체입니다. 전달할 수 있습니다는 `COR_TYPEID` 에서 값을 `COR_HEAPOBJECT.type` 필드를 합니다 [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 개체에 대 한 형식 정보를 제공 하는 ICorDebugType 개체를 검색 하는 방법.  
  
 `COR_TYPEID` 불투명 개체는 위한 것입니다. 개별 필드를 액세스 하거나 조작할 수 해야 합니다. 유일한 용도으로 제공 되는 식별자로는 `out` 수 있는 메서드 호출에 매개 변수를 전달할 수 다른 방법 추가 정보를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
