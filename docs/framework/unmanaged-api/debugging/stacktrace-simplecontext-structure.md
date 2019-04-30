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
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986533"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="15ec2-102">StackTrace_SimpleContext 구조체</span><span class="sxs-lookup"><span data-stu-id="15ec2-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="15ec2-103">전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15ec2-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ec2-104">구문</span><span class="sxs-lookup"><span data-stu-id="15ec2-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="15ec2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="15ec2-105">Members</span></span>  
  
|<span data-ttu-id="15ec2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="15ec2-106">Member</span></span>|<span data-ttu-id="15ec2-107">설명</span><span class="sxs-lookup"><span data-stu-id="15ec2-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="15ec2-108">스택 포인터 또는 x86 enter 스택 포인터 (ESP) 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="15ec2-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="15ec2-109">프레임 오프셋 또는 x86의 EBP 레지스터 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="15ec2-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="15ec2-110">명령 포인터 또는 x86 enter 명령 포인터 (EIP) 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="15ec2-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15ec2-111">설명</span><span class="sxs-lookup"><span data-stu-id="15ec2-111">Remarks</span></span>  
 <span data-ttu-id="15ec2-112">일반적으로 스택 추적 함수 주소, 프레임 오프셋 및 스택 주소를 반환 해야, 하므로 필요에 따라 사용할 수는 `SimpleContext` 큰 대신 구조 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="15ec2-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ec2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15ec2-113">Requirements</span></span>  
 <span data-ttu-id="15ec2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15ec2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ec2-115">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="15ec2-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="15ec2-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ec2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ec2-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="15ec2-117">See also</span></span>

- [<span data-ttu-id="15ec2-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="15ec2-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="15ec2-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="15ec2-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
