---
title: ICorProfilerObjectEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f08b3d9634362d47615fe14287ab9ec35e78ee65
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775048"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="09119-102">ICorProfilerObjectEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="09119-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="09119-103">컬렉션에서 고정 된 개체의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09119-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09119-104">구문</span><span class="sxs-lookup"><span data-stu-id="09119-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09119-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09119-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="09119-106">[out] 컬렉션에서 고정 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="09119-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="09119-107">이 메서드는.NET Framework 버전 3.5에에서 0이 항상 반환 서비스 팩 1 (SP1) 및 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="09119-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09119-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09119-108">Requirements</span></span>  
 <span data-ttu-id="09119-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09119-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09119-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09119-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09119-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09119-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09119-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09119-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09119-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="09119-113">See also</span></span>

- [<span data-ttu-id="09119-114">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09119-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
