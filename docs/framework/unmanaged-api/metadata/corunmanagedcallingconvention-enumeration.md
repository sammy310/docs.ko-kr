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
ms.openlocfilehash: 9d35f6b1928d714216b669704ec28e53895f6549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699068"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention 열거형

비관리 코드에 대 한 호출 규칙을 지정 합니다.  
  
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
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|C 언어 호출 규칙입니다.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|표준 호출 규칙입니다.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|"This" 호출 규칙입니다.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|"Fast" 호출 규칙입니다.|  
|`IMAGE_CEE_CS_CALLCONV_C`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|사용되지 않습니다.|  
  
## <a name="remarks"></a>설명  

 CLR은 .NET Framework 버전 1.0의 "fast" 호출 규칙을 지원 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](metadata-enumerations.md)
