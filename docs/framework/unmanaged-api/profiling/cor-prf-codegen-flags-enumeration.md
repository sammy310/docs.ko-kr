---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_CODEGEN_FLAGS'
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
ms.openlocfilehash: 40ddaa77047e0b1daa743b512f21ba7643127230
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649178"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="ea08e-103">COR_PRF_CODEGEN_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="ea08e-103">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>

<span data-ttu-id="ea08e-104">[ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드를 사용 하 여 설정할 수 있는 코드 생성 플래그를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea08e-104">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea08e-105">구문</span><span class="sxs-lookup"><span data-stu-id="ea08e-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ea08e-106">구성원</span><span class="sxs-lookup"><span data-stu-id="ea08e-106">Members</span></span>  
  
|<span data-ttu-id="ea08e-107">멤버</span><span class="sxs-lookup"><span data-stu-id="ea08e-107">Member</span></span>|<span data-ttu-id="ea08e-108">설명</span><span class="sxs-lookup"><span data-stu-id="ea08e-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="ea08e-109">이 함수의 본문에는 함수가 인라인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea08e-109">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="ea08e-110">그러나 함수 자체가 해당 호출자에 게 인라인 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea08e-110">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="ea08e-111">이 함수의 본문에 대해 모든 최적화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea08e-111">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="ea08e-112">그러나 함수 자체는 여전히 해당 호출자에 게 인라인 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea08e-112">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea08e-113">설명</span><span class="sxs-lookup"><span data-stu-id="ea08e-113">Remarks</span></span>  

 <span data-ttu-id="ea08e-114">`COR_PRF_CODEGEN_FLAGS`열거형은 [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드에서 프로파일러를 사용 하 여 JIT 다시 컴파일된 함수의 코드 생성을 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea08e-114">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea08e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea08e-115">Requirements</span></span>  

 <span data-ttu-id="ea08e-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea08e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea08e-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea08e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea08e-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea08e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea08e-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea08e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea08e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea08e-120">See also</span></span>

- [<span data-ttu-id="ea08e-121">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="ea08e-121">Profiling Enumerations</span></span>](profiling-enumerations.md)
