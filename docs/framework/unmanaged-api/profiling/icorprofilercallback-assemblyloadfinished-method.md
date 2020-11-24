---
title: ICorProfilerCallback::AssemblyLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: fd41463af0acac1bbe1a3d4515350905b6784f79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685336"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>ICorProfilerCallback::AssemblyLoadFinished 메서드

어셈블리의 로드가 완료 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>매개 변수

- `assemblyId`

  \[in] 로드 된 어셈블리를 식별 합니다.

- `hrStatus`

  \[in] 어셈블리의 로드가 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명  

 `assemblyId`메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다 `AssemblyLoadFinished` .  
  
 어셈블리를 로드 하는 일부 부분은 콜백 후에도 계속 될 수 있습니다 `AssemblyLoadFinished` . 의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다. 그러나의 성공 HRESULT는 어셈블리를 로드 하는 `hrStatus` 첫 번째 부분이 성공 했다는 것을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
