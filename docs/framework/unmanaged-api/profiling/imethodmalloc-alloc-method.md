---
title: IMethodMalloc::Alloc 메서드
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
ms.openlocfilehash: af881d23ff77f05dadbbc745b973979e35ebe9f7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447560"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc 메서드

새 MSIL (Microsoft 중간 언어) 함수 본문에 지정 된 양의 메모리를 할당 하려고 시도 합니다.

## <a name="syntax"></a>구문

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>매개 변수

`cb`\
진행 메서드 본문에 할당할 바이트 수입니다.

## <a name="remarks"></a>주의

 할당 된 메모리는이 할당자와 연결 된 모듈의 기본 주소 보다 큰 주소에서 시작 됩니다. 즉, 각 할당자는 특정 모듈에 대해 만들어지며 기본 주소에서 양의 오프셋으로 메모리를 할당 하려고 시도 합니다. `Alloc`에서 모듈의 기본 주소 보다 큰 주소에 요청 된 바이트 수를 할당 하지 못하면 사용 가능한 실제 메모리 공간의 크기에 관계 없이 E_OUTOFMEMORY를 반환 합니다.

 `Alloc` 메서드는 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드와 함께 사용 해야 합니다.

## <a name="requirements"></a>요구 사항
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

 **헤더:** CorProf.idl, CorProf.h

 **라이브러리:** CorGuids.lib

 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참고 항목

- [IMethodMalloc 인터페이스](imethodmalloc-interface.md)
