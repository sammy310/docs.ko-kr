---
title: ICorProfilerInfo::GetFunctionFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 18c3b6e840ec1f6cb1481c8d752e6399dcdae077
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498143"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="991e5-102">ICorProfilerInfo::GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="991e5-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="991e5-103">함수의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="991e5-103">Gets the ID of a function.</span></span> <span data-ttu-id="991e5-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="991e5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="991e5-105">대신 [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="991e5-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="991e5-106">구문</span><span class="sxs-lookup"><span data-stu-id="991e5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="991e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="991e5-107">Remarks</span></span>  
 <span data-ttu-id="991e5-108">메서드는 제네릭 `GetFunctionFromToken` 함수 또는 제네릭 형식의 함수에 대해 작동 하지 않습니다. 이제는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="991e5-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="991e5-109">`ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`모든 함수에 대해를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="991e5-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="991e5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="991e5-110">Requirements</span></span>  
 <span data-ttu-id="991e5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="991e5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="991e5-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="991e5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="991e5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="991e5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="991e5-114">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="991e5-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991e5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="991e5-115">See also</span></span>

- [<span data-ttu-id="991e5-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="991e5-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
