---
title: ICorProfilerCallback::ModuleAttachedToAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: 4f494919d11e0f979cf1964c08106fbb9b9ed20b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503395"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="ed2e5-102">ICorProfilerCallback::ModuleAttachedToAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="ed2e5-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="ed2e5-103">모듈이 부모 어셈블리에 연결 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed2e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed2e5-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed2e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed2e5-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ed2e5-106">진행 연결 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="ed2e5-107">진행 모듈이 연결 된 부모 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed2e5-108">설명</span><span class="sxs-lookup"><span data-stu-id="ed2e5-108">Remarks</span></span>  
 <span data-ttu-id="ed2e5-109">모듈은 IAT (가져오기 주소 테이블)를 통해 또는 호출을 통해 `LoadLibrary` 또는 메타 데이터 참조를 통해 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="ed2e5-110">결과적으로 CLR (공용 언어 런타임) 로더는 모듈이 있는 어셈블리를 확인 하기 위한 여러 코드 경로를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="ed2e5-111">따라서 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 를 호출한 후 모듈에서 해당 어셈블리를 인식 하지 못하면 부모 어셈블리 ID를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="ed2e5-112">`ModuleAttachedToAssembly`모듈을 부모 어셈블리에 연결 하 고 부모 어셈블리 ID를 가져올 수 있는 경우 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed2e5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed2e5-113">Requirements</span></span>  
 <span data-ttu-id="ed2e5-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed2e5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed2e5-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed2e5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed2e5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed2e5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed2e5-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed2e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed2e5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed2e5-118">See also</span></span>

- [<span data-ttu-id="ed2e5-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed2e5-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
