---
description: '자세히 알아보기: ICorDebugChainEnum:: Next 메서드'
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
ms.openlocfilehash: 5ab6665eb5af6d9f145f9aab67aeb75b4769e7e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711572"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="5777b-103">ICorDebugChainEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5777b-103">ICorDebugChainEnum::Next Method</span></span>

<span data-ttu-id="5777b-104">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugChain 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5777b-104">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5777b-105">구문</span><span class="sxs-lookup"><span data-stu-id="5777b-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5777b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5777b-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5777b-107">진행 `ICorDebugChain` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5777b-107">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="5777b-108">제한이 각각 체인을 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugChain` .</span><span class="sxs-lookup"><span data-stu-id="5777b-108">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5777b-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugChain` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5777b-109">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="5777b-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="5777b-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5777b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5777b-111">Requirements</span></span>  

 <span data-ttu-id="5777b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5777b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5777b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5777b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5777b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5777b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5777b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5777b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
