---
title: Silverlight용 CreateDebuggingInterfaceFromVersion 함수
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 438af9f191f48a86207c3b343ba428eef2c1fabc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132197"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>Silverlight용 CreateDebuggingInterfaceFromVersion 함수
[Createversionstringfrommodule 함수](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)에서 반환 되는 CLR (공용 언어 런타임) 버전 문자열을 수락 하 고 해당 디버거 인터페이스 (일반적으로 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md))를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szDebuggeeVersion`  
 진행 [Createversionstringfrommodule 함수](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)에서 반환 하는 대상 디버기에 있는 CLR의 버전 문자열입니다.  
  
 `ppCordb`  
 [out] COM 개체(`IUnknown`)에 대한 포인터의 포인터입니다. 이 개체는 반환 되기 전에 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 개체로 캐스팅 됩니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 `ppCordb` [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스를 구현 하는 유효한 개체를 참조 합니다.  
  
 E_INVALIDARG  
 `szDebuggeeVersion` 또는 `ppCordb`가 null입니다.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 CLR 디버깅에 필요한 구성 요소를 찾을 수 없습니다. 즉, mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 디렉터리에 없습니다.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 버전이 아닙니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)를 반환할 수 없습니다.  
  
## <a name="remarks"></a>주의  
 반환된 인터페이스는 대상 프로세스의 CLR에 연결하고 CLR에서 실행 중인 관리 코드를 디버그하기 위한 기능을 제공합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** dbgshim.dll  
  
 **라이브러리:** dbgshim.dll  
  
 **.NET Framework 버전:** 3.5 SP1
