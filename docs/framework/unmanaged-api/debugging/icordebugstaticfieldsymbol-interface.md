---
title: ICorDebugStaticFieldSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103898"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="82786-102">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82786-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="82786-103">정적 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82786-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82786-104">메서드</span><span class="sxs-lookup"><span data-stu-id="82786-104">Methods</span></span>  
  
|<span data-ttu-id="82786-105">메서드</span><span class="sxs-lookup"><span data-stu-id="82786-105">Method</span></span>|<span data-ttu-id="82786-106">설명</span><span class="sxs-lookup"><span data-stu-id="82786-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82786-107">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="82786-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="82786-108">정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82786-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="82786-109">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="82786-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="82786-110">정적 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82786-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="82786-111">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="82786-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="82786-112">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82786-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82786-113">설명</span><span class="sxs-lookup"><span data-stu-id="82786-113">Remarks</span></span>  
 <span data-ttu-id="82786-114">`ICorDebugStaticFieldSymbol` 인터페이스는 정적 필드에 대한 디버그 기호 정보를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="82786-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82786-115">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82786-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="82786-116">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="82786-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82786-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82786-117">Requirements</span></span>  
 <span data-ttu-id="82786-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="82786-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82786-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82786-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82786-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82786-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82786-121">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82786-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82786-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="82786-122">See also</span></span>

- [<span data-ttu-id="82786-123">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82786-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="82786-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82786-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="82786-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="82786-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
