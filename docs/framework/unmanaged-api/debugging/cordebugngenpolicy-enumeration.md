---
title: CorDebugNGenPolicy 열거형
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: b64de0fa2ecbddd2decf69a4099d9897ec42a563
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696429"
---
# <a name="cordebugngenpolicy-enumeration"></a>CorDebugNGenPolicy 열거형

디버거가 네이티브 이미지 캐시에서 네이티브(NGen) 이미지를 로드하는지 여부를 결정하는 값을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>멤버  
  
|멤버 이름|설명|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|Windows 8.x 스토어 앱에서 로컬 네이티브 이미지 캐시의 이미지 사용은 사용 하지 않도록 설정 됩니다. 데스크톱 앱에서는이 설정이 적용 되지 않습니다.|  
  
## <a name="remarks"></a>설명  

 `CorDebugNGENPolicy`열거형은 [ICorDebugProcess5:: EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) 메서드에서 사용 됩니다. 로컬 네이티브 이미지 캐시에서 이미지를 사용 하지 않도록 설정 하면 디버거가 최적화 된 네이티브 이미지 대신 디버깅 가능한 JIT 컴파일된 이미지를 로드 하 여 일관 된 디버깅 환경을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
