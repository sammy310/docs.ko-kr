---
description: '자세히 알아보기: ICorProfilerInfo9:: GetNativeCodeStartAddresses 메서드'
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
ms.openlocfilehash: 062aebf6d5bed208ea71b215bd9f857b82483673
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759050"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="43037-103">ICorProfilerInfo9:: GetNativeCodeStartAddresses 메서드</span><span class="sxs-lookup"><span data-stu-id="43037-103">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="43037-104">FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="43037-104">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="43037-105">구문</span><span class="sxs-lookup"><span data-stu-id="43037-105">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="43037-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43037-106">Parameters</span></span>

<span data-ttu-id="43037-107">`functionId` 진행 네이티브 코드 시작 주소가 반환 되어야 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="43037-107">`functionId` [in] The ID of the function whose native code start addresses should be returned.</span></span>

<span data-ttu-id="43037-108">`reJitId` 진행 JIT 다시 컴파일된 함수의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="43037-108">`reJitId` [in] The identity of the JIT-recompiled function.</span></span>

<span data-ttu-id="43037-109">`cCodeStartAddresses` 진행 배열의 최대 크기 `codeStartAddresses` 입니다.</span><span class="sxs-lookup"><span data-stu-id="43037-109">`cCodeStartAddresses` [in] The maximum size of the `codeStartAddresses` array.</span></span>

<span data-ttu-id="43037-110">`pcCodeStartAddresses` 제한이 사용 가능한 주소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="43037-110">`pcCodeStartAddresses` [out] The number of available addresses.</span></span>

<span data-ttu-id="43037-111">`codeStartAddresses` 제한이 의 배열로 `UINT_PTR` , 각는 지정 된 함수에 대 한 네이티브 본문의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="43037-111">`codeStartAddresses` [out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="43037-112">설명</span><span class="sxs-lookup"><span data-stu-id="43037-112">Remarks</span></span>

<span data-ttu-id="43037-113">계층화 된 컴파일을 사용 하는 경우 함수에 둘 이상의 네이티브 코드 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43037-113">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="43037-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43037-114">Requirements</span></span>

<span data-ttu-id="43037-115">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43037-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="43037-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43037-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="43037-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43037-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="43037-118">**.Net 버전:**[!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43037-118">**.NET Versions:** [!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="43037-119">참조</span><span class="sxs-lookup"><span data-stu-id="43037-119">See also</span></span>

- [<span data-ttu-id="43037-120">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43037-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
