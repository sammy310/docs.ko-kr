---
title: ICorDebugCode 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca47eb5508907297a78dba1ab2b0a6d2b8ece0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750256"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="1b98d-102">ICorDebugCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b98d-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="1b98d-103">MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b98d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-104">Methods</span></span>  
  
|<span data-ttu-id="1b98d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-105">Method</span></span>|<span data-ttu-id="1b98d-106">설명</span><span class="sxs-lookup"><span data-stu-id="1b98d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b98d-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="1b98d-108">지정된 된 오프셋에서 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="1b98d-109">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="1b98d-110">코드 세그먼트의 상대 가상 주소 (RVA)을 가져옵니다이 `ICorDebugCode` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="1b98d-111">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="1b98d-112">디스어셈블리에 대 한 형식이 지정된 된 함수에 대 한 모든 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="1b98d-113">이 메서드는 더 이상 사용 되지 않습니다. 사용 하 여 [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="1b98d-114">GetEnCRemapSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="1b98d-115">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-115">Not implemented.</span></span>|  
|[<span data-ttu-id="1b98d-116">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="1b98d-117">와 연결 된 "ICorDebugFunction" 가져옵니다 `ICorDebugCode`합니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="1b98d-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="1b98d-119">MSIL 오프셋에서 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="1b98d-120">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="1b98d-121">크기 (바이트)가 표시 되는 이진 코드의 가져옵니다 `ICorDebugCode`합니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="1b98d-122">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="1b98d-123">코드의 버전을 식별 하는 1부터 번호를 가져옵니다이 `ICorDebugCode` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="1b98d-124">IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="1b98d-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="1b98d-125">나타내는 값을 가져옵니다 여부를이 `ICorDebugCode` MSIL에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b98d-126">설명</span><span class="sxs-lookup"><span data-stu-id="1b98d-126">Remarks</span></span>  
 <span data-ttu-id="1b98d-127">`ICorDebugCode` MSIL 또는 네이티브 코드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="1b98d-128">MSIL 코드를 나타내는 "ICorDebugFunction" 개체는 0 이나 1 있습니다 `ICorDebugCode` 연결 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="1b98d-129">네이티브 코드를 나타내는 "ICorDebugFunction" 개체 개수에 관계 없이 있습니다 `ICorDebugCode` 연결 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b98d-130">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b98d-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b98d-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b98d-131">Requirements</span></span>  
 <span data-ttu-id="1b98d-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1b98d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b98d-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b98d-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b98d-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b98d-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b98d-135">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b98d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b98d-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="1b98d-136">See also</span></span>

- [<span data-ttu-id="1b98d-137">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b98d-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="1b98d-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b98d-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
