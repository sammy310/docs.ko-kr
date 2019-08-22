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
ms.openlocfilehash: 9e8e4c7e6c367970100c98dc3dc8237b25f99221
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665610"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="28ec9-102">ICorProfilerInfo9:: GetILToNativeMapping3 메서드</span><span class="sxs-lookup"><span data-stu-id="28ec9-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="28ec9-103">네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="28ec9-104">구문</span><span class="sxs-lookup"><span data-stu-id="28ec9-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

#### <a name="parameters"></a><span data-ttu-id="28ec9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28ec9-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="28ec9-106">진행 네이티브 함수의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-106">[in] A pointer to the start of a native function.</span></span>

`cMap` \
<span data-ttu-id="28ec9-107">[in] `map` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-107">[in] The maximum size of the `map` array.</span></span>

`pcMap` \
<span data-ttu-id="28ec9-108">제한이 사용 가능한 COR_DEBUG_IL_TO_NATIVE_MAP 구조체의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

`map` \
<span data-ttu-id="28ec9-109">제한이 각각 오프셋을 지정 하는 [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="28ec9-110">`GetILToNativeMapping3` 메서드가 반환되면 `map`에 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체가 일부 또는 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="28ec9-111">설명</span><span class="sxs-lookup"><span data-stu-id="28ec9-111">Remarks</span></span>

<span data-ttu-id="28ec9-112">계층화 된 컴파일을 사용 하는 경우 메서드에 둘 이상의 네이티브 코드 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="28ec9-113">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) 는 모든 네이티브 코드 본문에 대 한 시작 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ec9-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="28ec9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28ec9-114">Requirements</span></span>

<span data-ttu-id="28ec9-115">**플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28ec9-115">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="28ec9-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28ec9-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="28ec9-117">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28ec9-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="28ec9-118">**.NET Framework 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ec9-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="28ec9-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="28ec9-119">See also</span></span>

- [<span data-ttu-id="28ec9-120">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28ec9-120">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
