---
description: '자세히 알아보기: ICorDebugRegisterSet2:: GetRegisters 메서드'
title: ICorDebugRegisterSet2::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: 58af939b0e88185e2be23b69ca70d28e93ff873f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794782"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2:: GetRegisters 메서드

지정 된 비트 마스크로 지정 된 각 레지스터의 값 (코드가 현재 실행 중인 플랫폼의 경우)을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>매개 변수

 `maskCount`  
 진행 배열의 크기 (바이트) `mask` 입니다.  
  
 `mask`  
 진행 각 비트가 레지스터에 해당 하는 바이트 배열입니다. 비트가 1 이면 해당 레지스터의 값이 검색 됩니다.  
  
 `regCount`  
 진행 검색할 레지스터 값의 수입니다.  
  
 `regBuffer`  
 제한이 `CORDB_REGISTER` 각각 레지스터의 값을 받는 개체의 배열입니다.  
  
## <a name="remarks"></a>설명

 `GetRegisters`메서드는 마스크로 지정 된 레지스터에서 값의 배열을 반환 합니다. 배열에 해당 마스크 비트가 설정 되지 않은 레지스터의 값이 없습니다. 따라서 배열의 크기는 `regBuffer` 마스크에 있는 1의 수와 같아야 합니다. `regCount`마스크가 나타내는 레지스터의 수에 대해의 값이 너무 작으면 집합에서 더 높은 숫자의 레지스터 값이 잘립니다. `regCount`가 너무 클 경우 사용 하지 않는 `regBuffer` 요소는 수정 되지 않습니다.  
  
 사용할 수 없는 레지스터가 마스크로 표시 되 면 해당 레지스터에 대해 결정 되지 않은 값이 반환 됩니다.  
  
 `ICorDebugRegisterSet2::GetRegisters`이 메서드는 레지스터가 64 개를 초과 하는 플랫폼에 필요 합니다. 예를 들어 IA64에는 128 범용 레지스터와 128 부동 소수점 레지스터가 있으므로 비트 마스크에 64 비트 이상이 필요 합니다.  
  
 64 개를 초과 하는 레지스터가 없는 경우 x86 등의 플랫폼에 대 한 경우 처럼 메서드는 `GetRegisters` 바이트 배열의 바이트를로 변환한 `mask` `ULONG64` 다음 마스크를 사용 하는 [ICorDebugRegisterSet:: getregisters](icordebugregisterset-getregisters-method.md) 메서드를 호출 합니다 `ULONG64` .  
  
## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
