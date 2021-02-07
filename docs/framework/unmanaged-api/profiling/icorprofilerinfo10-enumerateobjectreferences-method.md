---
description: '자세히 알아보기: ICorProfilerInfo10:: EnumerateObjectReferences 메서드'
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
ms.openlocfilehash: 3e31192426ea38e177b636bcc6a4b6e54057801f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737326"
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

  \[in] 프로파일러에서 함수에 전달할 데이터를 제공 `callback` 합니다.

## <a name="remarks"></a>설명

`EnumerateObjectReferences`메서드는 참조를 저장 하는 배열을 미리 할당 하는 대신 프로파일러의 요청 시 참조를 [ObjectReferences](icorprofilercallback-objectreferences-method.md)한다는 점을 제외 하 고는와 유사 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.Net 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo10 인터페이스](icorprofilerinfo10-interface.md)
