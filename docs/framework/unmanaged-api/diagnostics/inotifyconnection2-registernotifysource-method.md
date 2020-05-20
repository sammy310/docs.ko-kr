---
title: INotifyConnection2::RegisterNotifySource 메서드
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442074"
---
# <a name="inotifyconnection2registernotifysource-method"></a>INotifyConnection2::RegisterNotifySource 메서드
지정 된 알림 소스를 설치 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `in_pNotifySource`  
 진행 알림 소스로 사용할 개체를 지정 합니다.  
  
 `out_ppNotifySink`  
 제한이 알림 싱크로 사용할 개체를 받습니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [INotifyConnection2 인터페이스](inotifyconnection2-interface.md)
- [INotifySource2 인터페이스](inotifysource2-interface.md)
- [INotifySink2 인터페이스](inotifysink2-interface.md)
- [UnregisterNotifySource 메서드](inotifyconnection2-unregisternotifysource-method.md)
