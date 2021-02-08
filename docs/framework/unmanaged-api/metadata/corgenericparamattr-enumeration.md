---
description: '다음에 대 한 자세한 정보: CorGenericParamAttr 열거형'
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
ms.openlocfilehash: 8fe8cb20834ecbc5477bbe8b01bf77d6b1af0eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784459"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr 열거형

<xref:System.Type> [IMetaDataEmit2::D efineGenericParam](imetadataemit2-definegenericparam-method.md)호출에 사용 되는 제네릭 형식에 대 한 매개 변수를 설명 하는 값을 포함 합니다.  
  
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
  
|멤버|설명|  
|------------|-----------------|  
|`gpVarianceMask`|매개 변수 분산은 인터페이스 및 대리자에 대 한 제네릭 매개 변수에만 적용 됩니다.|  
|`gpNonVariant`|분산이 없음을 나타냅니다.|  
|`gpCovariant`|공 분산을 나타냅니다.|  
|`gpContravariant`|반 공변성 (contravariance)을 나타냅니다.|  
|`gpSpecialConstraintMask`|특수 제약 조건은 모든 매개 변수에 적용할 수 있습니다 <xref:System.Type> .|  
|`gpNoSpecialConstraint`|매개 변수에 적용 되는 제약 조건이 없음을 나타냅니다 <xref:System.Type> .|  
|`gpReferenceTypeConstraint`|<xref:System.Type>매개 변수가 참조 형식 이어야 함을 나타냅니다.|  
|`gpNotNullableValueTypeConstraint`|<xref:System.Type>매개 변수가 null 값이 될 수 없는 값 형식 이어야 함을 나타냅니다.|  
|`gpDefaultConstructorConstraint`|매개 변수를 <xref:System.Type> 사용 하지 않는 기본 public 생성자가 매개 변수에 있어야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
