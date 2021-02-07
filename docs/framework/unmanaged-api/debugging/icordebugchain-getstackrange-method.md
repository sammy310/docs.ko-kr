---
description: '자세히 알아보기: ICorDebugChain:: GetStackRange 메서드'
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
ms.openlocfilehash: 066dda06564655350d799dabb54acd622b828172
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694932"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange 메서드

이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pStart`  
 제한이 스택 세그먼트의 시작 주소에 해당 하는 값에 대 한 포인터입니다 `CORDB_ADDRESS` .  
  
 `pEnd`  
 제한이 `CORDB_ADDRESS` 스택 세그먼트의 끝 주소인 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 숫자 범위는 스택 프레임 위치를 비교 하는 경우에만 의미가 있습니다. 실제로 스택에 저장 되는 항목에 대 한 가정을 만들 수는 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
