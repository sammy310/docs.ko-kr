---
title: ICorDebugMemoryBuffer 인터페이스
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 2765852309401d2aa30f91b506ba55156cd8a3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710744"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="ae8e4-102">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae8e4-102">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="ae8e4-103">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae8e4-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae8e4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ae8e4-104">Methods</span></span>  
  
|<span data-ttu-id="ae8e4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae8e4-105">Method</span></span>|<span data-ttu-id="ae8e4-106">설명</span><span class="sxs-lookup"><span data-stu-id="ae8e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae8e4-107">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ae8e4-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="ae8e4-108">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae8e4-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="ae8e4-109">GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ae8e4-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="ae8e4-110">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae8e4-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae8e4-111">설명</span><span class="sxs-lookup"><span data-stu-id="ae8e4-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae8e4-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8e4-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ae8e4-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8e4-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae8e4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae8e4-114">Requirements</span></span>  

 <span data-ttu-id="ae8e4-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae8e4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae8e4-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae8e4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae8e4-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae8e4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae8e4-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae8e4-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8e4-119">참조</span><span class="sxs-lookup"><span data-stu-id="ae8e4-119">See also</span></span>

- [<span data-ttu-id="ae8e4-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae8e4-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ae8e4-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="ae8e4-121">Debugging</span></span>](index.md)
