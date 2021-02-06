---
description: '자세히 알아보기: ICorDebugModuleEnum:: Next 메서드'
title: ICorDebugModuleEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: ed9558edad80c67e7bf3febb10c3adcd027e180a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650276"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="fcd4d-103">ICorDebugModuleEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="fcd4d-103">ICorDebugModuleEnum::Next Method</span></span>

<span data-ttu-id="fcd4d-104">`celt`현재 위치에서 시작 하 여 열거형에서로 지정 된 "ICorDebugModule" 인스턴스의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fcd4d-104">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd4d-105">구문</span><span class="sxs-lookup"><span data-stu-id="fcd4d-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd4d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fcd4d-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="fcd4d-107">진행 `ICorDebugModule` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fcd4d-107">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="fcd4d-108">제한이 각각 개체를 가리키는 포인터의 배열입니다 `ICorDebugModule` .</span><span class="sxs-lookup"><span data-stu-id="fcd4d-108">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fcd4d-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugModule` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fcd4d-109">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="fcd4d-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="fcd4d-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd4d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcd4d-111">Requirements</span></span>  

 <span data-ttu-id="fcd4d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcd4d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd4d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcd4d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcd4d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd4d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd4d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd4d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcd4d-116">See also</span></span>
