---
title: ICorDebugProcessEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: d00a5f71ac7e47d78deebca0e46350e465964c72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210100"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="ad304-102">ICorDebugProcessEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="ad304-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="ad304-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugProcess 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad304-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad304-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad304-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad304-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad304-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ad304-106">진행 `ICorDebugProcess`검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ad304-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="ad304-107">제한이 각각 프로세스를 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugProcess` .</span><span class="sxs-lookup"><span data-stu-id="ad304-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ad304-108">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugProcess` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ad304-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="ad304-109">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="ad304-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad304-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad304-110">Requirements</span></span>  
 <span data-ttu-id="ad304-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad304-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad304-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad304-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad304-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad304-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad304-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad304-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
