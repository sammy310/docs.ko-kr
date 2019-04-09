---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 메서드
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080958"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="a87a8-102">ICorDebugAssembly3::EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="a87a8-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="a87a8-103">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a87a8-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a87a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="a87a8-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a87a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a87a8-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="a87a8-106">[out] 열거자는 ICorDebugAssemblyEnum 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a87a8-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a87a8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a87a8-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="a87a8-108">이 `ICorDebugAssembly3` 개체가 컨테이너가 고, 그렇지 않으면 `S_FALSE`, 열거형은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a87a8-108">if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a87a8-109">설명</span><span class="sxs-lookup"><span data-stu-id="a87a8-109">Remarks</span></span>  
 <span data-ttu-id="a87a8-110">포함된 어셈블리를 열거하려면 기호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a87a8-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="a87a8-111">기호가 없으면 메서드는 `S_FALSE`를 반환하며 올바른 열거자가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a87a8-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a87a8-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a87a8-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a87a8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a87a8-113">Requirements</span></span>  
 <span data-ttu-id="a87a8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a87a8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a87a8-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a87a8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a87a8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a87a8-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a87a8-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a87a8-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a87a8-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a87a8-118">See also</span></span>

- [<span data-ttu-id="a87a8-119">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a87a8-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="a87a8-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a87a8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
