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
ms.openlocfilehash: c81a5787eb06971e3d52aff5d1c1154a72564daf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790329"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="35a4f-102">StackTrace_SimpleContext 구조체</span><span class="sxs-lookup"><span data-stu-id="35a4f-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="35a4f-103">전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35a4f-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="35a4f-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="35a4f-105">Members</span><span class="sxs-lookup"><span data-stu-id="35a4f-105">Members</span></span>  
  
|<span data-ttu-id="35a4f-106">Member</span><span class="sxs-lookup"><span data-stu-id="35a4f-106">Member</span></span>|<span data-ttu-id="35a4f-107">설명</span><span class="sxs-lookup"><span data-stu-id="35a4f-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="35a4f-108">X86 플랫폼의 스택 포인터 또는 ESP (enter stack 포인터)입니다.</span><span class="sxs-lookup"><span data-stu-id="35a4f-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="35a4f-109">프레임 오프셋 또는 x86 플랫폼의 EBP 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="35a4f-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="35a4f-110">X86 플랫폼의 명령 포인터 또는 EIP (enter 명령 포인터)입니다.</span><span class="sxs-lookup"><span data-stu-id="35a4f-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a4f-111">주의</span><span class="sxs-lookup"><span data-stu-id="35a4f-111">Remarks</span></span>  
 <span data-ttu-id="35a4f-112">스택 추적 함수는 일반적으로 주소, 프레임 오프셋 및 스택 주소만 반환 해야 하기 때문에 필요에 따라 긴 `CONTEXT` 구조 대신 `SimpleContext` 구조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a4f-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a4f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35a4f-113">Requirements</span></span>  
 <span data-ttu-id="35a4f-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35a4f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a4f-115">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="35a4f-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="35a4f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a4f-117">참조</span><span class="sxs-lookup"><span data-stu-id="35a4f-117">See also</span></span>

- [<span data-ttu-id="35a4f-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="35a4f-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="35a4f-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="35a4f-119">Debugging</span></span>](index.md)
