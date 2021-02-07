---
description: '다음에 대 한 자세한 정보: USER_THREAD 구조체'
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
ms.openlocfilehash: a4bd22073b7610307e67107781bdb68a15ef795f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761270"
---
# <a name="user_thread-structure"></a>USER_THREAD 구조체

스레드에 대 한 정보를 디버거에 제공 합니다. 자세한 내용은 [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`pSidBuffer`|스레드 버퍼의 주소입니다.|  
|`dwSidLen`|스레드 버퍼의 길이 (바이트)입니다.|  
|`dwTid`|스레드 ID입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [SetNotifyFilter 메서드](inotifysource2-setnotifyfilter-method.md)
- [진단 기호 저장소 구조체](diagnostics-symbol-store-structures.md)
