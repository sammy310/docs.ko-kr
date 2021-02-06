---
description: '자세히 알아보기: ICorProfilerInfo:: GetFunctionFromToken 메서드'
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
ms.openlocfilehash: 58dea413539d6e3a625f515aa7e8d5123152c90a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647455"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="b692e-103">ICorProfilerInfo::GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="b692e-103">ICorProfilerInfo::GetFunctionFromToken Method</span></span>

<span data-ttu-id="b692e-104">함수의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b692e-104">Gets the ID of a function.</span></span> <span data-ttu-id="b692e-105">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b692e-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b692e-106">대신 [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b692e-106">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b692e-107">구문</span><span class="sxs-lookup"><span data-stu-id="b692e-107">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="b692e-108">설명</span><span class="sxs-lookup"><span data-stu-id="b692e-108">Remarks</span></span>  

 <span data-ttu-id="b692e-109">메서드는 제네릭 `GetFunctionFromToken` 함수 또는 제네릭 형식의 함수에 대해 작동 하지 않습니다. 이제는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b692e-109">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="b692e-110">`ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`모든 함수에 대해를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b692e-110">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b692e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b692e-111">Requirements</span></span>  

 <span data-ttu-id="b692e-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b692e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b692e-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b692e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b692e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b692e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b692e-115">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="b692e-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b692e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b692e-116">See also</span></span>

- [<span data-ttu-id="b692e-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b692e-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
