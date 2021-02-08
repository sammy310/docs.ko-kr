---
description: '자세히 알아보기: ICorDebugVariableHomeEnum:: Next 메서드'
title: 'ICorDebugVariableHomeEnum:: Next 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 0aa0174e67bceaa724ddfeadc2560d12e112b859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790609"
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum:: Next 메서드

함수의 지역 변수 및 인수에 대 한 정보를 포함 하는 지정 된 수의 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `celt`  
 [in] 검색할 개체 수입니다.  
  
 `homes`  
 각 포인터가 지역 변수 또는 함수의 인수에 대 한 정보를 제공 하는 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 가리키는 포인터의 배열입니다.  
  
 `pceltFetched`  
 제한이 개체에서 실제로 반환 되는 인스턴스 수입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드는 다음 값을 반환 합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|메서드가 완료되었습니다.|  
|`S_FALSE`|에 반영 된 대로 검색 된 인스턴스의 실제 수가 `pceltFetched` 요청 된 인스턴스 수보다 작은 경우|  
  
## <a name="remarks"></a>설명  

 [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) 메서드는 `celt` 열거자의 현재 위치에서 시작 하 여 개체의 최대값을 검색 합니다. 메서드가 반환 될 때 `pceltFetched` 검색 된 개체의 실제 수를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugVariableHomeEnum 인터페이스](icordebugvariablehomeenum-interface.md)
- [ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)
