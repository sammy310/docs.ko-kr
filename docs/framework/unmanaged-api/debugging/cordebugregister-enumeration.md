---
description: '다음에 대 한 자세한 정보: CorDebugRegister 열거형'
title: CorDebugRegister 열거형
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
ms.openlocfilehash: 7a5dc771a239a82448f898e2f518e920993ec35a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661878"
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="be9f4-103">CorDebugRegister 열거형</span><span class="sxs-lookup"><span data-stu-id="be9f4-103">CorDebugRegister Enumeration</span></span>

<span data-ttu-id="be9f4-104">지정한 프로세서 아키텍처에 연결된 레지스터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-104">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be9f4-105">구문</span><span class="sxs-lookup"><span data-stu-id="be9f4-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a><span data-ttu-id="be9f4-106">구성원</span><span class="sxs-lookup"><span data-stu-id="be9f4-106">Members</span></span>  
  
|<span data-ttu-id="be9f4-107">멤버</span><span class="sxs-lookup"><span data-stu-id="be9f4-107">Member</span></span>|<span data-ttu-id="be9f4-108">설명</span><span class="sxs-lookup"><span data-stu-id="be9f4-108">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="be9f4-109">프로세서의 명령 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-109">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="be9f4-110">프로세서의 스택 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-110">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="be9f4-111">프로세서의 프레임 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-111">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="be9f4-112">x86 프로세서의 명령 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-112">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="be9f4-113">x86 프로세서의 스택 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-113">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="be9f4-114">x86 프로세서의 기본 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-114">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="be9f4-115">x86 프로세서의 A 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-115">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="be9f4-116">x86 프로세서의 C 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-116">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="be9f4-117">x86 프로세서의 D 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-117">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="be9f4-118">x86 프로세서의 B 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-118">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="be9f4-119">x86 프로세서의 소스 인덱스 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-119">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="be9f4-120">x86 프로세서의 대상 인덱스 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-120">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="be9f4-121">x86 FP(부동 소수점) 프로세서의 스택 레지스터 0입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-121">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="be9f4-122">x86 FP 프로세서의 1번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-122">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="be9f4-123">x86 FP 프로세서의 2번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-123">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="be9f4-124">x86 FP 프로세서의 3번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-124">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="be9f4-125">x86 FP 프로세서의 4번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-125">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="be9f4-126">x86 FP 프로세서의 5번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-126">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="be9f4-127">x86 FP 프로세서의 6번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-127">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="be9f4-128">x86 FP 프로세서의 7번 스택 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-128">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="be9f4-129">AMD64 프로세서의 명령 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-129">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="be9f4-130">AMD64 프로세서의 스택 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-130">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="be9f4-131">AMD64 프로세서의 기본 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-131">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="be9f4-132">AMD64 프로세서의 A 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-132">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="be9f4-133">AMD64 프로세서의 C 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-133">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="be9f4-134">AMD64 프로세서의 D 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-134">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="be9f4-135">AMD64 프로세서의 B 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-135">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="be9f4-136">AMD64 프로세서의 소스 인덱스 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-136">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="be9f4-137">AMD64 프로세서의 대상 인덱스 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-137">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="be9f4-138">AMD64 프로세서의 8번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-138">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="be9f4-139">AMD64 프로세서의 9번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-139">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="be9f4-140">AMD64 프로세서의 10번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-140">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="be9f4-141">AMD64 프로세서의 11번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-141">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="be9f4-142">AMD64 프로세서의 12번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-142">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="be9f4-143">AMD64 프로세서의 13번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-143">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="be9f4-144">AMD64 프로세서의 14번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-144">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="be9f4-145">AMD64 프로세서의 15번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-145">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="be9f4-146">AMD64 프로세서의 0번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-146">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="be9f4-147">AMD64 프로세서의 1번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-147">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="be9f4-148">AMD64 프로세서의 2번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-148">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="be9f4-149">AMD64 프로세서의 3번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-149">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="be9f4-150">AMD64 프로세서의 4번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-150">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="be9f4-151">AMD64 프로세서의 5번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-151">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="be9f4-152">AMD64 프로세서의 6번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-152">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="be9f4-153">AMD64 프로세서의 7번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-153">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="be9f4-154">AMD64 프로세서의 8번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-154">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="be9f4-155">AMD64 프로세서의 9번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-155">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="be9f4-156">AMD64 프로세서의 10번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-156">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="be9f4-157">AMD64 프로세서의 11번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-157">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="be9f4-158">AMD64 프로세서의 12번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-158">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="be9f4-159">AMD64 프로세서의 13번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-159">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="be9f4-160">AMD64 프로세서의 14번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-160">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="be9f4-161">AMD64 프로세서의 15번 멀티미디어 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-161">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="be9f4-162">IA-64 프로세서의 스택 포인터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-162">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="be9f4-163">IA-64 프로세서의 0번 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-163">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="be9f4-164">IA-64 프로세서의 0번 FP 데이터 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-164">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="be9f4-165">ARM 프로세서의 프로그램 카운터 레지스터(R15)입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-165">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="be9f4-166">ARM 프로세서의 스택 포인터 레지스터(R13)입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-166">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="be9f4-167">ARM 프로세서의 데이터 레지스터 R0입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-167">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="be9f4-168">ARM 프로세서의 데이터 레지스터 R1입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-168">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="be9f4-169">ARM 프로세서의 데이터 레지스터 R2입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-169">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="be9f4-170">ARM 프로세서의 데이터 레지스터 R3입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-170">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="be9f4-171">ARM 프로세서의 레지스터 R4입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-171">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="be9f4-172">ARM 프로세서의 레지스터 R5입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-172">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="be9f4-173">ARM 프로세서의 레지스터 R6입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-173">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="be9f4-174">ARM 프로세서의 레지스터 R7(THUMB 프레임 포인터)입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-174">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="be9f4-175">ARM 프로세서의 레지스터 R8입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-175">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="be9f4-176">ARM 프로세서의 레지스터 R9입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-176">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="be9f4-177">ARM 프로세서의 레지스터 R10입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-177">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="be9f4-178">ARM 프로세서의 프레임 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-178">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="be9f4-179">ARM 프로세서의 레지스터 R12입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-179">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="be9f4-180">ARM 프로세서의 링크 레지스터(R14)입니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-180">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be9f4-181">설명</span><span class="sxs-lookup"><span data-stu-id="be9f4-181">Remarks</span></span>  

 <span data-ttu-id="be9f4-182">IA-64 프로세서에는 범용 데이터 레지스터와 부동 소수점 데이터 레지스터가 각각 128개씩 있지만 `REGISTER_IA64_R0` 및 `REGISTER_IA64_F0` 값만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-182">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="be9f4-183">나머지 값은 다음과 같이 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-183">The other values can be determined as follows:</span></span>  
  
- <span data-ttu-id="be9f4-184">`REGISTER_IA64_R0`~`REGISTER_IA64_R1` 값의 경우 레지스터 번호를 `REGISTER_IA64_R127`에 더합니다. 그러면 IA-64 프로세서에서 1번~127번 데이터 레지스터에 해당하는 값이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-184">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
- <span data-ttu-id="be9f4-185">`REGISTER_IA64_F0`~`REGISTER_IA64_F1` 값의 경우 레지스터 번호를 `REGISTER_IA64_F127`에 더합니다. 그러면 IA-64 프로세서에서 1번~127번 FP 데이터 레지스터에 해당하는 값이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-185">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="be9f4-186">예를 들어 IA-64 프로세서의 83번 데이터 레지스터를 지정해야 한다면 `REGISTER_IA64_R0` + 83을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be9f4-186">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be9f4-187">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be9f4-187">Requirements</span></span>  

 <span data-ttu-id="be9f4-188">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be9f4-188">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be9f4-189">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be9f4-189">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be9f4-190">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be9f4-190">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be9f4-191">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be9f4-191">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be9f4-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be9f4-192">See also</span></span>

- [<span data-ttu-id="be9f4-193">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="be9f4-193">Debugging Enumerations</span></span>](debugging-enumerations.md)
