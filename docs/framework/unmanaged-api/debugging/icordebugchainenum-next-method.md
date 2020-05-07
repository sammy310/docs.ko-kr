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
ms.openlocfilehash: 2d075820df534e08bdf4c2b75d36f6a60f979662
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894088"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="89f19-102">ICorDebugChainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="89f19-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="89f19-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugChain 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89f19-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f19-104">구문</span><span class="sxs-lookup"><span data-stu-id="89f19-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89f19-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89f19-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="89f19-106">진행 검색할 `ICorDebugChain` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89f19-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="89f19-107">제한이 각각 체인을 나타내는 `ICorDebugChain` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="89f19-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="89f19-108">제한이 실제로 반환 된 `ICorDebugChain` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89f19-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="89f19-109">이 일 경우 `celt` 이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f19-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f19-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89f19-110">Requirements</span></span>  
 <span data-ttu-id="89f19-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89f19-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f19-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89f19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89f19-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89f19-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
