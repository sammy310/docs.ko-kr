---
title: ICorDebugStaticFieldSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: 0891df1fc0528ff485605b2c4168fcff0adff990
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131701"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="3f395-102">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f395-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="3f395-103">정적 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f395-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3f395-104">Methods</span></span>  
  
|<span data-ttu-id="3f395-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3f395-105">Method</span></span>|<span data-ttu-id="3f395-106">설명</span><span class="sxs-lookup"><span data-stu-id="3f395-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f395-107">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="3f395-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="3f395-108">정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="3f395-109">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="3f395-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="3f395-110">정적 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="3f395-111">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="3f395-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="3f395-112">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f395-113">주의</span><span class="sxs-lookup"><span data-stu-id="3f395-113">Remarks</span></span>  
 <span data-ttu-id="3f395-114">`ICorDebugStaticFieldSymbol` 인터페이스는 정적 필드에 대한 디버그 기호 정보를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f395-115">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3f395-116">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="3f395-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f395-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f395-117">Requirements</span></span>  
 <span data-ttu-id="3f395-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f395-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f395-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f395-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f395-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f395-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f395-121">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f395-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f395-122">참조</span><span class="sxs-lookup"><span data-stu-id="3f395-122">See also</span></span>

- [<span data-ttu-id="3f395-123">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f395-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="3f395-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f395-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3f395-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="3f395-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
