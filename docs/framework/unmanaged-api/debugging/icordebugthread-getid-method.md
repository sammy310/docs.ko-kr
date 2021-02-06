---
description: '자세히 알아보기: ICorDebugThread:: GetID 메서드'
title: ICorDebugThread::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: d089201527da67299b64cdf074bdd331f22375a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659090"
---
# <a name="icordebugthreadgetid-method"></a>ICorDebugThread::GetID 메서드

이 ICorDebugThread 활성 부분의 현재 운영 체제 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pdwThreadId`  
 제한이 스레드의 식별자입니다.  
  
## <a name="remarks"></a>설명  

 운영 체제 식별자는 프로세스를 실행 하는 동안 변경 될 수 있으며 스레드의 다른 부분에 대 한 다른 값일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
