---
title: CALL_ID 구조체
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420632"
---
# <a name="call_id-structure"></a>CALL_ID 구조체
호출 되는 함수에 대 한 정보를 디버거에 제공 합니다. 자세한 내용은 [INotifySink2](inotifysink2-interface.md) 인터페이스를 참조 하세요.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`szMachine`|호출을 수행 하는 컴퓨터를 식별 합니다.|  
|`dwPid`|컴퓨터 프로세서를 식별 합니다.|  
|`pUserThread`|호출을 실행 하는 스레드를 식별 합니다.|  
|`addrStackPointer`|호출 스택의 주소를 지정 합니다.|  
|`szEntryPoint`|호출의 주소를 지정 합니다.|  
|`szDestinationMachine`|호출을 실행할 컴퓨터를 식별 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ProtocolNotify2  
  
## <a name="see-also"></a>참고 항목

- [INotifySink2 인터페이스](inotifysink2-interface.md)
- [진단 기호 저장소 구조체](diagnostics-symbol-store-structures.md)
