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
ms.openlocfilehash: 2b2d619c5940376806e9873a528b4f08886593e9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863558"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="6d6dd-102">ICorProfilerInfo::GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="6d6dd-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="6d6dd-103">함수의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-103">Gets the ID of a function.</span></span> <span data-ttu-id="6d6dd-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6d6dd-105">대신 [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6dd-106">구문</span><span class="sxs-lookup"><span data-stu-id="6d6dd-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6d6dd-107">주의</span><span class="sxs-lookup"><span data-stu-id="6d6dd-107">Remarks</span></span>  
 <span data-ttu-id="6d6dd-108">제네릭 함수 또는 제네릭 형식의 함수에는 `GetFunctionFromToken` 메서드를 사용할 수 없습니다. 이제 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="6d6dd-109">모든 함수에 대해 `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6dd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d6dd-110">Requirements</span></span>  
 <span data-ttu-id="6d6dd-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6dd-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d6dd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d6dd-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d6dd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d6dd-114">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="6d6dd-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6dd-115">참조</span><span class="sxs-lookup"><span data-stu-id="6d6dd-115">See also</span></span>

- [<span data-ttu-id="6d6dd-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d6dd-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
