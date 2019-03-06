---
title: ICorDebugChainEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26df40297d080d1ccc9464f7b09e7731f135e270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489828"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="5c940-102">ICorDebugChainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5c940-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="5c940-103">ICorDebugChain 인스턴스 수가 지정 된 현재 위치부터 시작 하는 열거형에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c940-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c940-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c940-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c940-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c940-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5c940-106">[in] 수가 `ICorDebugChain` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c940-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="5c940-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugChain` 체인을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5c940-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5c940-108">[out] 개수에 대 한 포인터 `ICorDebugChain` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5c940-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="5c940-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5c940-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c940-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c940-110">Requirements</span></span>  
 <span data-ttu-id="5c940-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c940-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c940-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c940-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c940-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c940-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c940-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c940-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
