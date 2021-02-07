---
description: '자세히 알아보기: ICorDebugEval:: Abort 메서드'
title: ICorDebugEval::Abort 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: d61cb0d696a8a134d992bc8dbbfdb61103ef469f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694320"
---
# <a name="icordebugevalabort-method"></a>ICorDebugEval::Abort 메서드

이 ICorDebugEval 개체가 현재 수행 하 고 있는 계산을 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>설명  

 계산이 중첩 되 고 가장 최근 계산이 아닌 경우 `Abort` 메서드가 실패할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
