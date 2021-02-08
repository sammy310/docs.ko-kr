---
description: '자세히 알아보기: ICorDebugAssemblyEnum:: Next 메서드'
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
ms.openlocfilehash: feb77f22ec59fcc0e1b3f5590b7aee4efba13d01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772226"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="04b55-103">ICorDebugAssemblyEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="04b55-103">ICorDebugAssemblyEnum::Next Method</span></span>

<span data-ttu-id="04b55-104">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04b55-104">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04b55-105">구문</span><span class="sxs-lookup"><span data-stu-id="04b55-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04b55-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04b55-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="04b55-107">진행 검색할 어셈블리의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04b55-107">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="04b55-108">제한이 각각 어셈블리를 나타내는 ICorDebugAssembly 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="04b55-108">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="04b55-109">제한이 실제로 반환 된 어셈블리 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04b55-109">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="04b55-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="04b55-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04b55-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04b55-111">Requirements</span></span>  

 <span data-ttu-id="04b55-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04b55-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04b55-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04b55-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04b55-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04b55-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04b55-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04b55-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
