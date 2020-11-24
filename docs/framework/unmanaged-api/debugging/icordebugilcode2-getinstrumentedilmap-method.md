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
ms.openlocfilehash: 097502f4321531922d6c4385e2eccbf32f66f026
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688356"
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
 [out] 맵 배열에 기록되는 COR_IL_MAP 값의 수입니다.  
  
 map  
 [out] 프로파일러가 계측한 IL에서 원래 메서드 IL로의 매핑에 대한 정보를 제공하는 COR_IL_MAP 값의 배열입니다.  
  
## <a name="remarks"></a>설명  

 프로파일러가 [ICorProfilerInfo:: SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드를 호출 하 여 매핑을 설정 하는 경우 디버거는이 메서드를 호출 하 여 매핑을 검색 하 고 스택 추적 및 변수 수명에 대 한 IL 오프셋을 계산할 때 내부적으로 매핑을 사용할 수 있습니다.  
  
 `cMap`가 0이 고 `pcMap` 가 **null** 이 아닌 경우 `pcMap` 는 사용 가능한 COR_IL_MAP 값의 수로 설정 됩니다. `cMap`은 값이 0이 아닌 경우 `map` 배열의 스토리지 용량을 나타냅니다. 메서드가 반환 될 때에는 `map` 최대 항목 수가 포함 `cMap` 되 고 `pcMap` 는 배열에 실제로 기록 되는 COR_IL_MAP 값의 수로 설정 됩니다 `map` .  
  
 IL이 계측되지 않았거나 프로파일러가 매핑을 제공하지 않은 경우 이 메서드는 `S_OK`를 반환하고 `pcMap`을 0으로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2 인터페이스](icordebugilcode2-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
