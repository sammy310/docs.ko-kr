---
description: '자세히 알아보기: ICorDebugDataTarget2 인터페이스'
title: ICorDebugDataTarget2 인터페이스
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 13a83ee99f0158f32f466f9ae29af3d917248f95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710467"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="df2ba-103">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df2ba-103">ICorDebugDataTarget2 Interface</span></span>

<span data-ttu-id="df2ba-104">[ICorDebugDataTarget](icordebugdatatarget-interface.md)인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-104">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df2ba-105">메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-105">Methods</span></span>  
  
|<span data-ttu-id="df2ba-106">메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-106">Method</span></span>|<span data-ttu-id="df2ba-107">설명</span><span class="sxs-lookup"><span data-stu-id="df2ba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df2ba-108">CreateVirtualUnwinder 메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-108">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="df2ba-109">초기 컨텍스트(반드시 스레드의 리프일 필요는 없음)에서 해제를 시작하는 새 스택 해제기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-109">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="df2ba-110">EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-110">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="df2ba-111">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-111">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="df2ba-112">GetImageFromPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-112">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="df2ba-113">모듈 기본 주소와 크기를 해당 모듈의 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-113">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="df2ba-114">GetImageLocation 메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-114">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="df2ba-115">모듈의 경로를 모듈의 기준 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-115">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="df2ba-116">GetSymbolProviderForImage 메서드</span><span class="sxs-lookup"><span data-stu-id="df2ba-116">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="df2ba-117">모듈의 시스템 공급자를 해당 모듈의 기본 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-117">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df2ba-118">설명</span><span class="sxs-lookup"><span data-stu-id="df2ba-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df2ba-119">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-119">This interface is available with .NET Native only.</span></span> <span data-ttu-id="df2ba-120">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="df2ba-120">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df2ba-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df2ba-121">Requirements</span></span>  

 <span data-ttu-id="df2ba-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df2ba-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2ba-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df2ba-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df2ba-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df2ba-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df2ba-125">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2ba-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2ba-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df2ba-126">See also</span></span>

- [<span data-ttu-id="df2ba-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df2ba-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="df2ba-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="df2ba-128">Debugging</span></span>](index.md)
