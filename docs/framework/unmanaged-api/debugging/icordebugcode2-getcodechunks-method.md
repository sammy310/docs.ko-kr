---
title: ICorDebugCode2::GetCodeChunks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1428fc245d4f6993050c2753321684afee488c0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750152"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="eedc4-102">ICorDebugCode2::GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="eedc4-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="eedc4-103">이 코드 개체를 구성 하는 코드의 청크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eedc4-104">구문</span><span class="sxs-lookup"><span data-stu-id="eedc4-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eedc4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eedc4-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="eedc4-106">[in] 크기는 `chunks` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="eedc4-107">[out] 반환 된 청크 수는 `chunks` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="eedc4-108">[out] 각각을 단일 코드 청크를 나타내는 "CodeChunkInfo" 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="eedc4-109">경우 변수의 `cbufSize` 가 0 이면이 매개 변수는 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eedc4-110">설명</span><span class="sxs-lookup"><span data-stu-id="eedc4-110">Remarks</span></span>  
 <span data-ttu-id="eedc4-111">코드 청크 겹치는 되지 됩니다 및 순서는 이러한는 연결 된 여 따를 [icordebugcode:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="eedc4-112">.NET Framework 버전 2.0의에서 Microsoft MSIL (intermediate language) 코드 개체를 구성 하는 단일 코드 청크 합니다.</span><span class="sxs-lookup"><span data-stu-id="eedc4-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eedc4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eedc4-113">Requirements</span></span>  
 <span data-ttu-id="eedc4-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eedc4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eedc4-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eedc4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eedc4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eedc4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eedc4-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eedc4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedc4-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="eedc4-118">See also</span></span>
