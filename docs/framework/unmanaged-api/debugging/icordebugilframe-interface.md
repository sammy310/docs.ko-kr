---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c60d7685de1e9a1d4f631ad1fba53b981829f58
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159804"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="75caf-102">ICorDebugILFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75caf-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="75caf-103">Microsoft MSIL (intermediate language) 코드의 스택 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="75caf-104">이 인터페이스는 ICorDebugFrame 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75caf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-105">Methods</span></span>  
  
|<span data-ttu-id="75caf-106">메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-106">Method</span></span>|<span data-ttu-id="75caf-107">설명</span><span class="sxs-lookup"><span data-stu-id="75caf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75caf-108">CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="75caf-109">지정된 된 오프셋된 위치에 명령 포인터를 설정할 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="75caf-110">EnumerateArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="75caf-111">이 프레임에서 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="75caf-112">EnumerateLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="75caf-113">이 프레임에서 로컬 변수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="75caf-114">GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="75caf-115">이 MSIL 스택 프레임에서 지정 된 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="75caf-116">GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="75caf-117">명령 포인터의 값 및 명령 포인터의 값을 가져온 방법에 대해 설명 하는 비트 조합 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="75caf-118">GetLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="75caf-119">이 MSIL 스택 프레임에서 지정 된 로컬 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="75caf-120">GetStackDepth 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="75caf-121">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-121">Not implemented.</span></span>|  
|[<span data-ttu-id="75caf-122">GetStackValue 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="75caf-123">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-123">Not implemented.</span></span>|  
|[<span data-ttu-id="75caf-124">SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="75caf-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="75caf-125">MSIL 코드에서 지정된 된 오프셋된 위치에 명령 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75caf-126">설명</span><span class="sxs-lookup"><span data-stu-id="75caf-126">Remarks</span></span>  
 <span data-ttu-id="75caf-127">`ICorDebugILFrame` 인터페이스는 특수 한 ICorDebugFrame 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="75caf-128">사용 되는 시간 (JIT) 또는 MSIL 코드 프레임에 대 한 컴파일된 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="75caf-129">둘 다 JIT 컴파일 프레임을 구현 합니다 `ICorDebugILFrame` 인터페이스 및 ICorDebugNativeFrame 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75caf-130">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75caf-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75caf-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75caf-131">Requirements</span></span>  
 <span data-ttu-id="75caf-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75caf-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75caf-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75caf-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75caf-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75caf-134">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="75caf-135">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="75caf-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75caf-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="75caf-136">See also</span></span>

- [<span data-ttu-id="75caf-137">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75caf-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
