---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 메서드
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 1e040453d5eb7a312f2e665974486492b99de16d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719686"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="6bde4-102">ICorDebugAssembly3::EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="6bde4-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>

<span data-ttu-id="6bde4-103">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bde4-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bde4-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bde4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bde4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6bde4-105">Parameters</span></span>  

 `ppAssemblies`  
 <span data-ttu-id="6bde4-106">[out] 열거자인 ICorDebugAssemblyEnum 인터페이스 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6bde4-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bde4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6bde4-107">Return Value</span></span>  

 <span data-ttu-id="6bde4-108">이 `S_OK` 개체가 컨테이너이면 `ICorDebugAssembly3`이고, 그러지 않으면 `S_FALSE`이며 열거형은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bde4-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bde4-109">설명</span><span class="sxs-lookup"><span data-stu-id="6bde4-109">Remarks</span></span>  

 <span data-ttu-id="6bde4-110">포함된 어셈블리를 열거하려면 기호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6bde4-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="6bde4-111">기호가 없으면 메서드는 `S_FALSE`를 반환하며 올바른 열거자가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bde4-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bde4-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bde4-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bde4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bde4-113">Requirements</span></span>  

 <span data-ttu-id="6bde4-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bde4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bde4-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bde4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bde4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bde4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bde4-117">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bde4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bde4-118">참조</span><span class="sxs-lookup"><span data-stu-id="6bde4-118">See also</span></span>

- [<span data-ttu-id="6bde4-119">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bde4-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="6bde4-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bde4-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
