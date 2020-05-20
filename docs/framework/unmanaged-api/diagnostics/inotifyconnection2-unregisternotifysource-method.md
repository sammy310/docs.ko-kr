---
title: INotifyConnection2::UnregisterNotifySource 메서드
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442048"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource 메서드
지정 된 알림 소스 개체를 연결에서 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `in_pNotifySource`  
 진행 등록을 취소할 알림 개체입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [INotifyConnection2 인터페이스](inotifyconnection2-interface.md)
- [INotifySource2 인터페이스](inotifysource2-interface.md)
- [INotifySink2 인터페이스](inotifysink2-interface.md)
- [RegisterNotifySource 메서드](inotifyconnection2-registernotifysource-method.md)
