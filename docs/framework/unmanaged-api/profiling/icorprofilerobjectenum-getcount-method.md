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
ms.openlocfilehash: a1a616c1289867864eb9eb449c7d6f47f9a8352b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861296"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="62a52-102">ICorProfilerObjectEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="62a52-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="62a52-103">컬렉션에 있는 고정 된 개체의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62a52-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a52-104">구문</span><span class="sxs-lookup"><span data-stu-id="62a52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62a52-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62a52-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="62a52-106">제한이 컬렉션의 고정 된 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62a52-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="62a52-107">이 메서드는 .NET Framework 버전 3.5 SP1 (서비스 팩 1) 이상 버전에서 항상 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a52-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62a52-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62a52-108">Requirements</span></span>  
 <span data-ttu-id="62a52-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62a52-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62a52-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62a52-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62a52-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62a52-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62a52-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62a52-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a52-113">참조</span><span class="sxs-lookup"><span data-stu-id="62a52-113">See also</span></span>

- [<span data-ttu-id="62a52-114">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62a52-114">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
