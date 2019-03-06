---
title: ICorDebugChain::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481562"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange 메서드
이 체인에 대 한 스택 세그먼트의 주소 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pStart`  
 [out] 에 대 한 포인터를 `CORDB_ADDRESS` 스택 세그먼트의 시작 주소입니다.  
  
 `pEnd`  
 [out] 에 대 한 포인터를 `CORDB_ADDRESS` 값 스택 세그먼트의 끝 주소입니다.  
  
## <a name="remarks"></a>설명  
 숫자 범위는 스택 프레임 위치를 비교 하기 위해. 실제로 스택에 저장 된 대 한 가정을 만들 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
