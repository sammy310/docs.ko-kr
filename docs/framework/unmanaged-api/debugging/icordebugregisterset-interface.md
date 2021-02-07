---
description: '자세히 알아보기: ICorDebugRegisterSet 인터페이스'
title: ICorDebugRegisterSet 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 7d888e9e395e9f5fa88c6a6d96b2b8e3171ef4ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690784"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="acc5b-103">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc5b-103">ICorDebugRegisterSet Interface</span></span>

<span data-ttu-id="acc5b-104">현재 코드를 실행 중인 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-104">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acc5b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-105">Methods</span></span>  
  
|<span data-ttu-id="acc5b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-106">Method</span></span>|<span data-ttu-id="acc5b-107">설명</span><span class="sxs-lookup"><span data-stu-id="acc5b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acc5b-108">GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-108">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="acc5b-109">비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-109">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="acc5b-110">GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-110">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="acc5b-111">현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다 `ICorDebugRegisterSet` .</span><span class="sxs-lookup"><span data-stu-id="acc5b-111">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="acc5b-112">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-112">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="acc5b-113">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-113">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="acc5b-114">SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-114">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="acc5b-115">.NET Framework 버전 2.0에 대해 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-115">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="acc5b-116">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="acc5b-116">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="acc5b-117">.NET Framework 2.0에 대해 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-117">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acc5b-118">설명</span><span class="sxs-lookup"><span data-stu-id="acc5b-118">Remarks</span></span>  

 <span data-ttu-id="acc5b-119">`ICorDebugRegisterSet`인터페이스는 32 비트 레지스터만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-119">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="acc5b-120">추가 레지스터가 필요한 IA-64와 같은 플랫폼에서 [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-120">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="acc5b-121">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acc5b-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc5b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acc5b-122">Requirements</span></span>  

 <span data-ttu-id="acc5b-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acc5b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc5b-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acc5b-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acc5b-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acc5b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acc5b-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc5b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc5b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acc5b-127">See also</span></span>

- [<span data-ttu-id="acc5b-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc5b-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="acc5b-129">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc5b-129">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
