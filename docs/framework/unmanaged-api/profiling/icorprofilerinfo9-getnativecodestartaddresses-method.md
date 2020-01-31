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
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="4e819-102">ICorProfilerInfo9:: GetNativeCodeStartAddresses 메서드</span><span class="sxs-lookup"><span data-stu-id="4e819-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="4e819-103">FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e819-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e819-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="4e819-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e819-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="4e819-106">\[in] 네이티브 코드 시작 주소가 반환 되어야 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="4e819-107">\[in] JIT 다시 컴파일된 함수의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="4e819-108">\[in] `codeStartAddresses` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="4e819-109">\[out] 사용 가능한 주소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="4e819-110">\[out] `UINT_PTR`배열로, 각는 지정 된 함수에 대 한 네이티브 본문의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e819-111">주의</span><span class="sxs-lookup"><span data-stu-id="4e819-111">Remarks</span></span>

<span data-ttu-id="4e819-112">계층화 된 컴파일을 사용 하는 경우 함수에 둘 이상의 네이티브 코드 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e819-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e819-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e819-113">Requirements</span></span>

<span data-ttu-id="4e819-114">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e819-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="4e819-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e819-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4e819-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e819-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4e819-117">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e819-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4e819-118">참조</span><span class="sxs-lookup"><span data-stu-id="4e819-118">See also</span></span>

- [<span data-ttu-id="4e819-119">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e819-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
