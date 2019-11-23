---
title: ICorProfilerInfo::GetClassFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 6999821412b3cdd614cb30858a0616c9f27a6baa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448116"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="43db6-102">ICorProfilerInfo::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="43db6-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="43db6-103">Gets the ID of the class, given the metadata token.</span><span class="sxs-lookup"><span data-stu-id="43db6-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="43db6-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="43db6-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="43db6-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span><span class="sxs-lookup"><span data-stu-id="43db6-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43db6-106">구문</span><span class="sxs-lookup"><span data-stu-id="43db6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43db6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43db6-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="43db6-108">[in] The ID of the module that contains the class.</span><span class="sxs-lookup"><span data-stu-id="43db6-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="43db6-109">[in] An `mdTypeDef` metadata token that references the class.</span><span class="sxs-lookup"><span data-stu-id="43db6-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="43db6-110">[out] A pointer to the class ID.</span><span class="sxs-lookup"><span data-stu-id="43db6-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43db6-111">주의</span><span class="sxs-lookup"><span data-stu-id="43db6-111">Remarks</span></span>  
 <span data-ttu-id="43db6-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span><span class="sxs-lookup"><span data-stu-id="43db6-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43db6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43db6-113">Requirements</span></span>  
 <span data-ttu-id="43db6-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43db6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43db6-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43db6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43db6-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43db6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43db6-117">**.NET Framework Versions:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="43db6-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43db6-118">참조</span><span class="sxs-lookup"><span data-stu-id="43db6-118">See also</span></span>

- [<span data-ttu-id="43db6-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43db6-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
