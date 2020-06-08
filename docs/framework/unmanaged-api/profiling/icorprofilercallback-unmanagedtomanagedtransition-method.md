---
title: ICorProfilerCallback::UnmanagedToManagedTransition 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: 8734fa9c9418b818cbe14ebe87ce2af6fa59c078
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499846"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition 메서드
비관리 코드에서 관리 코드로의 전환이 발생 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 진행 호출 되는 함수의 ID입니다.  
  
 `reason`  
 진행 비관리 코드에서 관리 코드를 호출 하거나 관리 되는 함수에 의해 호출 된 관리 되지 않는 함수의 반환 때문에 전환이 발생 했는지 여부를 나타내는 [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>설명  
 의 값 `reason` 이 COR_PRF_TRANSITION_RETURN이 고 `functionId` 가 null이 아닌 경우 함수 ID는 관리 되지 않는 함수의 함수 ID 이며 JIT (just-in-time) 컴파일러를 사용 하 여 컴파일되지 않습니다. 관리 되지 않는 함수에는 이름 및 일부 메타 데이터와 같은 몇 가지 기본 정보가 연결 되어 있습니다.  
  
 의 값 `reason` 이 COR_PRF_TRANSITION_CALL 이면 호출 된 함수 (관리 되는 함수)가 아직 JIT 컴파일되지 않았을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ManagedToUnmanagedTransition 메서드](icorprofilercallback-managedtounmanagedtransition-method.md)
- [C + +에서 명시적 PInvoke 사용 (DllImport 특성)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [C + + Interop 사용 (암시적 PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
