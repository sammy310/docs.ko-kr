---
title: USER_THREAD 구조체
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127167"
---
# <a name="userthread-structure"></a>USER_THREAD 구조체
디버거에 스레드에 대 한 정보를 제공합니다. 자세한 내용은 참조는 [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pSidBuffer`|스레드 버퍼의 주소입니다.|  
|`dwSidLen`|스레드 버퍼 바이트의 길이입니다.|  
|`dwTid`|스레드 id입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>참고자료

- [SetNotifyFilter 메서드](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [진단 기호 저장소 구조체](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
