---
description: '자세히 알아보기: ICorDebugAssembly3 인터페이스'
title: ICorDebugAssembly3 인터페이스
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 3a8cabf41dffa75d82c2b6fde53dff2ede4838e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791506"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="01bad-103">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01bad-103">ICorDebugAssembly3 Interface</span></span>

<span data-ttu-id="01bad-104">컨테이너 어셈블리 및 해당 포함된 어셈블리에 대한 지원을 제공하기 위해 ICorDebugAssembly 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="01bad-104">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01bad-105">메서드</span><span class="sxs-lookup"><span data-stu-id="01bad-105">Methods</span></span>  
  
|<span data-ttu-id="01bad-106">메서드</span><span class="sxs-lookup"><span data-stu-id="01bad-106">Method</span></span>|<span data-ttu-id="01bad-107">설명</span><span class="sxs-lookup"><span data-stu-id="01bad-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01bad-108">EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="01bad-108">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="01bad-109">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01bad-109">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="01bad-110">GetContainerAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="01bad-110">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="01bad-111">이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01bad-111">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01bad-112">설명</span><span class="sxs-lookup"><span data-stu-id="01bad-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01bad-113">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01bad-113">The interface is available with .NET Native only.</span></span> <span data-ttu-id="01bad-114">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="01bad-114">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01bad-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01bad-115">Requirements</span></span>  

 <span data-ttu-id="01bad-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01bad-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01bad-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01bad-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01bad-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01bad-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01bad-119">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01bad-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bad-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01bad-120">See also</span></span>

- [<span data-ttu-id="01bad-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01bad-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="01bad-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="01bad-122">Debugging</span></span>](index.md)
