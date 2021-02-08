---
description: '자세히 알아보기: ICorDebugStaticFieldSymbol 인터페이스'
title: ICorDebugStaticFieldSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: 3aa9c98cef4cdc7edc519b06b6cf9b4b2192b4e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794678"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="8d80f-103">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d80f-103">ICorDebugStaticFieldSymbol Interface</span></span>

<span data-ttu-id="8d80f-104">정적 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-104">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d80f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8d80f-105">Methods</span></span>  
  
|<span data-ttu-id="8d80f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8d80f-106">Method</span></span>|<span data-ttu-id="8d80f-107">설명</span><span class="sxs-lookup"><span data-stu-id="8d80f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d80f-108">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="8d80f-108">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="8d80f-109">정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-109">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="8d80f-110">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="8d80f-110">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="8d80f-111">정적 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-111">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="8d80f-112">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="8d80f-112">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="8d80f-113">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-113">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d80f-114">설명</span><span class="sxs-lookup"><span data-stu-id="8d80f-114">Remarks</span></span>  

 <span data-ttu-id="8d80f-115">`ICorDebugStaticFieldSymbol` 인터페이스는 정적 필드에 대한 디버그 기호 정보를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-115">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d80f-116">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-116">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8d80f-117">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80f-117">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d80f-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d80f-118">Requirements</span></span>  

 <span data-ttu-id="8d80f-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d80f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d80f-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d80f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d80f-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d80f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d80f-122">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d80f-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d80f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d80f-123">See also</span></span>

- [<span data-ttu-id="8d80f-124">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d80f-124">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="8d80f-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d80f-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8d80f-126">디버깅</span><span class="sxs-lookup"><span data-stu-id="8d80f-126">Debugging</span></span>](index.md)
