---
title: ICorDebugManagedCallback2::ChangeConnection 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 7d209b7c319baff912b3462f8ed5f3f30f127750
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501913"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection 메서드
지정 된 연결과 관련 된 작업 집합이 변경 되었음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pProcess`  
 진행 변경 된 연결을 포함 하는 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.  
  
 `dwConnectionId`  
 진행 변경 된 연결의 ID입니다.  
  
## <a name="remarks"></a>설명  
 `ChangeConnection`콜백은 다음 중 한 가지 경우에 발생 합니다.  
  
- 디버거가 연결을 포함 하는 프로세스에 연결 하는 경우 이 경우 런타임은 프로세스의 각 연결에 대해 [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) 이벤트와 이벤트를 생성 하 고 디스패치합니다 `ChangeConnection` . `ChangeConnection`연결의 태스크 집합이 생성 된 후 변경 되었는지 여부에 관계 없이 모든 기존 연결에 대해 이벤트가 생성 됩니다.  
  
- 호스트가 [호스팅 API](../hosting/index.md)에서 [ICLRDebugManager:: setconnectiontasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) 를 호출 하는 경우  
  
 디버거는 프로세스의 모든 스레드를 검색 하 여 새 변경 내용을 선택 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugManagedCallback2 인터페이스](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
