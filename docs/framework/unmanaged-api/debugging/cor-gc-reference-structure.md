---
title: COR_GC_REFERENCE 구조체
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1e31e95473136bf7e7c196eacc278fa8a1caab2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093659"
---
# <a name="corgcreference-structure"></a>COR_GC_REFERENCE 구조체
가비지 수집할 개체에 대한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`domain`|핸들 또는 개체가 속한 응용 프로그램 도메인에 대 한 포인터입니다. 해당 값 `null`합니다.|  
|`location`|ICorDebugValue 또는 가비지 수집 개체에 해당 하는 ICorDebugReferenceValue 인터페이스입니다.|  
|`type`|A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 루트에서 발생 한 위치를 나타내는 열거형 값입니다. 자세한 내용은 설명 섹션을 참조하세요.|  
|`extraData`|가비지 수집 되기를 개체에 대 한 추가 데이터입니다. 명시 된 개체의 원본에 따라 달라 집니다이 정보는 `type` 필드입니다. 자세한 내용은 설명 섹션을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 합니다 `type` 필드를 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 참조에서 제공 하는 위치를 나타내는 열거형 값입니다. 특정 `COR_GC_REFERENCE` 값에는 다음과 같은 유형의 관리 되는 개체를 반영할 수 있습니다.  
  
-   모든 관리 되는 스택 개체 (`CorGCReferenceType.CorReferenceStack`). 공용 언어 런타임에서 생성 된 개체를 비롯 하 여 관리 코드에 대 한 라이브 참조가 포함 됩니다.  
  
-   개체 핸들 테이블의 (`CorGCReferenceType.CorHandle*`). 여기에 강력한 참조 (`HNDTYPE_STRONG` 및 `HNDTYPE_REFCOUNT`) 및 모듈의 정적 변수.  
  
-   종료자 큐에서 개체 (`CorGCReferenceType.CorReferenceFinalizer`). 종료자 큐는 종료 자가 실행 될 때까지 개체 루트입니다.  
  
 `extraData` 필드 참조의 원본 (또는 유형)에 따라 추가 데이터를 포함 합니다. 가능한 값은 다음과 같습니다.  
  
-   `DependentSource`. 경우는 `type` 됩니다 `CorGCREferenceType.CorHandleStrongDependent`,이 필드는 활성 상태로 유지 하는 경우 루트 개체에서 가비지 수집 되도록 하는 개체 `COR_GC_REFERENCE.Location`합니다.  
  
-   `RefCount`. 경우는 `type` 는 `CorGCREferenceType.CorHandleStrongRefCount`,이 필드는 핸들의 참조 횟수입니다.  
  
-   `Size`. 경우는 `type` 는 `CorGCREferenceType.CorHandleStrongSizedByref`,이 필드는 가비지 수집기가 개체 루트 계산 되는 개체 트리의 마지막 크기입니다. 이 계산은 반드시 최신는 참고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
