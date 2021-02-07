---
description: '자세히 알아보기: ICorProfilerInfo7:: Getinmemory기호 Slength 메서드'
title: 'ICorProfilerInfo7:: Getinmemory기호 Slength 메서드'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: 5d96b17e8abbd023f2d050eff3f121a871a94754
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737118"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="e50e5-103">ICorProfilerInfo7:: Getinmemory기호 Slength 메서드</span><span class="sxs-lookup"><span data-stu-id="e50e5-103">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>

<span data-ttu-id="e50e5-104">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="e50e5-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="e50e5-105">메모리 내 기호 스트림의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e50e5-105">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e50e5-106">구문</span><span class="sxs-lookup"><span data-stu-id="e50e5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e50e5-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e50e5-107">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="e50e5-108">진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e50e5-108">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="e50e5-109">Pcount기호 바이트</span><span class="sxs-lookup"><span data-stu-id="e50e5-109">pCountSymbolBytes</span></span>  
 <span data-ttu-id="e50e5-110">제한이 `DWORD` 메서드가 반환 될 때 스트림의 길이 (바이트)를 포함 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e50e5-110">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e50e5-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="e50e5-111">Return Value</span></span>  

 <span data-ttu-id="e50e5-112">`S_OK`메모리 스트림의 길이가 0 인 경우에도이 메서드는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e50e5-112">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="e50e5-113">메서드는를 `CORPROF_E_MODULE_IS_DYNAMIC` 사용 하 여 메서드를 만든 경우를 반환 합니다 <xref:System.Reflection.Emit?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e50e5-113">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e50e5-114">설명</span><span class="sxs-lookup"><span data-stu-id="e50e5-114">Remarks</span></span>  

 <span data-ttu-id="e50e5-115">모듈에 메모리 내 기호가 있으면 스트림의 길이가에 배치 됩니다 `pCountSymbolBytes` .</span><span class="sxs-lookup"><span data-stu-id="e50e5-115">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="e50e5-116">모듈에 메모리 내 `*pCountSymbolBytes = 0` 기호 ()가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="e50e5-116">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e50e5-117">현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e50e5-117">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="e50e5-118">리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는를 반환 합니다 `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="e50e5-118">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e50e5-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e50e5-119">Requirements</span></span>  

 <span data-ttu-id="e50e5-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e50e5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e50e5-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e50e5-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e50e5-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e50e5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e50e5-123">**.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e50e5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50e5-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e50e5-124">See also</span></span>

- [<span data-ttu-id="e50e5-125">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e50e5-125">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
