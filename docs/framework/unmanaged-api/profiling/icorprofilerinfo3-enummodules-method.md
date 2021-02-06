---
description: '자세히 알아보기: ICorProfilerInfo3:: EnumModules 메서드'
title: ICorProfilerInfo3::EnumModules 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
ms.openlocfilehash: 9cdb76b77f78fa68eafa111e60b31b738173d658
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646857"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="11a17-103">ICorProfilerInfo3::EnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="11a17-103">ICorProfilerInfo3::EnumModules Method</span></span>

<span data-ttu-id="11a17-104">애플리케이션에 로드되는 관리 모듈 컬렉션을 순차적으로 반복하는 메서드를 제공하는 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11a17-104">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a17-105">구문</span><span class="sxs-lookup"><span data-stu-id="11a17-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a17-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11a17-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="11a17-107">제한이 [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11a17-107">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a17-108">설명</span><span class="sxs-lookup"><span data-stu-id="11a17-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a17-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11a17-109">Requirements</span></span>  

 <span data-ttu-id="11a17-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11a17-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a17-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11a17-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11a17-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11a17-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11a17-113">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a17-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11a17-114">See also</span></span>

- [<span data-ttu-id="11a17-115">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11a17-115">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="11a17-116">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11a17-116">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="11a17-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11a17-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="11a17-118">프로파일링</span><span class="sxs-lookup"><span data-stu-id="11a17-118">Profiling</span></span>](index.md)
