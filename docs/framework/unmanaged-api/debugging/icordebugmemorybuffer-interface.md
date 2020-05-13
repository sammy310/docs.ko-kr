---
title: ICorDebugMemoryBuffer 인터페이스
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 60f3b0c3230c524ca7d308d3cb80e50b0693715d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212336"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="b231d-102">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b231d-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="b231d-103">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b231d-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b231d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b231d-104">Methods</span></span>  
  
|<span data-ttu-id="b231d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b231d-105">Method</span></span>|<span data-ttu-id="b231d-106">설명</span><span class="sxs-lookup"><span data-stu-id="b231d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b231d-107">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b231d-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="b231d-108">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b231d-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="b231d-109">GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="b231d-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="b231d-110">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b231d-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b231d-111">설명</span><span class="sxs-lookup"><span data-stu-id="b231d-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b231d-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b231d-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b231d-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="b231d-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b231d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b231d-114">Requirements</span></span>  
 <span data-ttu-id="b231d-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b231d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b231d-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b231d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b231d-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b231d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b231d-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b231d-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b231d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b231d-119">See also</span></span>

- [<span data-ttu-id="b231d-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b231d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b231d-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="b231d-121">Debugging</span></span>](index.md)
