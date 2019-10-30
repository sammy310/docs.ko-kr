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
ms.openlocfilehash: 3c11a0547ad5acc5613324d7e9d7439d44549dbc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125807"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="07931-102">ICorDebugChainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="07931-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="07931-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugChain 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07931-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07931-104">구문</span><span class="sxs-lookup"><span data-stu-id="07931-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07931-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07931-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="07931-106">진행 검색할 `ICorDebugChain` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="07931-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="07931-107">제한이 각각 체인을 나타내는 `ICorDebugChain` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="07931-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="07931-108">제한이 실제로 반환 된 `ICorDebugChain` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07931-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="07931-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07931-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07931-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07931-110">Requirements</span></span>  
 <span data-ttu-id="07931-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07931-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07931-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07931-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07931-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07931-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07931-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07931-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
