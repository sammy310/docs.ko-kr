---
title: ICorDebugFrameEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 76b96dfd9d22c7e770671dcc01cb421430df729f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728188"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="7ad93-102">ICorDebugFrameEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="7ad93-102">ICorDebugFrameEnum::Next Method</span></span>

<span data-ttu-id="7ad93-103">현재 위치에서 시작 하 여 지정 된 수의 ICorDebugFrame 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ad93-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad93-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ad93-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ad93-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ad93-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="7ad93-106">진행 `ICorDebugFrame` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad93-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="7ad93-107">제한이 각각 개체를 가리키는 포인터의 배열입니다 `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="7ad93-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7ad93-108">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugFrame` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad93-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="7ad93-109">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="7ad93-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ad93-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ad93-110">Requirements</span></span>  

 <span data-ttu-id="7ad93-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ad93-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ad93-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ad93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ad93-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ad93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ad93-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
