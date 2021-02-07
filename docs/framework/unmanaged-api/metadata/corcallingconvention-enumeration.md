---
description: '다음에 대 한 자세한 정보: CorCallingConvention 열거형'
title: CorCallingConvention 열거형
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
ms.openlocfilehash: 2e823fe3566ef7a54f759cd5debbbd7d5dcf3ceb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678447"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention 열거형

관리 코드에서 수행된 호출 규칙의 형식을 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|기본 호출 규칙을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|메서드가 가변적인 개수의 매개 변수를 사용 함을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|필드에 대 한 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|로컬 메서드에 대 한 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|속성에 대 한 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|호출이 관리 되지 않음을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|제네릭 메서드 인스턴스화를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|가변 개수의 매개 변수를 사용 하는 메서드에 대 한 64 비트 PInvoke 호출을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|잘못 된 4 비트 값을 설명 합니다.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|호출 규칙이 아래쪽 4 비트로 설명 됨을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|상위 비트가 매개 변수를 설명 함을 나타냅니다 `this` .|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|`this`매개 변수가 시그니처에 명시적으로 설명 됨을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|명시적 개수의 형식 인수가 있는 제네릭 메서드 시그니처를 나타냅니다. 이는 일반 매개 변수 개수 앞에 나옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
