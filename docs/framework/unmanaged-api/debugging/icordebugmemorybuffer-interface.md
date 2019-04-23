---
title: ICorDebugMemoryBuffer 인터페이스
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072911"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="ff952-102">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff952-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="ff952-103">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff952-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff952-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ff952-104">Methods</span></span>  
  
|<span data-ttu-id="ff952-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ff952-105">Method</span></span>|<span data-ttu-id="ff952-106">설명</span><span class="sxs-lookup"><span data-stu-id="ff952-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff952-107">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ff952-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="ff952-108">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff952-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="ff952-109">GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ff952-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="ff952-110">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff952-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff952-111">설명</span><span class="sxs-lookup"><span data-stu-id="ff952-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff952-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff952-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ff952-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ff952-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff952-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff952-114">Requirements</span></span>  
 <span data-ttu-id="ff952-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff952-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff952-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff952-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff952-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff952-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff952-118">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff952-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff952-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff952-119">See also</span></span>

- [<span data-ttu-id="ff952-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff952-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ff952-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="ff952-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
