---
title: CorSerializationType 열거형
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
ms.openlocfilehash: 649a9159f99afa64615c40c23a98a80318ae0d7f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009173"
---
# <a name="corserializationtype-enumeration"></a>CorSerializationType 열거형
공용 언어 런타임에 의해 개체가 serialize 되는 방법을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|개체의 Serialization이 정의 되지 않았습니다.|  
|`SERIALIZATION_TYPE_BOOLEAN`|개체는 부울 형식으로 직렬화 됩니다.|  
|`SERIALIZATION_TYPE_CHAR`|개체는 문자 형식으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I1`|개체는 부호 있는 1 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U1`|개체는 부호 없는 1 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I2`|개체는 부호 있는 2 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U2`|개체는 부호 없는 2 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I4`|개체는 부호 있는 4 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U4`|개체는 부호 없는 4 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I8`|개체는 부호 있는 8 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U8`|개체는 부호 없는 8 바이트 정수로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_R4`|개체가 4 바이트 부동 소수점으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_R8`|개체가 8 바이트 부동 소수점으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_STRING`|개체는 System.string 형식으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_SZARRAY`|개체는 0이 아닌 1 차원 배열로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_TYPE`|개체가 제네릭 형식으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|개체가 태그가 지정 된 개체로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_FIELD`|개체가 필드로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_PROPERTY`|개체는 속성으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_ENUM`|개체가 열거형으로 serialize 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
