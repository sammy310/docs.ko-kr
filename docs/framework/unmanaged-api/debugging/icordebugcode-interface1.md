---
description: '자세히 알아보기: ICorDebugCode 인터페이스'
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
ms.openlocfilehash: ce67c48501783bbe00152f0ba2c224e6e7dde6d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711156"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="af4f2-103">ICorDebugCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af4f2-103">ICorDebugCode Interface</span></span>

<span data-ttu-id="af4f2-104">MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-104">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af4f2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-105">Methods</span></span>  
  
|<span data-ttu-id="af4f2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-106">Method</span></span>|<span data-ttu-id="af4f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="af4f2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af4f2-108">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-108">CreateBreakpoint Method</span></span>](icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="af4f2-109">지정 된 오프셋에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-109">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="af4f2-110">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-110">GetAddress Method</span></span>](icordebugcode-getaddress-method.md)|<span data-ttu-id="af4f2-111">이가 나타내는 코드 세그먼트의 RVA (상대 가상 주소)를 가져옵니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-111">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="af4f2-112">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-112">GetCode Method</span></span>](icordebugcode-getcode-method.md)|<span data-ttu-id="af4f2-113">지정 된 함수에 대 한 코드를 모두 가져오고 디스어셈블리에 맞게 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-113">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="af4f2-114">이 메서드는 더 이상 사용 되지 않습니다. 대신 [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-114">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="af4f2-115">GetEnCRemapSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-115">GetEnCRemapSequencePoints Method</span></span>](icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="af4f2-116">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-116">Not implemented.</span></span>|  
|[<span data-ttu-id="af4f2-117">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-117">GetFunction Method</span></span>](icordebugcode-getfunction-method.md)|<span data-ttu-id="af4f2-118">이와 연결 된 "ICorDebugFunction"를 가져옵니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-118">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="af4f2-119">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-119">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="af4f2-120">MSIL 오프셋과 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-120">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="af4f2-121">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-121">GetSize Method</span></span>](icordebugcode-getsize-method.md)|<span data-ttu-id="af4f2-122">이가 나타내는 이진 코드의 크기 (바이트)를 가져옵니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-122">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="af4f2-123">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-123">GetVersionNumber Method</span></span>](icordebugcode-getversionnumber-method.md)|<span data-ttu-id="af4f2-124">이가 나타내는 코드의 버전을 식별 하는 1부터 사용 하는 번호를 가져옵니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-124">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="af4f2-125">IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="af4f2-125">IsIL Method</span></span>](icordebugcode-isil-method.md)|<span data-ttu-id="af4f2-126">이이 MSIL로 컴파일 되었는지 여부를 나타내는 값을 가져옵니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-126">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af4f2-127">설명</span><span class="sxs-lookup"><span data-stu-id="af4f2-127">Remarks</span></span>  

 <span data-ttu-id="af4f2-128">`ICorDebugCode` MSIL 또는 네이티브 코드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-128">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="af4f2-129">MSIL 코드를 나타내는 "ICorDebugFunction" 개체에는 0 개 또는 하나의 개체가 연결 될 수 있습니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-129">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="af4f2-130">네이티브 코드를 나타내는 "ICorDebugFunction" 개체에는 연결 된 개체가 여러 개 있을 수 있습니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="af4f2-130">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af4f2-131">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af4f2-131">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af4f2-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af4f2-132">Requirements</span></span>  

 <span data-ttu-id="af4f2-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af4f2-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af4f2-134">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af4f2-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af4f2-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af4f2-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af4f2-136">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af4f2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4f2-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af4f2-137">See also</span></span>

- [<span data-ttu-id="af4f2-138">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af4f2-138">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="af4f2-139">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af4f2-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
