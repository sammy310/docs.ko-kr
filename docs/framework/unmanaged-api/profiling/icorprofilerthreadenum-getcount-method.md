---
description: '자세히 알아보기: ICorProfilerThreadEnum:: GetCount 메서드'
title: ICorProfilerThreadEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: 5219dfc71b79be82f769ac7c8230beaf62c6f33e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646428"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="f86b7-103">ICorProfilerThreadEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="f86b7-103">ICorProfilerThreadEnum::GetCount Method</span></span>

<span data-ttu-id="f86b7-104">애플리케이션에서 사용하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f86b7-104">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f86b7-105">구문</span><span class="sxs-lookup"><span data-stu-id="f86b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f86b7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f86b7-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f86b7-107">제한이 응용 프로그램에서 사용 하는 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f86b7-107">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f86b7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f86b7-108">Requirements</span></span>  

 <span data-ttu-id="f86b7-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f86b7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f86b7-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f86b7-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f86b7-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f86b7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f86b7-112">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f86b7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86b7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f86b7-113">See also</span></span>

- [<span data-ttu-id="f86b7-114">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f86b7-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="f86b7-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f86b7-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
