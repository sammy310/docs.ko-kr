---
description: '자세히 알아보기: ICorProfilerInfo10:: IsFrozenObject 메서드'
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3b47204630056e2797b5cf126bd7c291830cea05
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103454"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>ICorProfilerInfo10:: IsFrozenObject 메서드

ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a>매개 변수

- `objectId`

  \[in] 검사할 개체입니다.

- `pbFrozen`

  \[out] `BOOL` 개체가 읽기 전용 세그먼트에 있는지 여부를 나타내는입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.Net 버전:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo10 인터페이스](icorprofilerinfo10-interface.md)
