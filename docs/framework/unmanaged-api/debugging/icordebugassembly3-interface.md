---
title: ICorDebugAssembly3 인터페이스
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210310"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="be76c-102">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be76c-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="be76c-103">컨테이너 어셈블리 및 포함 된 어셈블리에 대 한 지원을 제공 하는 ICorDebugAssembly 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="be76c-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be76c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="be76c-104">Methods</span></span>  
  
|<span data-ttu-id="be76c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="be76c-105">Method</span></span>|<span data-ttu-id="be76c-106">설명</span><span class="sxs-lookup"><span data-stu-id="be76c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be76c-107">EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="be76c-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="be76c-108">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="be76c-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="be76c-109">GetContainerAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="be76c-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="be76c-110">이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be76c-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be76c-111">설명</span><span class="sxs-lookup"><span data-stu-id="be76c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be76c-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be76c-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="be76c-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="be76c-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be76c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be76c-114">Requirements</span></span>  
 <span data-ttu-id="be76c-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be76c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be76c-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be76c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be76c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be76c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be76c-118">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be76c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be76c-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="be76c-119">See also</span></span>

- [<span data-ttu-id="be76c-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be76c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="be76c-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="be76c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
