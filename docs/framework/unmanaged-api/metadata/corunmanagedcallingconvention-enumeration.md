---
title: CorUnmanagedCallingConvention 열거형
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 58d30e71929d314ee36adb9f83270858ff8a161b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442444"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention 열거형
Specifies the calling conventions for unmanaged code.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|The C language calling convention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|The standard calling convention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|The "this" calling convention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|The "fast" calling convention.|  
|`IMAGE_CEE_CS_CALLCONV_C`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|사용되지 않습니다.|  
  
## <a name="remarks"></a>주의  
 The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **Header:** CorHdr.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
