---
description: '자세히 알아보기: ICorProfilerInfo9:: GetCodeInfo4 메서드'
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: c7897e266fbb84d44df719c127e24bd375b560bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759093"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="5183c-103">ICorProfilerInfo9:: GetCodeInfo4 메서드</span><span class="sxs-lookup"><span data-stu-id="5183c-103">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="5183c-104">네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-104">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="5183c-105">구문</span><span class="sxs-lookup"><span data-stu-id="5183c-105">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a><span data-ttu-id="5183c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5183c-106">Parameters</span></span>

<span data-ttu-id="5183c-107">`pNativeCodeStartAddress` 진행 네이티브 함수의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-107">`pNativeCodeStartAddress` [in] A pointer to the start of a native function.</span></span>

<span data-ttu-id="5183c-108">`cCodeInfos` 진행 `codeInfos` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-108">`cCodeInfos` [in] The size of the `codeInfos` array.</span></span>

<span data-ttu-id="5183c-109">`pcCodeInfos` 제한이 사용할 수 있는 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조체의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-109">`pcCodeInfos` [out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>

<span data-ttu-id="5183c-110">`codeInfos` 제한이 호출자가 제공한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-110">`codeInfos` [out] A caller-provided buffer.</span></span> <span data-ttu-id="5183c-111">메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5183c-112">설명</span><span class="sxs-lookup"><span data-stu-id="5183c-112">Remarks</span></span>

<span data-ttu-id="5183c-113">메서드는 `GetCodeInfo4` 메서드의 다른 네이티브 버전에 대 한 코드 정보를 조회할 수 있다는 점을 제외 하 고 [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md)와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-113">The `GetCodeInfo4` method is similar to [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="5183c-114">`GetCodeInfo4` 가비지 수집을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-114">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="5183c-115">범위는 CIL(Common Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-115">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="5183c-116">`GetCodeInfo4`가 반환 된 후 `codeInfos` 버퍼가 모든 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조를 포함할 수 있을 만큼 충분히 큰지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-116">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="5183c-117">이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-117">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="5183c-118">`cCodeInfos` [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조의 크기로 나눈 값이 보다 작으면 `pcCodeInfos` 더 큰 버퍼를 할당 하 고를 `codeInfos` `cCodeInfos` 더 큰 새 크기로 업데이트 한 다음를 `GetCodeInfo4` 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-118">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="5183c-119">또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo4`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="5183c-119">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="5183c-120">그런 다음 `codeInfos` 버퍼 크기를에서 반환 된 값으로 설정 하 `pcCodeInfos` 고 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조체의 크기를 곱한 다음를 다시 호출할 수 있습니다 `GetCodeInfo4` .</span><span class="sxs-lookup"><span data-stu-id="5183c-120">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="5183c-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5183c-121">Requirements</span></span>

<span data-ttu-id="5183c-122">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5183c-122">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="5183c-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5183c-123">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5183c-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5183c-124">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5183c-125">**.Net 버전:**[!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5183c-125">**.NET Versions:** [!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5183c-126">참조</span><span class="sxs-lookup"><span data-stu-id="5183c-126">See also</span></span>

- [<span data-ttu-id="5183c-127">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5183c-127">ICorProfilerInfo9 Interface</span></span>](ICorProfilerInfo9-interface.md)
