---
title: IMethodMalloc::Alloc 메서드
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66bd56a332dc34fd35f3129256cc0e3d6c5d4508
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636693"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="b8186-102">IMethodMalloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="b8186-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="b8186-103">새 Microsoft MSIL (intermediate language) 함수 본문에 대 한 지정된 된 양의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8186-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8186-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8186-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="b8186-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8186-105">Parameters</span></span>

`cb`\
<span data-ttu-id="b8186-106">[in] 메서드 본문에 대해 할당할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b8186-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8186-107">설명</span><span class="sxs-lookup"><span data-stu-id="b8186-107">Remarks</span></span>

 <span data-ttu-id="b8186-108">할당 된 메모리가이 할당자와 연결 된 모듈의 기본 주소 보다 큰 주소에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8186-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="b8186-109">즉, 각 할당자는 특정 모듈의 경우 생성 되 고 해당 기본 주소에서 양수 오프셋에서 메모리를 할당 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8186-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="b8186-110">경우 `Alloc` 모듈의 기준 주소 보다 큰 주소에서 바이트 수가 요청 된 할당에 실패 e_outofmemory가 실제 양 사용 가능한 메모리 공간에 관계 없이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8186-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="b8186-111">합니다 `Alloc` 함께에서 메서드를 사용 해야 합니다 [icorprofilerinfo:: Setilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b8186-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8186-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8186-112">Requirements</span></span>
 <span data-ttu-id="b8186-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b8186-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="b8186-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8186-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="b8186-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8186-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="b8186-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8186-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b8186-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b8186-117">See also</span></span>

- [<span data-ttu-id="b8186-118">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8186-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
