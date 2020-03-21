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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179321"
---
# <a name="cor_gc_reference-structure"></a>COR_GC_REFERENCE 구조체
가비지 수집할 개체에 대한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`domain`|핸들 또는 개체가 속한 응용 프로그램 도메인에 대한 포인터입니다. 해당 값은 `null`할 수 있습니다.|  
|`location`|ICorDebugValue 또는 가비지 수집할 개체에 해당하는 ICorDebugReferenceValue 인터페이스입니다.|  
|`type`|루트의 위치를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거 값입니다. 자세한 내용은 주의 섹션을 참조하세요.|  
|`extraData`|가비지 수집할 개체에 대한 추가 데이터입니다. 이 정보는 필드에 표시된 대로 개체의 소스에 `type` 따라 다릅니다. 자세한 내용은 주의 섹션을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 `type` 필드는 참조가 발생한 위치를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거 값입니다. 특정 `COR_GC_REFERENCE` 값은 다음과 같은 종류의 관리되는 개체를 반영할 수 있습니다.  
  
- 관리되는 모든 스택()의`CorGCReferenceType.CorReferenceStack`개체입니다. 여기에는 관리 코드의 라이브 참조와 공통 언어 런타임에 의해 생성된 개체가 포함됩니다.  
  
- 핸들 테이블 ()의`CorGCReferenceType.CorHandle*`개체입니다. 여기에는 모듈의`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`강력한 참조(및) 및 정적 변수가 포함됩니다.  
  
- 종료자 큐()의`CorGCReferenceType.CorReferenceFinalizer`개체입니다. 종료자 큐는 종료자가 실행될 때까지 개체를 루트합니다.  
  
 필드에는 `extraData` 참조의 원본(또는 형식)에 따라 추가 데이터가 포함되어 있습니다. 가능한 값은 다음과 같습니다.  
  
- `DependentSource`. 이 `type` `CorGCREferenceType.CorHandleStrongDependent`필드는 이 필드가 있는 경우 `COR_GC_REFERENCE.Location`에서 가비지 수집할 개체를 뿌리로 지정하는 개체입니다.  
  
- `RefCount`. 의 `type` `CorGCREferenceType.CorHandleStrongRefCount`경우 이 필드는 핸들의 참조 수입니다.  
  
- `Size`. 이 `type` `CorGCREferenceType.CorHandleStrongSizedByref`경우 이 필드는 가비지 수집기에서 개체 루트를 계산한 개체 트리의 마지막 크기입니다. 이 계산이 반드시 최신 날짜는 아닙니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
