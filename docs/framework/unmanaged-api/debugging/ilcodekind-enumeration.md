---
title: ILCodeKind 열거형
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 553a92812f009ca1033f1bdcda0ea3722c5f01e3
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937832"
---
# <a name="ilcodekind-enumeration"></a>ILCodeKind 열거형
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수나 코드에 액세스할 수 있는지 여부를 지정하는 값을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Members  
  
|멤버 이름|설명|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|디버거가 ReJIT 계측의 정보에 액세스할 수 없습니다.|  
|`ILCODE_REJIT_IL`|디버거가 ReJIT 계측의 정보에 액세스할 수 있습니다.|  
  
## <a name="remarks"></a>주의  
 [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) 및 [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) 메서드에 `ILCodeKind` 열거형의 멤버를 전달하여 디버거가 프로파일러 ReJIT 계측에 추가된 변수에 액세스할 수 있는지 여부를 확인하고 디버거가 계측된 IL에 액세스할 수 있는지 여부를 확인하는 [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) 메서드  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [ICorDebugILFrame4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [ReJIT: 방법 가이드](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
