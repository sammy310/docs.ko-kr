---
title: ICorDebugILCode::GetEHClauses 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: 38936a57944e9a0920c374f473c4cbe8e8d70abb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728669"
---
# <a name="icordebugilcodegetehclauses-method"></a>ICorDebugILCode::GetEHClauses 메서드

[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 IL(중간 언어)에 대해 정의된 EH(예외 처리) 절 목록에 대한 포인터를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `cClauses`  
 [in] `clauses` 배열의 스토리지 용량입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `pcClauses`  
 [out] `clauses` 배열에 관련 정보가 기록되는 절의 수입니다.  
  
 절  
 제한이 이 IL에 대해 정의 된 예외 처리 절에 대 한 정보를 포함 하는 [CorDebugEHClause](cordebugehclause-structure.md) 개체의 배열입니다.  
  
## <a name="remarks"></a>설명  

 `cClauses`가 0이 고 `pcClauses` 가 **null** 이 아닌 경우 `pcClauses` 는 사용 가능한 예외 처리 절 수로 설정 됩니다. `cClauses`은 값이 0이 아닌 경우 `clauses` 배열의 스토리지 용량을 나타냅니다. 메서드가 반환될 때 `clauses`는 `cClauses` 항목의 최대값을 포함하며 `pcClauses`는 `clauses` 배열에 실제로 기록된 절의 수로 설정됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugILCode 인터페이스](icordebugilcode-interface.md)
- [CorDebugEHClause 구조](cordebugehclause-structure.md)
- [디버깅 인터페이스](debugging-interfaces.md)
