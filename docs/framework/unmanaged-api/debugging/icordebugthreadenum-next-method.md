---
title: ICorDebugThreadEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: c025afac1b53b23636a6160a475704011999d434
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379051"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="cdccd-102">ICorDebugThreadEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="cdccd-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="cdccd-103">현재 위치에서 시작 하 여 열거형에서 지정 된 ICorDebugThread 인스턴스의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cdccd-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdccd-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdccd-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdccd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdccd-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cdccd-106">진행 `ICorDebugThread`검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cdccd-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="cdccd-107">제한이 각각 스레드를 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="cdccd-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cdccd-108">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugThread` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cdccd-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="cdccd-109">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="cdccd-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdccd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdccd-110">Requirements</span></span>  
 <span data-ttu-id="cdccd-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdccd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdccd-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdccd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdccd-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdccd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdccd-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdccd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
