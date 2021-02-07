---
description: '자세히 알아보기: ICorProfilerInfo:: SetILInstrumentedCodeMap 메서드'
title: ICorProfilerInfo::SetILInstrumentedCodeMap 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
ms.openlocfilehash: 0cf3b4ccf31076c2d1ea2df581003e3a07f0e795
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737352"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="cda73-103">ICorProfilerInfo::SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="cda73-103">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>

<span data-ttu-id="cda73-104">지정 된 MSIL (Microsoft 중간 언어) 맵 항목을 사용 하 여 지정 된 함수에 대 한 코드 맵을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-104">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>

> [!NOTE]
> <span data-ttu-id="cda73-105">.NET Framework 버전 2.0에서 `SetILInstrumentedCodeMap` `FunctionID` 특정 응용 프로그램 도메인의 제네릭 함수를 나타내는에 대해를 호출 하면 응용 프로그램 도메인에 있는 해당 함수의 모든 인스턴스에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-105">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>

## <a name="syntax"></a><span data-ttu-id="cda73-106">구문</span><span class="sxs-lookup"><span data-stu-id="cda73-106">Syntax</span></span>

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a><span data-ttu-id="cda73-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cda73-107">Parameters</span></span>

`functionId`\
<span data-ttu-id="cda73-108">진행 코드 맵을 설정할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-108">[in] The ID of the function for which to set the code map.</span></span>

`fStartJit`\
<span data-ttu-id="cda73-109">진행 `SetILInstrumentedCodeMap` 메서드에 대 한 호출이 특정에 대해 첫 번째 인지 여부를 나타내는 부울 값입니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="cda73-109">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="cda73-110">지정 된에 `fStartJit` `true` 대 한 첫 번째 호출에서을로 설정 하 `SetILInstrumentedCodeMap` `FunctionID` 고, 그 이후에를로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-110">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>

`cILMapEntries`\
<span data-ttu-id="cda73-111">진행 배열의 요소 수 `cILMapEntries` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-111">[in] The number of elements in the `cILMapEntries` array.</span></span>

`rgILMapEntries`\
<span data-ttu-id="cda73-112">진행 각각 MSIL 오프셋을 지정 하는 COR_IL_MAP 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-112">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>

## <a name="remarks"></a><span data-ttu-id="cda73-113">설명</span><span class="sxs-lookup"><span data-stu-id="cda73-113">Remarks</span></span>

<span data-ttu-id="cda73-114">프로파일러는 메서드를 계측 하기 위해 메서드 소스 코드 내에 문을 삽입 하는 경우가 있습니다. 예를 들어 지정 된 소스 줄에 도달할 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-114">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="cda73-115">`SetILInstrumentedCodeMap` 프로파일러가 원래 MSIL 명령을 새 위치에 매핑할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-115">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="cda73-116">프로파일러는 [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) 메서드를 사용 하 여 지정 된 네이티브 오프셋의 원래 MSIL 오프셋을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-116">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>

<span data-ttu-id="cda73-117">디버거는 각각의 이전 오프셋이 원래 수정 되지 않은 MSIL 코드 내에서 MSIL 오프셋을 참조 하 고 각각의 새 오프셋이 새로운 계측 된 코드 내에서 MSIL 오프셋을 참조 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-117">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="cda73-118">맵은 오름차순으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-118">The map should be sorted in increasing order.</span></span> <span data-ttu-id="cda73-119">단계별 실행이 제대로 작동 하려면 다음 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cda73-119">For stepping to work properly, follow these guidelines:</span></span>

- <span data-ttu-id="cda73-120">계측 된 MSIL 코드를 다시 정렬 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-120">Do not reorder instrumented MSIL code.</span></span>

- <span data-ttu-id="cda73-121">원래 MSIL 코드를 제거 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="cda73-121">Do not remove the original MSIL code.</span></span>

- <span data-ttu-id="cda73-122">맵의 PDB (프로그램 데이터베이스) 파일에서 모든 시퀀스 위치에 대 한 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-122">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="cda73-123">지도는 누락 된 항목을 보간 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-123">The map does not interpolate missing entries.</span></span> <span data-ttu-id="cda73-124">따라서 다음 맵이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-124">So, given the following map:</span></span>

  <span data-ttu-id="cda73-125">(0 이전, 0 개 새로 만들기)</span><span class="sxs-lookup"><span data-stu-id="cda73-125">(0 old, 0 new)</span></span>

  <span data-ttu-id="cda73-126">(5 이전, 10 개 새)</span><span class="sxs-lookup"><span data-stu-id="cda73-126">(5 old, 10 new)</span></span>

  <span data-ttu-id="cda73-127">(9 이전, 20 개 새로 만들기)</span><span class="sxs-lookup"><span data-stu-id="cda73-127">(9 old, 20 new)</span></span>

  - <span data-ttu-id="cda73-128">0, 1, 2, 3 또는 4의 이전 오프셋은 새 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-128">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>

  - <span data-ttu-id="cda73-129">5, 6, 7 또는 8의 이전 오프셋은 새 오프셋 10에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-129">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>

  - <span data-ttu-id="cda73-130">이전 오프셋 9 이상은 새 오프셋 20에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-130">An old offset of 9 or higher will be mapped to new offset 20.</span></span>

  - <span data-ttu-id="cda73-131">0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9의 새 오프셋은 이전 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-131">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>

  - <span data-ttu-id="cda73-132">새 오프셋 10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19는 이전 오프셋 5에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-132">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>

  - <span data-ttu-id="cda73-133">새 오프셋 20 이상은 이전 오프셋 9에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-133">A new offset of 20 or higher will be mapped to old offset 9.</span></span>

<span data-ttu-id="cda73-134">.NET Framework 3.5 및 이전 버전에서는 `rgILMapEntries` [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) 메서드를 호출 하 여 배열을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-134">In the .NET Framework 3.5 and previous versions, you allocate the `rgILMapEntries` array by calling the [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) method.</span></span> <span data-ttu-id="cda73-135">런타임에서는이 메모리의 소유권을 가지 므로 프로파일러를 해제 하려고 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda73-135">Because the runtime takes ownership of this memory, the profiler should not attempt to free it.</span></span>

## <a name="requirements"></a><span data-ttu-id="cda73-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cda73-136">Requirements</span></span>

<span data-ttu-id="cda73-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cda73-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="cda73-138">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cda73-138">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="cda73-139">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cda73-139">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="cda73-140">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda73-140">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cda73-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cda73-141">See also</span></span>

- [<span data-ttu-id="cda73-142">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cda73-142">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
