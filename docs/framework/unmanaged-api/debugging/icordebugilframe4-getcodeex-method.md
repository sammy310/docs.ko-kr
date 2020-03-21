---
title: ICorDebugILFrame4::GetCodeEx 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178787"
---
# <a name="icordebugilframe4getcodeex-method"></a>ICorDebugILFrame4::GetCodeEx 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 스택 프레임에서 실행 중인 코드에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `flags`  
 【인】 프로파일러의 ReJIT 요청에 의해 정의된 중간 언어(IL)가 프레임에 포함되는지 여부를 지정하는 [ILCodeKind](ilcodekind-enumeration.md) 열거 멤버입니다.  
  
 `ppCode`  
 【아웃】 이 스택 프레임이 실행되는 코드를 나타내는 "ICorDebugCode" 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 프로파일러의 ReJIT 요청에 의해 정의된 코드에 선택적으로 액세스한다는 점을 제외하면 [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) 메서드와 유사합니다. 값으로이 메서드를 `flags` `ILCODE_ORIGINAL_IL` 호출 하는 [것은 GetCode를](icordebugframe-getcode-method.md)호출 하는 것과 같습니다. 메서드가 계측되면 IL에 액세스할 수 없습니다. `ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 요청에 의해 정의된 IL에 액세스할 수 있습니다. IL이 계측되지 `ppCode` 않은 경우 **null이며**메서드가 반환됩니다. `S_OK`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugILFrame4 인터페이스](icordebugilframe4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [ReJIT: 방법 가이드](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
