---
title: NOTIFY_FILTER 열거형
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 92e40dbe8892d48dba1c54d9cd16faa409440b24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438111"
---
# <a name="notify_filter-enumeration"></a>NOTIFY_FILTER 열거형
디버거 함수의 콜백을 식별 합니다. 자세한 내용은 [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|[INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) 메서드를 호출 해야 함을 나타냅니다.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|[INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) 메서드를 호출 해야 함을 나타냅니다.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|[INotifySink2:: OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) 메서드를 호출 해야 함을 나타냅니다.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|[INotifySink2:: OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) 메서드를 호출 해야 함을 나타냅니다.|  
|`NOTIFY_FILTER_ALLSYNC`|모든 [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) 메서드를 호출 해야 함을 나타냅니다.|  
|`NOTIFY_FILTER_ALL`|모든 기존 및 향후 알림을 활성화 합니다.|  
|`NOTIFY_FILTER_NONE`|알림 메서드를 호출 하지 않아야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 열거형](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
