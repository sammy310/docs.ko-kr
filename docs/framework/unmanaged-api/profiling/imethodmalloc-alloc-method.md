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
ms.openlocfilehash: 58809f12e4dd4419b754caafc3f8b883b8bc5089
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721168"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="4e066-102">IMethodMalloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="4e066-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="4e066-103">새 MSIL (Microsoft 중간 언어) 함수 본문에 지정 된 양의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e066-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e066-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="4e066-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e066-105">Parameters</span></span>

`cb`\
<span data-ttu-id="4e066-106">진행 메서드 본문에 할당할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e066-107">설명</span><span class="sxs-lookup"><span data-stu-id="4e066-107">Remarks</span></span>

 <span data-ttu-id="4e066-108">할당 된 메모리는이 할당자와 연결 된 모듈의 기본 주소 보다 큰 주소에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="4e066-109">즉, 각 할당자는 특정 모듈에 대해 만들어지며 기본 주소에서 양의 오프셋으로 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="4e066-110">에서 `Alloc` 모듈의 기본 주소 보다 큰 주소에서 요청 된 바이트 수를 할당 하지 못하면 사용 가능한 실제 메모리 공간의 크기에 관계 없이 E_OUTOFMEMORY 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="4e066-111">`Alloc`메서드는 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e066-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e066-112">Requirements</span></span>

 <span data-ttu-id="4e066-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e066-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="4e066-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e066-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="4e066-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e066-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="4e066-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e066-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4e066-117">참조</span><span class="sxs-lookup"><span data-stu-id="4e066-117">See also</span></span>

- [<span data-ttu-id="4e066-118">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e066-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
