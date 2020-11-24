---
title: ICorDebugVariableHome 인터페이스
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: 089e68278113dfdf509ed848f424ad32baa145ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679548"
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome 인터페이스

함수의 지역 변수 또는 인수를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetArgumentIndex 메서드](icordebugvariablehome-getargumentindex-method.md)|함수 인수의 인덱스를 가져옵니다.|  
|[GetCode 메서드](icordebugvariablehome-getcode-method.md)|이 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다 `ICorDebugVariableHome` .|  
|[GetLiveRange 메서드](icordebugvariablehome-getliverange-method.md)|이 변수가 활성 상태인 기본 범위를 가져옵니다.|  
|[GetLocationType 메서드](icordebugvariablehome-getlocationtype-method.md)|변수의 네이티브 위치 유형을 가져옵니다.|  
|[GetOffset 메서드](icordebugvariablehome-getoffset-method.md)|변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.|  
|[GetRegister 메서드](icordebugvariablehome-getregister-method.md)|위치 형식이 인 변수가 포함 된 레지스터 `VLT_REGISTER` 와 위치 형식이 인 변수에 대 한 기본 레지스터를 가져옵니다 `VLT_REGISTER_RELATIVE` .|  
|[GetSlotIndex 메서드](icordebugvariablehome-getslotindex-method.md)|지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.|  
  
## <a name="example"></a>예제  

 다음 코드 조각에서는 라는 [ICorDebugCode4](icordebugcode4-interface.md) 개체를 사용 합니다 `pCode4` .  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [ICorDebugVariableHomeEnum 인터페이스](icordebugvariablehomeenum-interface.md)
