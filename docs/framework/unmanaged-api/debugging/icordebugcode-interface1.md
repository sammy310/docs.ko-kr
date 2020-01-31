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
ms.openlocfilehash: 4b24b3dfe6a931866acd7eba966811071ff39ea5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788936"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="5eddc-102">ICorDebugCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eddc-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="5eddc-103">MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5eddc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-104">Methods</span></span>  
  
|<span data-ttu-id="5eddc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-105">Method</span></span>|<span data-ttu-id="5eddc-106">설명</span><span class="sxs-lookup"><span data-stu-id="5eddc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5eddc-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-107">CreateBreakpoint Method</span></span>](icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="5eddc-108">지정 된 오프셋에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="5eddc-109">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-109">GetAddress Method</span></span>](icordebugcode-getaddress-method.md)|<span data-ttu-id="5eddc-110">이 `ICorDebugCode`가 나타내는 코드 세그먼트의 RVA (상대 가상 주소)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="5eddc-111">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-111">GetCode Method</span></span>](icordebugcode-getcode-method.md)|<span data-ttu-id="5eddc-112">지정 된 함수에 대 한 코드를 모두 가져오고 디스어셈블리에 맞게 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="5eddc-113">이 메서드는 더 이상 사용 되지 않습니다. 대신 [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="5eddc-114">GetEnCRemapSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-114">GetEnCRemapSequencePoints Method</span></span>](icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="5eddc-115">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-115">Not implemented.</span></span>|  
|[<span data-ttu-id="5eddc-116">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-116">GetFunction Method</span></span>](icordebugcode-getfunction-method.md)|<span data-ttu-id="5eddc-117">이 `ICorDebugCode`와 연결 된 "ICorDebugFunction"를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="5eddc-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="5eddc-119">MSIL 오프셋과 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="5eddc-120">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-120">GetSize Method</span></span>](icordebugcode-getsize-method.md)|<span data-ttu-id="5eddc-121">이 `ICorDebugCode`표시 하는 이진 코드의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="5eddc-122">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-122">GetVersionNumber Method</span></span>](icordebugcode-getversionnumber-method.md)|<span data-ttu-id="5eddc-123">이 `ICorDebugCode`가 나타내는 코드의 버전을 식별 하는 1부터 사용 하는 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="5eddc-124">IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="5eddc-124">IsIL Method</span></span>](icordebugcode-isil-method.md)|<span data-ttu-id="5eddc-125">이 `ICorDebugCode` MSIL로 컴파일 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eddc-126">주의</span><span class="sxs-lookup"><span data-stu-id="5eddc-126">Remarks</span></span>  
 <span data-ttu-id="5eddc-127">`ICorDebugCode` MSIL 또는 네이티브 코드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="5eddc-128">MSIL 코드를 나타내는 "ICorDebugFunction" 개체에는 0 개 또는 1 개의 `ICorDebugCode` 개체가 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="5eddc-129">네이티브 코드를 나타내는 "ICorDebugFunction" 개체에는 연결 된 `ICorDebugCode` 개체가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5eddc-130">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eddc-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eddc-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5eddc-131">Requirements</span></span>  
 <span data-ttu-id="5eddc-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5eddc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eddc-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5eddc-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5eddc-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5eddc-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5eddc-135">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eddc-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eddc-136">참조</span><span class="sxs-lookup"><span data-stu-id="5eddc-136">See also</span></span>

- [<span data-ttu-id="5eddc-137">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eddc-137">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="5eddc-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eddc-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
