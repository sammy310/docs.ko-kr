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
ms.openlocfilehash: 69c7e6c465de5b8185a86b3de6e5c29f902a1d1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440876"
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
 진행 입력 하는 호출의 ID입니다. [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)를 참조 하세요.  
  
 `in_pBuffer`  
 진행 버퍼를 호출 합니다.  
  
 `in_BufferSize`  
 진행 호출 버퍼의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고자료

- [INotifySink2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [INotifySource2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [INotifyConnection2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
