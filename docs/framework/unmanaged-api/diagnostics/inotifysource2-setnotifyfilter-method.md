---
description: '자세히 알아보기: INotifySource2:: SetNotifyFilter 메서드'
title: INotifySource2::SetNotifyFilter 메서드
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 2aaf2a5253f8a9acb67c4b538f109a7a62559d12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800229"
---
# <a name="inotifysource2setnotifyfilter-method"></a>INotifySource2::SetNotifyFilter 메서드

이 원본에 사용할 알림 필터를 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `in_NotifyFilter`  
 진행 디버거 API에 대 한 콜백을 식별 하는 [NOTIFY_FILTER](notify-filter-enumeration.md) 열거형 값의 비트 조합입니다.  
  
 `in_pUserThreadFilter`  
 진행 디버거 API에 대 한 스레드를 식별 하는 [USER_THREAD](user-thread-structure.md) 구조체에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [INotifySource2 인터페이스](inotifysource2-interface.md)
- [INotifyConnection2 인터페이스](inotifyconnection2-interface.md)
- [INotifySink2 인터페이스](inotifysink2-interface.md)
