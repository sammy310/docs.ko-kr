---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365323"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="c0ddf-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="c0ddf-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="c0ddf-103">인라인 지정된 메서드를 지정 된 NGen 모듈에 정의 된 모든 메서드는 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0ddf-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0ddf-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="c0ddf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0ddf-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="c0ddf-106">[in] NGen 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="c0ddf-107">[in] 정의 하는 모듈의 식별자 `inlineeMethodId`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="c0ddf-108">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="c0ddf-109">[in] 인라인 메서드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="c0ddf-110">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="c0ddf-111">[out] 나타내는 플래그 있는지 여부를 `ppEnum` 지정된 메서드를 인라인 처리 하는 모든 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="c0ddf-112">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="c0ddf-113">[out] 열거자의 주소에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="c0ddf-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="c0ddf-114">설명</span><span class="sxs-lookup"><span data-stu-id="c0ddf-114">Remarks</span></span>

<span data-ttu-id="c0ddf-115">`inlineeModuleId` 및 `inlineeMethodId` 인라인 처리 하지 않을 수 있는 메서드에 대 한 전체 식별자를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="c0ddf-116">예를 들어 모듈 `A` 메서드를 정의 `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="c0ddf-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="c0ddf-117">모듈 B 정의 `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="c0ddf-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="c0ddf-118">또한 가정 있습니다 `Fancy.AddTwice` 인라인 호출을 `SimpleAdd`입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="c0ddf-119">프로파일러를 사용 하 여이 열거자는 인라인이 모듈 B의에서 정의 된 모든 메서드를 찾을 `Simple.Add`, 하 고 결과 열거는 `AddTwice`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="c0ddf-120">`inlineeModuleId` 모듈의 식별자 `A`, 및 `inlineeMethodId` 의 식별자 `Simple.Add(int a, int b)`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="c0ddf-121">경우 `incompleteData` 함수 뒤도 마찬가지 열거자에 없는 인라인 처리 하는 모든 메서드는 지정 된 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="c0ddf-122">이 경우 발생할 수 있습니다 또는 inliners 모듈의 직접 또는 간접 종속성 보다 아직 로드 하지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="c0ddf-123">프로파일러에 정확한 데이터가 필요 이상의 모듈이 로드 되는 경우 가급적 각 모듈을 로드할 때 나중에 재시도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="c0ddf-124">`EnumNgenModuleMethodsInliningThisMethod` 에서 제한 사항을 해결 하려면 메서드를 사용할 수 ReJIT에 대 한 인라인 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="c0ddf-125">ReJIT 메서드의 구현을 변경 하 고 만든 다음 새 코드를 즉석에서 프로파일러를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="c0ddf-126">예를 들어 변경 수 `Simple.Add` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="c0ddf-127">그러나 때문 `Fancy.AddTwice` 에 이미 인라인 `Simple.Add`, 동일 하 게 동작 이전과 같이 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="c0ddf-128">호출자가 해당 한계를 해결 하기 위해 인라인 있는 모든 모듈의 모든 메서드에 대 한 검색 `Simple.Add` 사용 하 여 `ICorProfilerInfo5::RequestRejit` 해당 메서드의 각 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="c0ddf-129">새 동작을 갖습니다 메서드 다시 컴파일된 경우 `Simple.Add` 이전 동작을 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0ddf-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0ddf-130">Requirements</span></span>

<span data-ttu-id="c0ddf-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0ddf-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c0ddf-132">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0ddf-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c0ddf-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ddf-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c0ddf-134">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ddf-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c0ddf-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0ddf-135">See also</span></span>

- [<span data-ttu-id="c0ddf-136">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0ddf-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)