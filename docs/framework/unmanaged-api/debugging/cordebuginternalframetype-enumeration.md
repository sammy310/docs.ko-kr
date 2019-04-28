---
title: CorDebugInternalFrameType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05184ceb3b32eb003951fff5cfdfbfb813992552
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792862"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="4e85d-102">CorDebugInternalFrameType 열거형</span><span class="sxs-lookup"><span data-stu-id="4e85d-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="4e85d-103">스택 프레임 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="4e85d-104">이 열거형은에서 사용 된 [icordebuginternalframe:: Getframetype](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4e85d-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e85d-105">구문</span><span class="sxs-lookup"><span data-stu-id="4e85d-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="4e85d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4e85d-106">Members</span></span>  
  
|<span data-ttu-id="4e85d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4e85d-107">Member</span></span>|<span data-ttu-id="4e85d-108">설명</span><span class="sxs-lookup"><span data-stu-id="4e85d-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="4e85d-109">null 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-109">A null value.</span></span> <span data-ttu-id="4e85d-110">`ICorDebugInternalFrame::GetFrameType` 메서드는이 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="4e85d-111">관리-비관리 스텁 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="4e85d-112">관리 되지 않는-managed 스텁 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="4e85d-113">응용 프로그램 도메인 간에 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="4e85d-114">간단한 메서드 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="4e85d-115">함수 실행의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="4e85d-116">공용 언어 런타임에 대 한 내부 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="4e85d-117">클래스 초기화를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="4e85d-118">예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="4e85d-119">코드 액세스 보안에 사용 되는 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="4e85d-120">런타임은 메서드를 JIT 컴파일하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4e85d-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e85d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e85d-121">Requirements</span></span>  
 <span data-ttu-id="4e85d-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e85d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e85d-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e85d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e85d-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e85d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e85d-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e85d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e85d-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e85d-126">See also</span></span>

- [<span data-ttu-id="4e85d-127">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="4e85d-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
