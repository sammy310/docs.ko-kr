---
title: ICorDebugRegisterSet2::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378216"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable 메서드
사용 가능한 레지스터의 비트맵을 제공 하는 바이트 배열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `numChunks`  
 [in] `availableRegChunks` 배열의 크기입니다.  
  
 `availableRegChunks`  
 제한이 각 비트가 레지스터에 해당 하는 바이트 배열입니다. 레지스터를 사용할 수 있는 경우 레지스터의 해당 비트가 설정 됩니다.  
  
## <a name="remarks"></a>설명  
 CorDebugRegister 열거형의 값은 다른 마이크로프로세서의 레지스터를 지정 합니다. 각 값의 상위 5 비트는 `availableRegChunks` 바이트 배열에 대 한 인덱스입니다. 각 값의 하위 3 비트는 인덱싱된 바이트 내의 비트 위치를 식별 합니다. `CorDebugRegister`특정 레지스터를 지정 하는 값을 지정 하는 경우 마스크의 레지스터 위치는 다음과 같이 결정 됩니다.  
  
1. 배열의 올바른 바이트에 액세스 하는 데 필요한 인덱스를 추출 합니다 `availableRegChunks` .  
  
     `CorDebugRegister`값 >> 3  
  
2. 인덱싱된 바이트 내에서 비트 위치를 추출 합니다. 여기서 bit 0은 최하위 비트입니다.  
  
     `CorDebugRegister`값 & 7  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
