---
description: '자세히 알아보기: ICorProfilerInfo8:: GetFunctionFromIP3 메서드'
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 1b753350f45f722d60099b17cfdd48bfd06e411a
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759106"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>ICorProfilerInfo8:: GetFunctionFromIP3 메서드

관리 코드 명령 포인터를 FunctionID에 매핑합니다. 이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a>매개 변수

`ip` 진행 관리 코드의 명령 포인터입니다.

`pFunctionId` 제한이 함수 ID입니다.

`pReJitId` 제한이 함수의 JIT 다시 컴파일된 버전 id입니다.

## <a name="remarks"></a>설명

이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다. 메타 데이터를 사용 하는 함수에만 작동 하는 [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)의 상위 집합입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo8 인터페이스](icorprofilerinfo8-interface.md)
