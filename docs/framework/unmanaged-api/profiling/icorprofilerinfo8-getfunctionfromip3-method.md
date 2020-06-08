---
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
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495258"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="d9037-102">ICorProfilerInfo8:: GetFunctionFromIP3 메서드</span><span class="sxs-lookup"><span data-stu-id="d9037-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="d9037-103">관리 코드 명령 포인터를 FunctionID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="d9037-104">이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9037-105">구문</span><span class="sxs-lookup"><span data-stu-id="d9037-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="d9037-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9037-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="d9037-107">\[in] 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="d9037-108">\[out] 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-108">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="d9037-109">\[out] 함수의 JIT 다시 컴파일된 버전 id입니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-109">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9037-110">설명</span><span class="sxs-lookup"><span data-stu-id="d9037-110">Remarks</span></span>

<span data-ttu-id="d9037-111">이 메서드는 동적 메서드와 비동적 메서드 모두에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="d9037-112">메타 데이터를 사용 하는 함수에만 작동 하는 [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)의 상위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d9037-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9037-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9037-113">Requirements</span></span>

<span data-ttu-id="d9037-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9037-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d9037-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9037-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d9037-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9037-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d9037-117">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9037-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d9037-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9037-118">See also</span></span>

- [<span data-ttu-id="d9037-119">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9037-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
