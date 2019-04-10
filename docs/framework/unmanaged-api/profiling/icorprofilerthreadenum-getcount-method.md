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
ms.openlocfilehash: 8b02f70f22a7d35bf0fe7816a52c490f88b31217
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218435"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="ca1bf-102">ICorProfilerThreadEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1bf-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="ca1bf-103">응용 프로그램에서 사용하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca1bf-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca1bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca1bf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ca1bf-106">[out] 응용 프로그램에서 사용 되는 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca1bf-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca1bf-107">Requirements</span></span>  
 <span data-ttu-id="ca1bf-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1bf-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca1bf-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca1bf-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca1bf-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ca1bf-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ca1bf-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca1bf-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca1bf-112">See also</span></span>

- [<span data-ttu-id="ca1bf-113">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1bf-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="ca1bf-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1bf-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
