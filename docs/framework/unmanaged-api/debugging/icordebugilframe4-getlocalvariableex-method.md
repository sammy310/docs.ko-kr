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
ms.openlocfilehash: 89a8aa1f789ad71b04bc5fed8885f55ee25c4609
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937663"
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
 진행 프로파일러 ReJIT 계측에 추가 된 변수가 프레임에 포함 되는지 여부를 지정 하는 [Ilcodekind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) 열거형 멤버입니다.  
  
 `dwIndex`  
 [in] IL 스택 프레임의 로컬 변수 인덱스입니다.  
  
 `ppValue`  
 제한이 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 선택적으로 프로파일러 ReJIT 계측에 추가 된 변수에 액세스 한다는 점을 제외 하 고 [Getlocalvariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 메서드와 비슷합니다. `flags` 값을 `ILCODE_ORIGINAL_IL`로 설정하여 이 메서드를 호출하는 것은 [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)을 호출하는 것과 같습니다. 추가 로컬 변수를 사용하여 메서드를 계측하는 경우에는 해당 변수에 액세스할 수 없습니다. `ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다. IL이 계측되지 않는 경우 메서드는 `E_INVALIDARG`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugILFrame4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: 방법 가이드](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
