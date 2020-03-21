---
title: ICorDebugILFrame4::GetLocalVariableEx 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: ee263e8c49cd6da7278bd2299557336629720d2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178773"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>ICorDebugILFrame4::GetLocalVariableEx 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 IL(중간 언어) 스택 프레임에 지정된 로컬 변수의 값을 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `flags`  
 【인】 프로파일러 ReJIT 계측에 추가된 변수가 프레임에 포함되는지 여부를 지정하는 [ILCodeKind](ilcodekind-enumeration.md) 열거 멤버입니다.  
  
 `dwIndex`  
 [in] IL 스택 프레임의 로컬 변수 인덱스입니다.  
  
 `ppValue`  
 【아웃】 검색된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 프로파일러 ReJIT 계측에 추가된 변수에 선택적으로 액세스한다는 점을 제외하면 [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) 메서드와 유사합니다. 값으로이 메서드를 `flags` `ILCODE_ORIGINAL_IL` 호출 하는 [것은 GetLocalVariable](icordebugilframe-getlocalvariable-method.md)를 호출 하는 것과 같습니다. 메서드가 추가 로컬 변수로 계측되면 해당 변수에 액세스할 수 없습니다. `ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다. IL이 계측되지 않는 경우 메서드는 `E_INVALIDARG`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugILFrame4 인터페이스](icordebugilframe4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [ReJIT: 방법 가이드](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
