---
title: ICorDebugModule::EnableJITDebugging 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109721"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging 메서드
JIT (just-in-time) 컴파일러에서이 모듈의 메서드에 대 한 디버깅 정보를 유지할지 여부를 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bTrackJITInfo`  
 진행 JIT 컴파일러에서이 모듈의 각 메서드에 대 한 MSIL (Microsoft 중간 언어) 버전과 JIT 컴파일된 버전 사이의 매핑 정보를 유지할 수 있도록 하려면이 값을 `true`로 설정 합니다.  
  
 `bAllowJitOpts`  
 진행 JIT 컴파일러에서 디버깅을 위해 특정 JIT 관련 최적화를 사용 하 여 코드를 생성할 수 있도록 하려면이 값을 `true`로 설정 합니다.  
  
## <a name="remarks"></a>주의  
 JIT 디버깅은 디버거가 활성 상태일 때 로드 되는 모든 모듈에 대해 기본적으로 사용 하도록 설정 됩니다. 프로그래밍 방식으로 설정을 사용 하거나 사용 하지 않도록 설정 하면 전역 설정이 재정의 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
