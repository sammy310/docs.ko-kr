---
title: ICorProfilerCallback::ManagedToUnmanagedTransition 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: ef65ed908c71bcc2755aaf42070439fd7dab3f6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733141"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition 메서드

관리 코드에서 비관리 코드로의 전환이 발생 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>매개 변수  

 `functionId`  
 진행 호출 되는 함수의 ID입니다.  
  
 `reason`  
 진행 관리 코드에서 비관리 코드를 호출 하거나 관리 되지 않는 함수에서 호출 된 관리 되는 함수의 반환 때문에 전환이 발생 했는지 여부를 나타내는 [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>설명  

 의 값 `reason` 이 COR_PRF_TRANSITION_CALL 경우 함수 ID는 관리 되지 않는 함수의 함수 ID 이며 just-in-time 컴파일러를 사용 하 여 컴파일되지 않습니다. 관리 되지 않는 함수에는 이름 및 일부 메타 데이터와 같은 기본 정보가 연결 되어 있습니다. PInvoke (암시적 플랫폼 호출)를 사용 하 여 관리 되지 않는 함수를 호출한 경우 런타임에서 호출 대상을 확인할 수 없으며의 값 `functionId` 이 null이 됩니다. 암시적 PInvoke에 대 한 자세한 내용은 [c + + Interop 사용 (암시적 pinvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [UnmanagedToManagedTransition 메서드](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [C + +에서 명시적 PInvoke 사용 (DllImport 특성)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
