---
title: ICorProfilerInfo2::EnumModuleFrozenObjects 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: fe4f3a7355339c9b5adbe5de062f0a5688d81c23
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727187"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="fb60e-102">ICorProfilerInfo2::EnumModuleFrozenObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="fb60e-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>

<span data-ttu-id="fb60e-103">지정 된 모듈의 고정 된 개체를 반복할 수 있는 열거자를 가져옵니다. 이 메서드는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb60e-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb60e-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb60e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb60e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb60e-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="fb60e-106">진행 열거할 고정 개체가 포함 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fb60e-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="fb60e-107">제한이 고정 된 개체를 열거 하는 [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb60e-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb60e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb60e-108">Requirements</span></span>  

 <span data-ttu-id="fb60e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb60e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb60e-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb60e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb60e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb60e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb60e-112">**.NET Framework 버전:** 3.5, 3.0 sp1, 3.0, 2.0 sp1, 2.0</span><span class="sxs-lookup"><span data-stu-id="fb60e-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb60e-113">참조</span><span class="sxs-lookup"><span data-stu-id="fb60e-113">See also</span></span>

- [<span data-ttu-id="fb60e-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb60e-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="fb60e-115">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb60e-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
