---
title: ASM_DISPLAY_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
ms.openlocfilehash: ebaab57b647250823443b48d9e45921036372d5e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176606"
---
# <a name="asm_display_flags-enumeration"></a>ASM_DISPLAY_FLAGS 열거형
[IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) 메서드에 의해 검색되는 어셈블리의 버전, 빌드, 문화권, 서명 등을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =
                      ASM_DISPLAYF_VERSION           |
                      ASM_DISPLAYF_CULTURE           |
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |
                      ASM_DISPLAYF_RETARGET          |
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a>설명  
 `ASM_DISPLAYF_FULL`는 [IAssemblyName](iassemblyname-interface.md) 개체 버전에 대한 변경 내용을 반영합니다. 반환된 값이 변경할 수 없다고 가정하지 마십시오.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 퓨전.h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [Fusion 열거형](fusion-enumerations.md)
