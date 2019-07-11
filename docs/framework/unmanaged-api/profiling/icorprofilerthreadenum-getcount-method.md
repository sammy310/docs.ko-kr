---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbdb9f6fc8376e080455957367dc79f4dfed8843
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781207"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="30a67-102">ICorProfilerThreadEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="30a67-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="30a67-103">응용 프로그램에서 사용하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="30a67-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a67-104">구문</span><span class="sxs-lookup"><span data-stu-id="30a67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a67-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30a67-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="30a67-106">[out] 응용 프로그램에서 사용 되는 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30a67-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a67-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30a67-107">Requirements</span></span>  
 <span data-ttu-id="30a67-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="30a67-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a67-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30a67-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30a67-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a67-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a67-111">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a67-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a67-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="30a67-112">See also</span></span>

- [<span data-ttu-id="30a67-113">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30a67-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="30a67-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30a67-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
