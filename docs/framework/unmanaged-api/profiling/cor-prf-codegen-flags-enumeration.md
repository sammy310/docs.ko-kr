---
title: COR_PRF_CODEGEN_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 190774b17d6e8214dd2358edb74f3eaf3b079fc2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782669"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="d807f-102">COR_PRF_CODEGEN_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="d807f-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="d807f-103">사용 하 여 설정할 수 있는 코드 생성 플래그를 정의 합니다 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d807f-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d807f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d807f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d807f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d807f-105">Members</span></span>  
  
|<span data-ttu-id="d807f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d807f-106">Member</span></span>|<span data-ttu-id="d807f-107">Description</span><span class="sxs-lookup"><span data-stu-id="d807f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="d807f-108">함수가 없습니다.이 함수 본문으로 인라인 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d807f-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="d807f-109">그러나 함수 자체 해당 호출자에 인라인 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d807f-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="d807f-110">이 함수 본문에 대 한 모든 최적화 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d807f-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="d807f-111">그러나 함수 자체 여전히 못할 해당 호출자에 인라인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d807f-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d807f-112">설명</span><span class="sxs-lookup"><span data-stu-id="d807f-112">Remarks</span></span>  
 <span data-ttu-id="d807f-113">합니다 `COR_PRF_CODEGEN_FLAGS` 열거형에서 사용 되는 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) JIT 다시 컴파일된 함수에 대 한 코드 생성을 제어 하려면 프로파일러를 사용 하도록 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d807f-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d807f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d807f-114">Requirements</span></span>  
 <span data-ttu-id="d807f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d807f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d807f-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d807f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d807f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d807f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d807f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d807f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d807f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="d807f-119">See also</span></span>

- [<span data-ttu-id="d807f-120">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="d807f-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
