---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44a4b5903cec2249eb1e176381fe3d8e600dd5e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046113"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention 열거형
관리 코드에서 수행된 호출 규칙의 형식을 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|기본 호출 규칙을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|메서드는 가변 개수의 매개 변수를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|필드에 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|로컬 메서드 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|속성 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|관리 되지 않는 호출을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|제네릭 메서드 인스턴스를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|64 비트 PInvoke 호출에 가변 개수의 매개 변수를 사용 하는 메서드를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|잘못 된 4 비트 값을 설명합니다.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|호출 규칙 하위 4 비트에서 설명한 있는지를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|최상위 비트 설명 나타냅니다는 `this` 매개 변수입니다.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|나타내는 `this` 매개 변수는 서명에서 명시적으로 설명 합니다.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|명시적 개수의 형식 인수를 사용 하 여 제네릭 메서드 시그니처를 나타냅니다. 이 일반 매개 변수 개수를 앞에 옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorHdr.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
