---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 1a5a259e6604d906e55166b3fcb770bc37d346c5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444728"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="54598-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span><span class="sxs-lookup"><span data-stu-id="54598-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="54598-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span><span class="sxs-lookup"><span data-stu-id="54598-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="54598-104">구문</span><span class="sxs-lookup"><span data-stu-id="54598-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

#### <a name="parameters"></a><span data-ttu-id="54598-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54598-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="54598-106">[in] A pointer to the start of a native function.</span><span class="sxs-lookup"><span data-stu-id="54598-106">[in] A pointer to the start of a native function.</span></span>

`cMap` \
<span data-ttu-id="54598-107">[in] `map` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="54598-107">[in] The maximum size of the `map` array.</span></span>

`pcMap` \
<span data-ttu-id="54598-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span><span class="sxs-lookup"><span data-stu-id="54598-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

`map` \
<span data-ttu-id="54598-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span><span class="sxs-lookup"><span data-stu-id="54598-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="54598-110">`GetILToNativeMapping3` 메서드가 반환되면 `map`에 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체가 일부 또는 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54598-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="54598-111">주의</span><span class="sxs-lookup"><span data-stu-id="54598-111">Remarks</span></span>

<span data-ttu-id="54598-112">When tiered compilation is enabled, a method may have more than one native code body.</span><span class="sxs-lookup"><span data-stu-id="54598-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="54598-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span><span class="sxs-lookup"><span data-stu-id="54598-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="54598-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54598-114">Requirements</span></span>

<span data-ttu-id="54598-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="54598-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="54598-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="54598-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="54598-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54598-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="54598-118">**.NET Framework 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54598-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="54598-119">참조</span><span class="sxs-lookup"><span data-stu-id="54598-119">See also</span></span>

- [<span data-ttu-id="54598-120">ICorProfilerInfo9 Interface</span><span class="sxs-lookup"><span data-stu-id="54598-120">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
