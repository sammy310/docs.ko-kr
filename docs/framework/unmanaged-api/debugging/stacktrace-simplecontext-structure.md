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
ms.openlocfilehash: 45ae947cda5b4ddadfb10f5b2bdc78a95f031703
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420691"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="9a884-102">StackTrace_SimpleContext 구조체</span><span class="sxs-lookup"><span data-stu-id="9a884-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="9a884-103">전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a884-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a884-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a884-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="9a884-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9a884-105">Members</span></span>  
  
|<span data-ttu-id="9a884-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9a884-106">Member</span></span>|<span data-ttu-id="9a884-107">설명</span><span class="sxs-lookup"><span data-stu-id="9a884-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="9a884-108">X86 플랫폼의 스택 포인터 또는 ESP (enter stack 포인터)입니다.</span><span class="sxs-lookup"><span data-stu-id="9a884-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="9a884-109">프레임 오프셋 또는 x86 플랫폼의 EBP 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="9a884-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="9a884-110">X86 플랫폼의 명령 포인터 또는 EIP (enter 명령 포인터)입니다.</span><span class="sxs-lookup"><span data-stu-id="9a884-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a884-111">설명</span><span class="sxs-lookup"><span data-stu-id="9a884-111">Remarks</span></span>  
 <span data-ttu-id="9a884-112">스택 추적 함수는 일반적으로 주소, 프레임 오프셋 및 스택 주소만 반환 해야 하기 때문에 필요한 경우에는 `SimpleContext` 구조체 대신 구조를 사용할 수 있습니다 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="9a884-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a884-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a884-113">Requirements</span></span>  
 <span data-ttu-id="9a884-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a884-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a884-115">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="9a884-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="9a884-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a884-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a884-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a884-117">See also</span></span>

- [<span data-ttu-id="9a884-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="9a884-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="9a884-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="9a884-119">Debugging</span></span>](index.md)
