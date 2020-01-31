---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863311"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10:: EnumerateObjectReferences 메서드

ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).

## <a name="syntax"></a>구문

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>매개 변수

- `objectId`

  \[in] 참조를 열거 하는 개체입니다.

- `callback`

  \[in] 개체에 대 한 참조를 사용 하 여 호출 되는 함수입니다.

- `clientData`

  \[in] 프로파일러 제공 데이터를 `callback` 함수에 전달 합니다.

## <a name="remarks"></a>주의

`EnumerateObjectReferences` 메서드는 참조를 저장 하는 배열을 미리 할당 하는 대신 프로파일러의 요청 시 참조를 안내 한다는 점을 제외 하 고 [ObjectReferences](icorprofilercallback-objectreferences-method.md)와 비슷합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo10 인터페이스](icorprofilerinfo10-interface.md)
