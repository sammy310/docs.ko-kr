---
description: '자세히 알아보기: ICorProfilerInfo:: GetILFunctionBodyAllocator 메서드'
title: ICorProfilerInfo::GetILFunctionBodyAllocator 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: 25d059d784fe64231d4d2ff3d23b4820443873cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647429"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="a6cb8-103">ICorProfilerInfo::GetILFunctionBodyAllocator 메서드</span><span class="sxs-lookup"><span data-stu-id="a6cb8-103">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>

<span data-ttu-id="a6cb8-104">MSIL (Microsoft 중간 언어) 코드에서 메서드의 본문을 교환 하는 데 사용할 메모리를 할당 하는 메서드를 제공 하는 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6cb8-104">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6cb8-105">구문</span><span class="sxs-lookup"><span data-stu-id="a6cb8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6cb8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6cb8-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="a6cb8-107">진행 메서드가 있는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cb8-107">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="a6cb8-108">제한이 메모리를 할당 하는 메서드를 제공 하는 [Imethodmalloc](imethodmalloc-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cb8-108">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6cb8-109">설명</span><span class="sxs-lookup"><span data-stu-id="a6cb8-109">Remarks</span></span>  

 <span data-ttu-id="a6cb8-110">MSIL 코드의 메서드 본문은 로드 된 모듈을 기준으로 하는 RVA (상대 가상 주소)로 배치 되어야 합니다. 즉, 4gb 내에서 모듈을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6cb8-110">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="a6cb8-111">도구를 사용 하 여 메서드의 본문을 쉽게 교환할 수 있도록 `GetILFunctionBodyAllocator` 메서드는 해당 범위 내에서 메모리가 할당 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cb8-111">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6cb8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6cb8-112">Requirements</span></span>  

 <span data-ttu-id="a6cb8-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6cb8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6cb8-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6cb8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6cb8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6cb8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6cb8-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6cb8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6cb8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6cb8-117">See also</span></span>

- [<span data-ttu-id="a6cb8-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6cb8-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
