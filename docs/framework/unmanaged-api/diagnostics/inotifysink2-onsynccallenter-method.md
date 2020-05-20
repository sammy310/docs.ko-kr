---
title: INotifySink2::OnSyncCallEnter 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 85f00698f42f120b209cca14f293a58ae4c65f6f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442035"
---
# <a name="inotifysink2onsynccallenter-method"></a>INotifySink2::OnSyncCallEnter 메서드
호출을 입력할 때 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `in_CallID`  
 진행 입력 하는 호출의 ID입니다. [CALL_ID 구조체](call-id-structure.md)를 참조 하세요.  
  
 `in_pBuffer`  
 진행 버퍼를 호출 합니다.  
  
 `in_BufferSize`  
 진행 호출 버퍼의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [INotifySink2 인터페이스](inotifysink2-interface.md)
- [INotifySource2 인터페이스](inotifysource2-interface.md)
- [INotifyConnection2 인터페이스](inotifyconnection2-interface.md)
