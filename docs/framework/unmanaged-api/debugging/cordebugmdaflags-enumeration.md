---
title: CorDebugMDAFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: 34a66a8afa118ecaaaeea0b7b78daaadf1da7509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778270"
---
# <a name="cordebugmdaflags-enumeration"></a>CorDebugMDAFlags 열거형
MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|Mda가 발생 한 스레드가 MDA가 실행 된 후에 누락 되었습니다.|  
  
## <a name="remarks"></a>주의  
 호출 스택에서 MDA가 원래 발생 한 위치를 더 이상 설명 하지 않는 경우 스레드는 *지연*된 것으로 간주 됩니다. 이는 스레드가 종료 될 때 잘못 된 작업을 실행 하 여 발생 하는 비정상적인 상황입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
