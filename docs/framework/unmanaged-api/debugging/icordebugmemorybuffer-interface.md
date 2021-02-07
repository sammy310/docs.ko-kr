---
description: '자세히 알아보기: ICorDebugMemoryBuffer 인터페이스'
title: ICorDebugMemoryBuffer 인터페이스
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 94eeb0f31c0e1c053fabbd556768fa65dda2d328
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754019"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="df57f-103">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df57f-103">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="df57f-104">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df57f-104">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df57f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="df57f-105">Methods</span></span>  
  
|<span data-ttu-id="df57f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="df57f-106">Method</span></span>|<span data-ttu-id="df57f-107">설명</span><span class="sxs-lookup"><span data-stu-id="df57f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df57f-108">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="df57f-108">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="df57f-109">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df57f-109">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="df57f-110">GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="df57f-110">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="df57f-111">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df57f-111">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df57f-112">설명</span><span class="sxs-lookup"><span data-stu-id="df57f-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df57f-113">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df57f-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="df57f-114">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="df57f-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df57f-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df57f-115">Requirements</span></span>  

 <span data-ttu-id="df57f-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df57f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df57f-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df57f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df57f-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df57f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df57f-119">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df57f-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df57f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df57f-120">See also</span></span>

- [<span data-ttu-id="df57f-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df57f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="df57f-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="df57f-122">Debugging</span></span>](index.md)
