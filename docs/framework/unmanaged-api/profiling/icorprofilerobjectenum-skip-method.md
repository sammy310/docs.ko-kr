---
title: ICorProfilerObjectEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 096489fcdc9d604e003386501c22967b45ba6d7f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861114"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="1ca50-102">ICorProfilerObjectEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="1ca50-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="1ca50-103">지정 된 수의 요소를 건너뛰도록 현재 위치에서이 열거자의 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca50-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ca50-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ca50-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ca50-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ca50-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1ca50-106">진행 건너뛸 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca50-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ca50-107">주의</span><span class="sxs-lookup"><span data-stu-id="1ca50-107">Remarks</span></span>  
 <span data-ttu-id="1ca50-108">이 열거자 커서의 새 위치는 (현재 위치) + `celt`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca50-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ca50-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ca50-109">Requirements</span></span>  
 <span data-ttu-id="1ca50-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ca50-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ca50-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ca50-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ca50-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ca50-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ca50-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ca50-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca50-114">참조</span><span class="sxs-lookup"><span data-stu-id="1ca50-114">See also</span></span>

- [<span data-ttu-id="1ca50-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ca50-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
