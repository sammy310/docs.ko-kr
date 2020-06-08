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
ms.openlocfilehash: 1fe44f8f84c079e920c8c82fb9d52d1980d3b852
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497207"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="6018c-102">ICorProfilerInfo2::EnumModuleFrozenObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="6018c-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="6018c-103">지정 된 모듈의 고정 된 개체를 반복할 수 있는 열거자를 가져옵니다. 이 메서드는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6018c-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6018c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6018c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6018c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6018c-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6018c-106">진행 열거할 고정 개체가 포함 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6018c-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="6018c-107">제한이 고정 된 개체를 열거 하는 [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6018c-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6018c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6018c-108">Requirements</span></span>  
 <span data-ttu-id="6018c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6018c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6018c-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6018c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6018c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6018c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6018c-112">**.NET Framework 버전:** 3.5, 3.0 sp1, 3.0, 2.0 sp1, 2.0</span><span class="sxs-lookup"><span data-stu-id="6018c-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6018c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6018c-113">See also</span></span>

- [<span data-ttu-id="6018c-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6018c-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6018c-115">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6018c-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
