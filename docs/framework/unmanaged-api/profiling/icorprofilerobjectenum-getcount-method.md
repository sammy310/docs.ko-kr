---
description: '자세히 알아보기: ICorProfilerObjectEnum:: GetCount 메서드'
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
ms.openlocfilehash: b1bedfca913a099f88780807021497d15f75fcd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798942"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="82cbf-103">ICorProfilerObjectEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="82cbf-103">ICorProfilerObjectEnum::GetCount Method</span></span>

<span data-ttu-id="82cbf-104">컬렉션에 있는 고정 된 개체의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82cbf-104">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cbf-105">구문</span><span class="sxs-lookup"><span data-stu-id="82cbf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82cbf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82cbf-106">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="82cbf-107">제한이 컬렉션의 고정 된 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82cbf-107">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="82cbf-108">이 메서드는 .NET Framework 버전 3.5 SP1 (서비스 팩 1) 이상 버전에서 항상 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82cbf-108">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82cbf-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82cbf-109">Requirements</span></span>  

 <span data-ttu-id="82cbf-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82cbf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82cbf-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82cbf-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82cbf-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82cbf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82cbf-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82cbf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cbf-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82cbf-114">See also</span></span>

- [<span data-ttu-id="82cbf-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82cbf-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
