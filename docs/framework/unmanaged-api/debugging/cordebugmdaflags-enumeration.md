---
description: '자세한 정보: CorDebugMDAFlags 열거'
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
ms.openlocfilehash: d7e9178d76286b112035729e997b1f68e2a93fb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661937"
---
# <a name="cordebugmdaflags-enumeration"></a>CorDebugMDAFlags 열거형

MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|Mda가 발생 한 스레드가 MDA가 실행 된 후에 누락 되었습니다.|  
  
## <a name="remarks"></a>설명  

 호출 스택에서 MDA가 원래 발생 한 위치를 더 이상 설명 하지 않는 경우 스레드는 *지연* 된 것으로 간주 됩니다. 이는 스레드가 종료 될 때 잘못 된 작업을 실행 하 여 발생 하는 비정상적인 상황입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 열거형](debugging-enumerations.md)
