---
description: '자세히 알아보기: INotifySink2:: OnSyncCallOut 메서드'
title: INotifySink2::OnSyncCallOut 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: 03028b138a7d95c618ae20530f66aa692d314cab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800242"
---
# <a name="inotifysink2onsynccallout-method"></a>INotifySink2::OnSyncCallOut 메서드

호출이 호출 될 때 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `in_CallID`  
 진행 Out 호출의 ID입니다. [CALL_ID 구조체](call-id-structure.md)를 참조 하세요.  
  
 `out_ppBuffer`  
 제한이 버퍼를 호출 합니다.  
  
 `out_pBufferSize`  
 제한이 호출 버퍼의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [INotifySink2 인터페이스](inotifysink2-interface.md)
- [INotifySource2 인터페이스](inotifysource2-interface.md)
- [INotifyConnection2 인터페이스](inotifyconnection2-interface.md)
