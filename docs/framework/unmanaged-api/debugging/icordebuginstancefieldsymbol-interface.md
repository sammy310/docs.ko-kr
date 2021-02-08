---
description: '자세히 알아보기: ICorDebugInstanceFieldSymbol 인터페이스'
title: ICorDebugInstanceFieldSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: aa47c858ec5b4b0d04b851357fe81c0fc9b2e30a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791134"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="2a3c5-103">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3c5-103">ICorDebugInstanceFieldSymbol Interface</span></span>

<span data-ttu-id="2a3c5-104">인스턴스 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-104">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a3c5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2a3c5-105">Methods</span></span>  
  
|<span data-ttu-id="2a3c5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2a3c5-106">Method</span></span>|<span data-ttu-id="2a3c5-107">설명</span><span class="sxs-lookup"><span data-stu-id="2a3c5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a3c5-108">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="2a3c5-108">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="2a3c5-109">인스턴스 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-109">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="2a3c5-110">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2a3c5-110">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="2a3c5-111">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-111">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="2a3c5-112">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2a3c5-112">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="2a3c5-113">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-113">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a3c5-114">설명</span><span class="sxs-lookup"><span data-stu-id="2a3c5-114">Remarks</span></span>  

 <span data-ttu-id="2a3c5-115">`ICorDebugInstanceFieldSymbol` 인터페이스는 인스턴스 필드에 대한 디버그 기호 정보를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-115">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a3c5-116">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-116">This interface is available with .NET Native only.</span></span> <span data-ttu-id="2a3c5-117">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-117">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3c5-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a3c5-118">Requirements</span></span>  

 <span data-ttu-id="2a3c5-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a3c5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3c5-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a3c5-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a3c5-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a3c5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a3c5-122">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3c5-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3c5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a3c5-123">See also</span></span>

- [<span data-ttu-id="2a3c5-124">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3c5-124">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="2a3c5-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3c5-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2a3c5-126">디버깅</span><span class="sxs-lookup"><span data-stu-id="2a3c5-126">Debugging</span></span>](index.md)
