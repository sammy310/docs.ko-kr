---
description: '자세히 알아보기: ICorDebugLoadedModule 인터페이스'
title: ICorDebugLoadedModule 인터페이스
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 6a1b466a9d2d7781fad7ac2bc8c24f0b2a5c23e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801230"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="38ad1-103">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38ad1-103">ICorDebugLoadedModule Interface</span></span>

<span data-ttu-id="38ad1-104">로드된 모듈에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-104">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38ad1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="38ad1-105">Methods</span></span>  
  
|<span data-ttu-id="38ad1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="38ad1-106">Method</span></span>|<span data-ttu-id="38ad1-107">설명</span><span class="sxs-lookup"><span data-stu-id="38ad1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38ad1-108">GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="38ad1-108">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="38ad1-109">로드된 모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-109">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="38ad1-110">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="38ad1-110">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="38ad1-111">로드된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-111">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="38ad1-112">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="38ad1-112">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="38ad1-113">로드된 모듈의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-113">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38ad1-114">설명</span><span class="sxs-lookup"><span data-stu-id="38ad1-114">Remarks</span></span>  

 <span data-ttu-id="38ad1-115">`ICorDebugLoadedModule` 인터페이스는 디버거에서 구현되며 CLR 디버깅 인터페이스가 디버거에서 로드된 모듈에 대한 정보를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-115">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38ad1-116">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-116">This interface is available with .NET Native only.</span></span> <span data-ttu-id="38ad1-117">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="38ad1-117">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ad1-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38ad1-118">Requirements</span></span>  

 <span data-ttu-id="38ad1-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38ad1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38ad1-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38ad1-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38ad1-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38ad1-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38ad1-122">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38ad1-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ad1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38ad1-123">See also</span></span>

- [<span data-ttu-id="38ad1-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38ad1-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="38ad1-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="38ad1-125">Debugging</span></span>](index.md)
