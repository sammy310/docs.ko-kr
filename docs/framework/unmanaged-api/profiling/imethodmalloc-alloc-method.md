---
description: '자세한 정보: IMethodMalloc:: Alloc 메서드'
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
ms.openlocfilehash: f8a41530e0e1a126fafa1816e6fed58d10df6587
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736954"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="ac76a-103">IMethodMalloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="ac76a-103">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="ac76a-104">새 MSIL (Microsoft 중간 언어) 함수 본문에 지정 된 양의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac76a-104">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac76a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac76a-105">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="ac76a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac76a-106">Parameters</span></span>

`cb`\
<span data-ttu-id="ac76a-107">진행 메서드 본문에 할당할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac76a-107">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac76a-108">설명</span><span class="sxs-lookup"><span data-stu-id="ac76a-108">Remarks</span></span>

 <span data-ttu-id="ac76a-109">할당 된 메모리는이 할당자와 연결 된 모듈의 기본 주소 보다 큰 주소에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac76a-109">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="ac76a-110">즉, 각 할당자는 특정 모듈에 대해 만들어지며 기본 주소에서 양의 오프셋으로 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac76a-110">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="ac76a-111">에서 `Alloc` 모듈의 기본 주소 보다 큰 주소에서 요청 된 바이트 수를 할당 하지 못하면 사용 가능한 실제 메모리 공간의 크기에 관계 없이 E_OUTOFMEMORY 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac76a-111">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="ac76a-112">`Alloc`메서드는 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac76a-112">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac76a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac76a-113">Requirements</span></span>

 <span data-ttu-id="ac76a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac76a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ac76a-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac76a-115">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="ac76a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac76a-116">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="ac76a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac76a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ac76a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac76a-118">See also</span></span>

- [<span data-ttu-id="ac76a-119">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac76a-119">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
