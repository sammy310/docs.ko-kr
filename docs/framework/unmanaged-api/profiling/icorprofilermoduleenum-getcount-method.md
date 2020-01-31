---
title: ICorProfilerModuleEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
ms.openlocfilehash: 772a7c08c934fda59a2764e1fbe22d3d2b08a620
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861504"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="060cd-102">ICorProfilerModuleEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="060cd-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="060cd-103">애플리케이션에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="060cd-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="060cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="060cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="060cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="060cd-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="060cd-106">제한이 컬렉션의 런타임 모듈 수입니다.</span><span class="sxs-lookup"><span data-stu-id="060cd-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="060cd-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="060cd-107">Requirements</span></span>  
 <span data-ttu-id="060cd-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="060cd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="060cd-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="060cd-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="060cd-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="060cd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="060cd-111">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="060cd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060cd-112">참조</span><span class="sxs-lookup"><span data-stu-id="060cd-112">See also</span></span>

- [<span data-ttu-id="060cd-113">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="060cd-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="060cd-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="060cd-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
