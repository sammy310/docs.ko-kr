---
description: '자세히 알아보기: ICorDebugProcessEnum:: Next 메서드'
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
ms.openlocfilehash: e32ff2e67f3f8a0242e0a0f93ed00229fee9cc26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691174"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="c692b-103">ICorDebugProcessEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="c692b-103">ICorDebugProcessEnum::Next Method</span></span>

<span data-ttu-id="c692b-104">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugProcess 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c692b-104">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c692b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c692b-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c692b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c692b-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="c692b-107">진행 `ICorDebugProcess` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c692b-107">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="c692b-108">제한이 각각 프로세스를 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugProcess` .</span><span class="sxs-lookup"><span data-stu-id="c692b-108">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c692b-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugProcess` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c692b-109">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="c692b-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="c692b-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c692b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c692b-111">Requirements</span></span>  

 <span data-ttu-id="c692b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c692b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c692b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c692b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c692b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c692b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c692b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c692b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
