---
title: CorDebugEHClause 구조체
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: 197c33511a474eb8291e4361ebb3c21fb3720cae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789422"
---
# <a name="cordebugehclause-structure"></a>CorDebugEHClause 구조체
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 지정된 IL(중간 언어) 코드 부분에 대한 EH(예외 처리) 절을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`Flags`|EH 절의 예외 정보를 설명하는 비트 필드입니다. 자세한 내용은 설명 섹션을 참조하세요.|  
|`TryOffset`|메서드 본문 시작 지점부터 `try` 블록의 오프셋(바이트)입니다.|  
|`TryLength`|`try` 블록의 길이(바이트)입니다.|  
|`HandlerOffset`|이 `try` 블록의 처리기 위치입니다.|  
|`HandlerLength`|처리기 코드의 크기(바이트)입니다.|  
|`ClassToken`|형식 기반 예외 처리기의 메타데이터 토큰입니다.|  
|`FilterOffset`|필터 기반 예외 처리기에 대한 메서드 본문 시작 지점부터의 오프셋(바이트)입니다.|  
  
## <a name="remarks"></a>주의  
 [GetEHClauses](icordebugilcode-getehclauses-method.md) 메서드는 `CoreDebugEHClause` 값의 배열을 반환 합니다.  
  
 EH 절 정보는 CLI 사양을 통해 정의됩니다. 자세한 내용은 [표준 ECMA-355: Common Language Infrastructure (CLI), 6 번째 버전](https://www.ecma-international.org/publications/standards/Ecma-335.htm)을 참조 하세요.  
  
 `flags` 필드는 다음 플래그를 포함할 수 있습니다. 이러한 플래그는 CorDebug.idl 또는 CorDebug.h에서 정의되지 않습니다.  
  
|플래그|값|설명|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|형식이 지정된 예외 절입니다.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|예외 필터 및 처리기 절입니다.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|`finally` 절입니다.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|fault 절, 즉 예외가 throw될 때만 호출되는 `finally` 절입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [GetEHClauses 메서드](icordebugilcode-getehclauses-method.md)
- [디버깅 구조체](debugging-structures.md)
