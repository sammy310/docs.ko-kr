---
title: ICorDebugAssembly3::GetContainerAssembly 메서드
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cda67145a0e624f87e93cf02ebdb6bc77c34d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69987596"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="6c142-102">ICorDebugAssembly3::GetContainerAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="6c142-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="6c142-103">이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c142-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c142-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c142-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c142-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c142-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="6c142-106">컨테이너 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터 이거나, 메서드 호출이 실패할 경우 **null** 입니다.</span><span class="sxs-lookup"><span data-stu-id="6c142-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c142-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6c142-107">Return Value</span></span>  
 <span data-ttu-id="6c142-108">`S_OK`메서드 호출이 성공 하면이 고, 그렇지 않으면입니다. 그렇지 않으면, 및 `ppAssembly` 가 **null**입니다. `S_FALSE`</span><span class="sxs-lookup"><span data-stu-id="6c142-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c142-109">설명</span><span class="sxs-lookup"><span data-stu-id="6c142-109">Remarks</span></span>  
 <span data-ttu-id="6c142-110">이 어셈블리를 단일 컨테이너 어셈블리 내의 다른 어셈블리와 병합한 경우 이 메서드는 컨테이너 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c142-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="6c142-111">자세한 내용과 용어에 대 한 자세한 내용은 [ICorDebugProcess6:: EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c142-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c142-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c142-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c142-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c142-113">Requirements</span></span>  
 <span data-ttu-id="6c142-114">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c142-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c142-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c142-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c142-116">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c142-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c142-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c142-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c142-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c142-118">See also</span></span>

- [<span data-ttu-id="6c142-119">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c142-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="6c142-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c142-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
