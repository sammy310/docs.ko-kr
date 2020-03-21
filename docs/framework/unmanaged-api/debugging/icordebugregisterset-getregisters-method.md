---
title: ICorDebugRegisterSet::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178538"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters 메서드
비트 마스크에 의해 지정된 각 레지스터(현재 실행 중인 컴퓨터에서)의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mask`  
 【인】 검색할 레지스터 값을 지정하는 비트 마스크입니다. 각 비트는 레지스터에 해당합니다. 비트가 1로 설정되면 레지스터의 값이 검색됩니다. 그렇지 않으면 레지스터의 값이 검색되지 않습니다.  
  
 `regCount`  
 【인】 검색할 레지스터 값의 수입니다.  
  
 `regBuffer`  
 【아웃】 레지스터의 `CORDB_REGISTER` 값을 받는 각각의 개체 배열입니다.  
  
## <a name="remarks"></a>설명  
 배열의 크기는 비트 마스크에서 1로 설정된 비트 수와 같아야 합니다. 매개 `regCount` 변수는 레지스터 값을 수신할 버퍼의 요소 수를 지정합니다. `regCount` 값이 마스크로 표시된 레지스터 수에 너무 작으면 번호가 높은 레지스터가 집합에서 잘립니다. `regCount` 값이 너무 크면 사용되지 `regBuffer` 않는 요소는 수정되지 않습니다.  
  
 비트 마스크에서 사용할 수 없는 레지스터를 `GetRegisters` 지정하면 해당 레지스터에 대한 확정되지 않은 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
