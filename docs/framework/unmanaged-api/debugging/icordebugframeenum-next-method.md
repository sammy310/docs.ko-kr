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
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124051"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="b3430-102">ICorDebugFrameEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b3430-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="b3430-103">현재 위치에서 시작 하 여 지정 된 수의 ICorDebugFrame 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3430-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3430-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3430-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3430-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3430-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b3430-106">진행 검색할 `ICorDebugFrame` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3430-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="b3430-107">제한이 각각 `ICorDebugFrame` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b3430-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b3430-108">제한이 실제로 반환 된 `ICorDebugFrame` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3430-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="b3430-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3430-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3430-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3430-110">Requirements</span></span>  
 <span data-ttu-id="b3430-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3430-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3430-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3430-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3430-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3430-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3430-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3430-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
