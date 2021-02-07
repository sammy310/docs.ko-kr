---
description: '자세히 알아보기: ICorDebugTypeEnum:: Next 메서드'
title: ICorDebugTypeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: 9260f5f2d1a2d6943a705f7e7ef1ead3d2924cdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690589"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="18b3c-103">ICorDebugTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="18b3c-103">ICorDebugTypeEnum::Next Method</span></span>

<span data-ttu-id="18b3c-104">`celt`현재 위치에서 시작 하 여 열거형에서로 지정 된 "ICorDebugType" 인스턴스의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18b3c-104">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b3c-105">구문</span><span class="sxs-lookup"><span data-stu-id="18b3c-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18b3c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18b3c-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="18b3c-107">진행 `ICorDebugType` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="18b3c-107">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="18b3c-108">제한이 각각 개체를 가리키는 포인터의 배열입니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="18b3c-108">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="18b3c-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="18b3c-109">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="18b3c-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="18b3c-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18b3c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18b3c-111">Requirements</span></span>  

 <span data-ttu-id="18b3c-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18b3c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b3c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18b3c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18b3c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18b3c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18b3c-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18b3c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b3c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18b3c-116">See also</span></span>
