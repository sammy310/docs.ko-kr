---
title: ICorDebugILCode2::GetInstrumentedILMap 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 7dede4e5af702f1b86b430450db4a669c326c062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131071"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>ICorDebugILCode2::GetInstrumentedILMap 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 인스턴스에 대해 프로파일러가 계측한 IL(중간 언어) 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 cMap  
 [in] `map` 배열의 스토리지 용량입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 pcMap  
 제한이 지도 배열에 기록 된 COR_IL_MAP 값의 수입니다.  
  
 map  
 제한이 프로파일러 계측 된 IL에서 원래 메서드의 IL로의 매핑에 대 한 정보를 제공 하는 COR_IL_MAP 값의 배열입니다.  
  
## <a name="remarks"></a>주의  
 프로파일러가 [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드를 호출 하 여 매핑을 설정 하는 경우 디버거는이 메서드를 호출 하 여 매핑을 검색 하 고 스택 추적 및 변수에 대 한 IL 오프셋을 계산할 때 내부적으로 매핑을 사용할 수 있습니다. 수명.  
  
 `cMap`이 0이 고 `pcMap`**null**이 아닌 경우 `pcMap`은 사용 가능한 COR_IL_MAP 값의 수로 설정 됩니다. `cMap`은 값이 0이 아닌 경우 `map` 배열의 스토리지 용량을 나타냅니다. 메서드가 반환 될 때 `map`는 최대 `cMap` 항목을 포함 하 고, `pcMap`는 실제로 `map` 배열에 기록 된 COR_IL_MAP 값의 수로 설정 됩니다.  
  
 IL이 계측되지 않았거나 프로파일러가 매핑을 제공하지 않은 경우 이 메서드는 `S_OK`를 반환하고 `pcMap`을 0으로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
