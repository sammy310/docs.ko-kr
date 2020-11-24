---
title: ICorDebugThread::EnumerateChains 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 76b231f00651186518d3bccfafa5780f258c4f75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688187"
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains 메서드

이 ICorDebugThread 개체의 모든 스택 체인을 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppChains`  
 제한이 `ICorDebugChainEnum` 활성 (가장 최근) 체인에서 시작 하 여이 스레드에서 모든 스택 체인을 열거할 수 있도록 하는 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 스택 체인은 스레드의 물리적 호출 스택을 나타냅니다. 다음 상황에서는 스택 체인 경계를 만듭니다.  
  
- 관리 되는 관리 또는 관리 되지 않는 전환입니다.  
  
- 컨텍스트 전환.  
  
- 디버거는 사용자 스레드를 하이재킹 합니다.  
  
 단일 컨텍스트에서 순수 하 게 관리 되는 코드를 실행 하는 스레드에 대 한 간단한 경우에는 스레드 및 스택 체인 사이에 일 대 일 대응이 존재 합니다.  
  
 디버거는 모든 스레드의 실제 호출 스택을 논리적 호출 스택으로 다시 정렬 하려고 할 수 있습니다. 여기에는 호출자/호출 수신자 관계로 모든 스레드 체인을 정렬 하 고 regrouping 하는 작업이 포함 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
