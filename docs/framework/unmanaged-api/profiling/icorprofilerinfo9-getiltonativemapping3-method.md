---
description: '자세히 알아보기: ICorProfilerInfo9:: GetILToNativeMapping3 메서드'
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
ms.openlocfilehash: 865545e2352209447b3942da3a62f3733c165b35
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759328"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="891fc-103">ICorProfilerInfo9:: GetILToNativeMapping3 메서드</span><span class="sxs-lookup"><span data-stu-id="891fc-103">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="891fc-104">네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-104">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="891fc-105">구문</span><span class="sxs-lookup"><span data-stu-id="891fc-105">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="891fc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="891fc-106">Parameters</span></span>

<span data-ttu-id="891fc-107">`pNativeCodeStartAddress` 진행 네이티브 함수의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-107">`pNativeCodeStartAddress` [in] A pointer to the start of a native function.</span></span>

<span data-ttu-id="891fc-108">`cMap` 진행 배열의 최대 크기 `map` 입니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-108">`cMap` [in] The maximum size of the `map` array.</span></span>

<span data-ttu-id="891fc-109">`pcMap` 제한이 사용 가능한 COR_DEBUG_IL_TO_NATIVE_MAP 구조체의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-109">`pcMap` [out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

<span data-ttu-id="891fc-110">`map` 제한이 각각 오프셋을 지정 하는 [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-110">`map` [out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="891fc-111">`GetILToNativeMapping3` 메서드가 반환되면 `map`에 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체가 일부 또는 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-111">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="891fc-112">설명</span><span class="sxs-lookup"><span data-stu-id="891fc-112">Remarks</span></span>

<span data-ttu-id="891fc-113">계층화 된 컴파일을 사용 하는 경우 메서드에 둘 이상의 네이티브 코드 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-113">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="891fc-114">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) 는 모든 네이티브 코드 본문에 대 한 시작 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="891fc-114">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="891fc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="891fc-115">Requirements</span></span>

<span data-ttu-id="891fc-116">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="891fc-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="891fc-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="891fc-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="891fc-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="891fc-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="891fc-119">**.NET Framework 버전:**[!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span><span class="sxs-lookup"><span data-stu-id="891fc-119">**.NET Framework Versions:** [!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="891fc-120">참조</span><span class="sxs-lookup"><span data-stu-id="891fc-120">See also</span></span>

- [<span data-ttu-id="891fc-121">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="891fc-121">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
