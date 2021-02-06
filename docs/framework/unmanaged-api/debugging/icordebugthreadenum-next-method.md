---
description: '자세히 알아보기: ICorDebugThreadEnum:: Next 메서드'
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
ms.openlocfilehash: 2cfb651d65eaf0f5797444ea1bec587cebdde2f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658427"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="fc451-103">ICorDebugThreadEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="fc451-103">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="fc451-104">현재 위치에서 시작 하 여 열거형에서 지정 된 ICorDebugThread 인스턴스의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc451-104">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc451-105">구문</span><span class="sxs-lookup"><span data-stu-id="fc451-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc451-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc451-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="fc451-107">진행 `ICorDebugThread` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fc451-107">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="fc451-108">제한이 각각 스레드를 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="fc451-108">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fc451-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugThread` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fc451-109">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="fc451-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="fc451-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc451-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc451-111">Requirements</span></span>  

 <span data-ttu-id="fc451-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc451-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc451-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc451-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc451-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc451-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc451-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc451-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
