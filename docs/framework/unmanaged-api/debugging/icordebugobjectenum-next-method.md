---
description: '자세히 알아보기: ICorDebugObjectEnum:: Next 메서드'
title: ICorDebugObjectEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: dd7d4240827e14962edf7573b59b273f65231bcf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729044"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="a6fb5-103">ICorDebugObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="a6fb5-103">ICorDebugObjectEnum::Next Method</span></span>

<span data-ttu-id="a6fb5-104">현재 위치에서 시작 하 여 열거형에서 지정 된 개체 수의 Rva (상대 가상 주소)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6fb5-104">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6fb5-105">구문</span><span class="sxs-lookup"><span data-stu-id="a6fb5-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6fb5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6fb5-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="a6fb5-107">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fb5-107">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="a6fb5-108">제한이 각각 CORDB_ADDRESS 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fb5-108">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a6fb5-109">제한이 실제로 반환 되는 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fb5-109">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="a6fb5-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="a6fb5-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6fb5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6fb5-111">Requirements</span></span>  

 <span data-ttu-id="a6fb5-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6fb5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6fb5-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6fb5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6fb5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6fb5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6fb5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6fb5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fb5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6fb5-116">See also</span></span>
