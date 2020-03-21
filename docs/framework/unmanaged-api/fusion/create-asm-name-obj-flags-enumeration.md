---
title: CREATE_ASM_NAME_OBJ_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: ee856dbd398d0fa5e3eee7d9b2b2cfc7c7a57ecf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176593"
---
# <a name="create_asm_name_obj_flags-enumeration"></a>CREATE_ASM_NAME_OBJ_FLAGS 열거형
[IAssembly명 명 인터페이스](iassemblyname-interface.md) 개체가 [CreateAssemblyNameObject](createassemblynameobject-function.md) 함수에 의해 생성될 때 IAssemblyName 인터페이스 개체의 특성을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|전달된 매개 변수가 텍스트 ID임을 나타냅니다.|  
|`CANOF_SET_DEFAULT_VALUES`|몇 가지 기본값을 설정합니다.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|친구 어셈블리 규칙(이름 및 공개 키만)을 확인합니다. 이 멤버는 내부 용도로만 사용됩니다.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|`CANOF_PARSE_DISPLAY_NAME` 와 `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 플래그의 조합입니다. 이 멤버는 내부 용도로만 사용됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 퓨전.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [CreateAssemblyNameObject 함수](createassemblynameobject-function.md)
- [Fusion 열거형](fusion-enumerations.md)
