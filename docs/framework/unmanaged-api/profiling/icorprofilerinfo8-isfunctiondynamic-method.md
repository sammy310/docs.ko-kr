---
title: 'ICorProfilerInfo8:: IsFunctionDynamic'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 50b4de2de3e74a5835ee5706999892735269d4c2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861738"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>ICorProfilerInfo8:: IsFunctionDynamic 메서드

함수에 연결 된 메타 데이터가 있는지 여부를 확인 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 해당 함수를 식별 하는 `FunctionID`입니다.

- `isDynamic`

  \[out] 함수가 메타 데이터를 포함 하지 않는지 여부를 나타내는 값을 포함 하는 `BOOL`에 대 한 포인터입니다.

## <a name="remarks"></a>주의

메타 데이터가 없는 함수는 동적 함수로 간주 됩니다. IL 스텁 또는 LCG 메서드와 같은 특정 메서드는 IMetaDataImport Api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터를 포함 하지 않습니다. 이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo8 인터페이스](icorprofilerinfo8-interface.md)
