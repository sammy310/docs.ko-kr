---
title: COR_FIELD_OFFSET 구조체
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 70fb637cd1edf81be140b0e3306e3b0a483653a6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007990"
---
# <a name="cor_field_offset-structure"></a>COR_FIELD_OFFSET 구조체
클래스 내에서 지정된 필드의 오프셋을 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`필드를 나타내는 메타 데이터 토큰입니다.|  
|`ulOffset`|클래스 내의 필드 오프셋입니다.|  
  
## <a name="remarks"></a>설명  
 [IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) 및 [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) 메서드는 형식의 매개 변수를 사용 `COR_FIELD_OFFSET` 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h, Corprof.idl  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 구조체](metadata-structures.md)
- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
