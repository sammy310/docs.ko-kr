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
ms.openlocfilehash: 315e4cc3b93fc78e11a4fb399bbe6f8a9f55ac84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705009"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters 메서드

비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.  
  
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
 진행 검색할 레지스터 값을 지정 하는 비트 마스크입니다. 각 비트는 레지스터에 해당 합니다. 비트가 1로 설정 된 경우 레지스터의 값이 검색 됩니다. 그렇지 않으면 레지스터의 값이 검색 되지 않습니다.  
  
 `regCount`  
 진행 검색할 레지스터 값의 수입니다.  
  
 `regBuffer`  
 제한이 `CORDB_REGISTER` 각각 레지스터의 값을 받는 개체의 배열입니다.  
  
## <a name="remarks"></a>설명  

 배열의 크기는 비트 마스크에서 1로 설정 된 비트 수와 같아야 합니다. `regCount`매개 변수는 레지스터 값을 받는 버퍼의 요소 수를 지정 합니다. `regCount`마스크가 나타내는 레지스터 수에 비해 값이 너무 작으면 집합에서 더 높은 번호의 레지스터가 잘립니다. `regCount`값이 너무 크면 사용 하지 않는 `regBuffer` 요소가 수정 되지 않습니다.  
  
 비트 마스크에서 사용할 수 없는 레지스터를 지정 하는 경우 `GetRegisters` 는 해당 레지스터에 대해 확정 되지 않은 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
