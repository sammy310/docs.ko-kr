---
title: ICorDebugAssemblyEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
ms.openlocfilehash: 86fa44b609b4b89cfaa28f0bfa7bbdce6217623f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122864"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="289b5-102">ICorDebugAssemblyEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="289b5-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="289b5-103">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="289b5-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="289b5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="289b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="289b5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="289b5-106">진행 검색할 어셈블리의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="289b5-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="289b5-107">제한이 각각 어셈블리를 나타내는 ICorDebugAssembly 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="289b5-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="289b5-108">제한이 실제로 반환 된 어셈블리 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="289b5-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="289b5-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="289b5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="289b5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="289b5-110">Requirements</span></span>  
 <span data-ttu-id="289b5-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="289b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="289b5-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="289b5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="289b5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="289b5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="289b5-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="289b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
