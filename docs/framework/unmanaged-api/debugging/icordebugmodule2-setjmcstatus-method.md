---
description: '자세히 알아보기: ICorDebugModule2:: SetJMCStatus 메서드'
title: ICorDebugModule2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: 7d91d098c21eac39d18a0aa7c3d4fd795be509ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790804"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus 메서드

이 ICorDebugModule2에 있는 모든 클래스의 모든 메서드에 대 한 모든 메서드의 JMC (내 코드만) 상태를 지정 된 값으로 설정 합니다. 단, `pTokens` 배열의 값은 반대 값으로 설정 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `bIsJustMycode`  
 진행 코드를 디버깅 하려면로 설정 하 고 그렇지 않으면로 설정 `true` `false` 합니다.  
  
 `cTokens`  
 [in] `pTokens` 배열의 크기입니다.  
  
 `pTokens`  
 진행 `mdToken` 각각 JMC 상태를!로 설정 하는 메서드를 참조 하는 값의 배열입니다 `bIsJustMycode` .  
  
## <a name="remarks"></a>설명  

 배열에 지정 된 각 메서드의 JMC 상태는 `pTokens` 값의 반대로 설정 됩니다 `bIsJustMycode` . 이 모듈의 다른 모든 메서드 상태는 값으로 설정 됩니다 `bIsJustMycode` .  
  
 `SetJMCStatus`메서드는이 모듈의 모든 이전 JMC 설정을 지웁니다.  
  
 `SetJMCStatus`모든 함수가 성공적으로 설정 된 경우 메서드는 S_OK HRESULT를 반환 합니다. 표시 된 일부 함수를 디버깅할 수 없는 경우 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT를 반환 합니다 `true` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
