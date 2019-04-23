---
title: COR_ACTIVE_FUNCTION 구조체
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0400da0cd29d642a1be42be7e2b22213ae54b94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121773"
---
# <a name="coractivefunction-structure"></a>COR_ACTIVE_FUNCTION 구조체
스레드 프레임에서 현재 활성 상태인 함수에 대한 정보를 포함합니다. 이 구조체를 사용 합니다 [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pAppDomain`|응용 프로그램 도메인 소유자에 대 한 포인터를 `ilOffset` 필드입니다.|  
|`pModule`|모듈 소유자에 대 한 포인터를 `ilOffset` 필드입니다.|  
|`pFunction`|함수 소유자에 대 한 포인터를 `ilOffset` 필드입니다.|  
|`ilOffset`|프레임의 Microsoft MSIL (intermediate language) 오프셋입니다.|  
|`flags`|향후 확장성을 위해 예약 되어 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
