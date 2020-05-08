---
title: ICorDebugAssembly3 인터페이스
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 67707092c80b0e07aa284336c426aba09ff991af
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894822"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="9602f-102">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9602f-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="9602f-103">컨테이너 어셈블리 및 해당 포함된 어셈블리에 대한 지원을 제공하기 위해 ICorDebugAssembly 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9602f-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9602f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9602f-104">Methods</span></span>  
  
|<span data-ttu-id="9602f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9602f-105">Method</span></span>|<span data-ttu-id="9602f-106">설명</span><span class="sxs-lookup"><span data-stu-id="9602f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9602f-107">EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="9602f-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="9602f-108">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9602f-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="9602f-109">GetContainerAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="9602f-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="9602f-110">이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9602f-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9602f-111">설명</span><span class="sxs-lookup"><span data-stu-id="9602f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9602f-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9602f-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9602f-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9602f-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9602f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9602f-114">Requirements</span></span>  
 <span data-ttu-id="9602f-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9602f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9602f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9602f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9602f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9602f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9602f-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9602f-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9602f-119">참조</span><span class="sxs-lookup"><span data-stu-id="9602f-119">See also</span></span>

- [<span data-ttu-id="9602f-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9602f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9602f-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="9602f-121">Debugging</span></span>](index.md)
