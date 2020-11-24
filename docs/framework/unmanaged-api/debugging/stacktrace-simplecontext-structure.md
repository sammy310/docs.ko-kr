---
title: StackTrace_SimpleContext 구조체
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 30775b4a6f904d06b9c77e6b2b64aec693c446d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671800"
---
# <a name="stacktrace_simplecontext-structure"></a>StackTrace_SimpleContext 구조체

전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`StackOffset`|X86 플랫폼의 스택 포인터 또는 ESP (enter stack 포인터)입니다.|  
|`FrameOffset`|프레임 오프셋 또는 x86 플랫폼의 EBP 레지스터입니다.|  
|`InstructionOffset`|X86 플랫폼의 명령 포인터 또는 EIP (enter 명령 포인터)입니다.|  
  
## <a name="remarks"></a>설명  

 스택 추적 함수는 일반적으로 주소, 프레임 오프셋 및 스택 주소만 반환 해야 하기 때문에 필요한 경우에는 `SimpleContext` 구조체 대신 구조를 사용할 수 있습니다 `CONTEXT` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** SOS_Stacktrace. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
