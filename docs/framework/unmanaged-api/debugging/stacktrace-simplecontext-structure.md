---
title: StackTrace_SimpleContext 구조체
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc0fc18e31b89b22ffd30d99a8b079ed7b87fa1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752493"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="49a85-102">StackTrace_SimpleContext 구조체</span><span class="sxs-lookup"><span data-stu-id="49a85-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="49a85-103">전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49a85-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49a85-104">구문</span><span class="sxs-lookup"><span data-stu-id="49a85-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="49a85-105">멤버</span><span class="sxs-lookup"><span data-stu-id="49a85-105">Members</span></span>  
  
|<span data-ttu-id="49a85-106">멤버</span><span class="sxs-lookup"><span data-stu-id="49a85-106">Member</span></span>|<span data-ttu-id="49a85-107">Description</span><span class="sxs-lookup"><span data-stu-id="49a85-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="49a85-108">스택 포인터 또는 x86 enter 스택 포인터 (ESP) 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="49a85-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="49a85-109">프레임 오프셋 또는 x86의 EBP 레지스터 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="49a85-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="49a85-110">명령 포인터 또는 x86 enter 명령 포인터 (EIP) 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="49a85-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49a85-111">설명</span><span class="sxs-lookup"><span data-stu-id="49a85-111">Remarks</span></span>  
 <span data-ttu-id="49a85-112">일반적으로 스택 추적 함수 주소, 프레임 오프셋 및 스택 주소를 반환 해야, 하므로 필요에 따라 사용할 수는 `SimpleContext` 큰 대신 구조 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="49a85-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49a85-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49a85-113">Requirements</span></span>  
 <span data-ttu-id="49a85-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="49a85-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49a85-115">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="49a85-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="49a85-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49a85-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a85-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="49a85-117">See also</span></span>

- [<span data-ttu-id="49a85-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="49a85-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="49a85-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="49a85-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
