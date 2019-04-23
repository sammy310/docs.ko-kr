---
title: ICorDebugCode::GetCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f396881ef16f63eaf198aec168e5e94ed887698b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228538"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="e54a8-102">ICorDebugCode::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="e54a8-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="e54a8-103">디스어셈블리에 대 한 형식이 지정된 된 함수에 대 한 모든 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="e54a8-104">이 메서드는.NET Framework 버전 2.0에서에서 더 이상 사용 되지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e54a8-105">사용 하 여 [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54a8-106">구문</span><span class="sxs-lookup"><span data-stu-id="e54a8-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e54a8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e54a8-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="e54a8-108">[in] 오프셋은 함수의 시작 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="e54a8-109">[in] 함수 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="e54a8-110">[in] 크기는 `buffer` 에 코드가 반환 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e54a8-111">[out] 코드가 반환 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="e54a8-112">[out] 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e54a8-113">설명</span><span class="sxs-lookup"><span data-stu-id="e54a8-113">Remarks</span></span>  
 <span data-ttu-id="e54a8-114">함수 코드에 여러 개의 청크로 나뉘어, 네이티브 오프셋을 증가 하는 순서에 연결 되며 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="e54a8-115">명령 경계 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e54a8-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54a8-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e54a8-116">Requirements</span></span>  
 <span data-ttu-id="e54a8-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e54a8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e54a8-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e54a8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e54a8-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e54a8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e54a8-120">**.NET framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e54a8-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54a8-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="e54a8-121">See also</span></span>

- [<span data-ttu-id="e54a8-122">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="e54a8-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
