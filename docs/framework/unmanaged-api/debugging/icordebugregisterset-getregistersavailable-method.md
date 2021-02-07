---
description: '자세히 알아보기: ICorDebugRegisterSet:: GetRegistersAvailable 메서드'
title: ICorDebugRegisterSet::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: a1727c594733fe6529fe1e78f341723623b68be2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690823"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>ICorDebugRegisterSet::GetRegistersAvailable 메서드

이 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 에서 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pAvailable`  
 제한이 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.  
  
## <a name="remarks"></a>설명  

 지정 된 상황에 대해 해당 값을 확인할 수 없는 경우에는 레지스터를 사용할 수 없습니다.  
  
 반환 된 마스크에는 각 레지스터의 비트 (1 << 레지스터 인덱스)가 포함 됩니다. 레지스터를 사용할 수 있으면 비트 값은 1이 고, 사용할 수 없는 경우 0입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
