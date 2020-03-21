---
title: CorGenericParamAttr 열거형
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176177"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr 열거형
<xref:System.Type> [IMetaDataEmit2::DefineGenericParam에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)대한 호출에 사용되는 제네릭 형식에 대한 매개 변수를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`gpVarianceMask`|매개 변수 분산은 인터페이스 및 대리자에 대한 일반 매개 변수에만 적용됩니다.|  
|`gpNonVariant`|분산이 없는 것을 나타냅니다.|  
|`gpCovariant`|공분산을 나타냅니다.|  
|`gpContravariant`|모순을 나타냅니다.|  
|`gpSpecialConstraintMask`|특수 제약 조건은 <xref:System.Type> 모든 매개 변수에 적용할 수 있습니다.|  
|`gpNoSpecialConstraint`|매개 변수에 제약 <xref:System.Type> 조건이 적용되지 없음을 나타냅니다.|  
|`gpReferenceTypeConstraint`|매개 변수가 <xref:System.Type> 참조 형식이어야 함을 나타냅니다.|  
|`gpNotNullableValueTypeConstraint`|매개 변수는 <xref:System.Type> null 값이 될 수 없는 값 형식이어야 함을 나타냅니다.|  
|`gpDefaultConstructorConstraint`|매개 변수에는 <xref:System.Type> 매개 변수를 수행하지 않는 기본 공용 생성자가 있어야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르Hdr.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
