---
title: ICorDebugMemoryBuffer 인터페이스
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 9e43f9a2297eb56755c7a6bba73e994441cbfeaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127975"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="97415-102">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97415-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="97415-103">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="97415-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97415-104">메서드</span><span class="sxs-lookup"><span data-stu-id="97415-104">Methods</span></span>  
  
|<span data-ttu-id="97415-105">메서드</span><span class="sxs-lookup"><span data-stu-id="97415-105">Method</span></span>|<span data-ttu-id="97415-106">설명</span><span class="sxs-lookup"><span data-stu-id="97415-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97415-107">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="97415-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="97415-108">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97415-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="97415-109">GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="97415-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="97415-110">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97415-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97415-111">주의</span><span class="sxs-lookup"><span data-stu-id="97415-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97415-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97415-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="97415-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="97415-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97415-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97415-114">Requirements</span></span>  
 <span data-ttu-id="97415-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97415-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97415-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97415-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97415-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97415-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97415-118">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97415-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97415-119">참조</span><span class="sxs-lookup"><span data-stu-id="97415-119">See also</span></span>

- [<span data-ttu-id="97415-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97415-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="97415-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="97415-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
