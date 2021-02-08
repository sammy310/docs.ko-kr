---
description: ICorDebugStepper::D eactivate 메서드에 대해 자세히 알아보세요.
title: ICorDebugStepper::Deactivate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 039c52f5bc237506dcc648ace70789c8eb7ef8c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794665"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate 메서드

이 ICorDebugStepper에서 받은 마지막 단계 명령을 취소 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>설명  

 가장 최근에 받은 단계 명령이 취소 된 후에 새 단계별 실행 명령이 실행 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
