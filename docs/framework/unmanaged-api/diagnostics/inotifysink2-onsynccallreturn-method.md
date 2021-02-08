---
description: '자세히 알아보기: INotifySink2:: OnSyncCallReturn 메서드'
title: INotifySink2::OnSyncCallReturn 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: 01518de4e5a9e1374edddadb3c49f16e8fe679a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800255"
---
# <a name="inotifysink2onsynccallreturn-method"></a>INotifySink2::OnSyncCallReturn 메서드

호출이 반환 될 때 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `in_CallID`  
 진행 에서 반환 되는 호출의 ID입니다. [CALL_ID 구조체](call-id-structure.md)를 참조 하세요.  
  
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
