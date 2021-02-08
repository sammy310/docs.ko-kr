---
description: '자세히 알아보기: ICorDebugILFrame 인터페이스'
title: ICorDebugILFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 251fa18151ff286bee3e1bcf7707bf5f7145b4f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791363"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="85c4d-103">ICorDebugILFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85c4d-103">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="85c4d-104">MSIL (Microsoft 중간 언어) 코드의 스택 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-104">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="85c4d-105">이 인터페이스는 ICorDebugFrame 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-105">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85c4d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-106">Methods</span></span>  
  
|<span data-ttu-id="85c4d-107">메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-107">Method</span></span>|<span data-ttu-id="85c4d-108">설명</span><span class="sxs-lookup"><span data-stu-id="85c4d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85c4d-109">CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-109">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="85c4d-110">지정 된 오프셋 위치에 명령 포인터를 설정 하는 것이 안전한 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-110">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="85c4d-111">EnumerateArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-111">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="85c4d-112">이 프레임의 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-112">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="85c4d-113">EnumerateLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-113">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="85c4d-114">이 프레임의 지역 변수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-114">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="85c4d-115">GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-115">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="85c4d-116">이 MSIL 스택 프레임에서 지정 된 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-116">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="85c4d-117">GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-117">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="85c4d-118">명령 포인터의 값과 명령 포인터의 값을 가져오는 방법을 설명 하는 비트 조합 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-118">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="85c4d-119">GetLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-119">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="85c4d-120">이 MSIL 스택 프레임에서 지정 된 지역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-120">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="85c4d-121">GetStackDepth 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-121">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="85c4d-122">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-122">Not implemented.</span></span>|  
|[<span data-ttu-id="85c4d-123">GetStackValue 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-123">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="85c4d-124">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-124">Not implemented.</span></span>|  
|[<span data-ttu-id="85c4d-125">SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="85c4d-125">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="85c4d-126">MSIL 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-126">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85c4d-127">설명</span><span class="sxs-lookup"><span data-stu-id="85c4d-127">Remarks</span></span>  

 <span data-ttu-id="85c4d-128">`ICorDebugILFrame`인터페이스는 특수 한 ICorDebugFrame 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-128">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="85c4d-129">MSIL 코드 프레임 또는 JIT (just-in-time) 컴파일된 프레임에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-129">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="85c4d-130">JIT 컴파일된 프레임은 `ICorDebugILFrame` 인터페이스와 ICorDebugNativeFrame 인터페이스를 둘 다 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-130">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85c4d-131">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85c4d-131">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c4d-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85c4d-132">Requirements</span></span>  

 <span data-ttu-id="85c4d-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85c4d-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c4d-134">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85c4d-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85c4d-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85c4d-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85c4d-136">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c4d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c4d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85c4d-137">See also</span></span>

- [<span data-ttu-id="85c4d-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85c4d-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
