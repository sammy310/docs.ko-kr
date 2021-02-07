---
description: '자세히 알아보기: ICorDebugAssembly3:: EnumerateContainedAssemblies 메서드'
title: ICorDebugAssembly3::EnumerateContainedAssemblies 메서드
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 8933500713661ef785eb3ce5abc574e512580b6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754084"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="df232-103">ICorDebugAssembly3::EnumerateContainedAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="df232-103">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>

<span data-ttu-id="df232-104">이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df232-104">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df232-105">구문</span><span class="sxs-lookup"><span data-stu-id="df232-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df232-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df232-106">Parameters</span></span>  

 `ppAssemblies`  
 <span data-ttu-id="df232-107">[out] 열거자인 ICorDebugAssemblyEnum 인터페이스 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="df232-107">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df232-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="df232-108">Return Value</span></span>  

 <span data-ttu-id="df232-109">이 `S_OK` 개체가 컨테이너이면 `ICorDebugAssembly3`이고, 그러지 않으면 `S_FALSE`이며 열거형은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df232-109">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df232-110">설명</span><span class="sxs-lookup"><span data-stu-id="df232-110">Remarks</span></span>  

 <span data-ttu-id="df232-111">포함된 어셈블리를 열거하려면 기호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df232-111">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="df232-112">기호가 없으면 메서드는 `S_FALSE`를 반환하며 올바른 열거자가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df232-112">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df232-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df232-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df232-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df232-114">Requirements</span></span>  

 <span data-ttu-id="df232-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df232-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df232-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df232-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df232-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df232-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df232-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df232-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df232-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df232-119">See also</span></span>

- [<span data-ttu-id="df232-120">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df232-120">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="df232-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df232-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
