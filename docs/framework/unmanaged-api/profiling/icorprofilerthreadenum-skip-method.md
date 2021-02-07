---
description: '자세히 알아보기: ICorProfilerThreadEnum:: Skip 메서드'
title: ICorProfilerThreadEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: 1da191980364868ed4237fccaf7495d5417705cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736897"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="d9a05-103">ICorProfilerThreadEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="d9a05-103">ICorProfilerThreadEnum::Skip Method</span></span>

<span data-ttu-id="d9a05-104">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a05-104">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a05-105">구문</span><span class="sxs-lookup"><span data-stu-id="d9a05-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9a05-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9a05-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="d9a05-107">진행 건너뛸 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9a05-107">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9a05-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="d9a05-108">Return Value</span></span>  

 <span data-ttu-id="d9a05-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a05-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d9a05-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9a05-110">HRESULT</span></span>|<span data-ttu-id="d9a05-111">설명</span><span class="sxs-lookup"><span data-stu-id="d9a05-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9a05-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9a05-112">S_OK</span></span>|<span data-ttu-id="d9a05-113">`celt` 요소를 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a05-113">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="d9a05-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d9a05-114">S_FALSE</span></span>|<span data-ttu-id="d9a05-115">요소 `celt` 수를 건너 뛰 었으 며 더 이상 요소가 없다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9a05-115">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9a05-116">설명</span><span class="sxs-lookup"><span data-stu-id="d9a05-116">Remarks</span></span>  

 <span data-ttu-id="d9a05-117">이 열거자 커서의 새 위치는 (현재 위치) + `celt` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d9a05-117">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9a05-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9a05-118">Requirements</span></span>  

 <span data-ttu-id="d9a05-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9a05-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9a05-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9a05-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9a05-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9a05-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9a05-122">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9a05-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a05-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9a05-123">See also</span></span>

- [<span data-ttu-id="d9a05-124">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9a05-124">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="d9a05-125">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9a05-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
