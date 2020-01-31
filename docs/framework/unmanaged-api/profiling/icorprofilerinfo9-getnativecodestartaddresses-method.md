---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 8412020fb98fde245b873a2f0c6a355f6436f712
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868280"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>ICorProfilerInfo9:: GetNativeCodeStartAddresses 메서드

FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 네이티브 코드 시작 주소가 반환 되어야 하는 함수의 ID입니다.

- `reJitId`

  \[in] JIT 다시 컴파일된 함수의 id입니다.

- `cCodeStartAddresses`

  \[in] `codeStartAddresses` 배열의 최대 크기입니다.

- `pcCodeStartAddresses`

  \[out] 사용 가능한 주소 수입니다.

- `codeStartAddresses`

  \[out] `UINT_PTR`배열로, 각는 지정 된 함수에 대 한 네이티브 본문의 시작 주소입니다.

## <a name="remarks"></a>주의

계층화 된 컴파일을 사용 하는 경우 함수에 둘 이상의 네이티브 코드 본문이 있을 수 있습니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo9 인터페이스](icorprofilerinfo9-interface.md)
