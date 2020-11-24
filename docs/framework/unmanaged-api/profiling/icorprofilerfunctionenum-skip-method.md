---
title: ICorProfilerFunctionEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: da578e02db0744b1f64c1d392844aa020721e784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669261"
---
# <a name="icorprofilerfunctionenumskip-method"></a>ICorProfilerFunctionEnum::Skip 메서드

지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a>매개 변수  

 `celt`  
 진행 건너뛸 요소의 수입니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`celt` 요소를 건너뛰었습니다.|  
|S_FALSE|요소 `celt` 수를 건너 뛰 었으 며 더 이상 요소가 없다는 것을 나타냅니다.|  
  
## <a name="remarks"></a>설명  

 이 열거자 커서의 새 위치는 (현재 위치) + `celt` 입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerFunctionEnum 인터페이스](icorprofilerfunctionenum-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
