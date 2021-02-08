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
ms.openlocfilehash: 3ce0a0964e26254ab09e515826b6bceb657e07bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783835"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="a502e-103">ICorProfilerInfo8:: GetFunctionFromIP3 메서드</span><span class="sxs-lookup"><span data-stu-id="a502e-103">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="a502e-104">관리 코드 명령 포인터를 FunctionID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-104">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="a502e-105">이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-105">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="a502e-106">구문</span><span class="sxs-lookup"><span data-stu-id="a502e-106">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="a502e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a502e-107">Parameters</span></span>

- `ip`

  <span data-ttu-id="a502e-108">\[in] 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-108">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="a502e-109">\[out] 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-109">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="a502e-110">\[out] 함수의 JIT 다시 컴파일된 버전 id입니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-110">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a502e-111">설명</span><span class="sxs-lookup"><span data-stu-id="a502e-111">Remarks</span></span>

<span data-ttu-id="a502e-112">이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-112">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="a502e-113">메타 데이터를 사용 하는 함수에만 작동 하는 [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)의 상위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="a502e-113">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="a502e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a502e-114">Requirements</span></span>

<span data-ttu-id="a502e-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a502e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a502e-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a502e-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a502e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a502e-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a502e-118">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a502e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a502e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a502e-119">See also</span></span>

- [<span data-ttu-id="a502e-120">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a502e-120">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
