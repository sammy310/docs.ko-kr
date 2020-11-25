---
title: ICorProfilerThreadEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: de2584b56701f4cffb6a108a5872641ec40e5762
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702526"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="3f4bf-102">ICorProfilerThreadEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="3f4bf-102">ICorProfilerThreadEnum::Clone Method</span></span>

<span data-ttu-id="3f4bf-103">이 [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) 인터페이스의 복사본에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f4bf-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f4bf-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f4bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f4bf-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="3f4bf-106">제한이 이 [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) 인터페이스의 복사본을 가리키는 인터페이스 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4bf-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="3f4bf-107">열거자의 복사본은이 열거자와 별도로 고유한 열거형 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4bf-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="3f4bf-108">그러나 복사본의 초기 커서 위치는 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4bf-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4bf-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f4bf-109">Requirements</span></span>  

 <span data-ttu-id="3f4bf-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f4bf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f4bf-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f4bf-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f4bf-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f4bf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f4bf-113">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4bf-114">참조</span><span class="sxs-lookup"><span data-stu-id="3f4bf-114">See also</span></span>

- [<span data-ttu-id="3f4bf-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="3f4bf-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="3f4bf-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f4bf-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
