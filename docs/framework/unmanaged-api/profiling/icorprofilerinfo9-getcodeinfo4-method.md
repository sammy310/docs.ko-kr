---
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
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444795"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="3b6ec-102">ICorProfilerInfo9:: GetCodeInfo4 메서드</span><span class="sxs-lookup"><span data-stu-id="3b6ec-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="3b6ec-103">네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b6ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b6ec-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a><span data-ttu-id="3b6ec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b6ec-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="3b6ec-106">진행 네이티브 함수의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-106">[in] A pointer to the start of a native function.</span></span>

`cCodeInfos` \
<span data-ttu-id="3b6ec-107">[in] `codeInfos` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-107">[in] The size of the `codeInfos` array.</span></span>

`pcCodeInfos` \
<span data-ttu-id="3b6ec-108">제한이 사용할 수 있는 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조체의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>

`codeInfos` \
<span data-ttu-id="3b6ec-109">[out] 호출자가 제공한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="3b6ec-110">메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b6ec-111">설명</span><span class="sxs-lookup"><span data-stu-id="3b6ec-111">Remarks</span></span>

<span data-ttu-id="3b6ec-112">`GetCodeInfo4` 메서드는 메서드의 여러 다른 네이티브 버전에 대 한 코드 정보를 조회할 수 있다는 점을 제외 하 고 [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="3b6ec-113">`GetCodeInfo4` 가비지 수집을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="3b6ec-114">범위는 CIL(Common Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="3b6ec-115">`GetCodeInfo4` 반환한 후에는 `codeInfos` 버퍼가 모든 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조를 포함할 수 있을 만큼 충분히 큰지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="3b6ec-116">이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="3b6ec-117">[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조의 크기로 나눈 `cCodeInfos` `pcCodeInfos`보다 작은 경우 더 큰 `codeInfos` 버퍼를 할당 하 고, 더 큰 새 크기를 사용 하 여 `cCodeInfos`를 업데이트 하 고, `GetCodeInfo4`을 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="3b6ec-118">또는 길이가 0인 `GetCodeInfo4` 버퍼로 `codeInfos`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="3b6ec-119">그런 다음 `codeInfos` 버퍼 크기를 `pcCodeInfos`에서 반환 된 값으로 설정 하 고 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조의 크기를 곱하여 `GetCodeInfo4`를 다시 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b6ec-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b6ec-120">Requirements</span></span>

<span data-ttu-id="3b6ec-121">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6ec-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="3b6ec-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b6ec-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3b6ec-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b6ec-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3b6ec-124">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b6ec-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3b6ec-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="3b6ec-125">See also</span></span>

- [<span data-ttu-id="3b6ec-126">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b6ec-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
