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
ms.openlocfilehash: 14a72e4622aac09840e43f8bcdcf8a8c8d6e6892
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777909"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="8fe71-102">ICorDebugCode::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="8fe71-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="8fe71-103">지정 된 함수에 대 한 코드를 모두 가져오고 디스어셈블리에 맞게 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="8fe71-104">이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="8fe71-105">대신 [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe71-106">구문</span><span class="sxs-lookup"><span data-stu-id="8fe71-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fe71-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8fe71-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="8fe71-108">진행 함수 시작의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="8fe71-109">진행 함수 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="8fe71-110">진행 코드가 반환 될 `buffer` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="8fe71-111">제한이 코드가 반환 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="8fe71-112">제한이 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fe71-113">주의</span><span class="sxs-lookup"><span data-stu-id="8fe71-113">Remarks</span></span>  
 <span data-ttu-id="8fe71-114">함수의 코드가 여러 청크로 분할 된 경우에는 기본 오프셋의 오름차순으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="8fe71-115">명령 경계는 확인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe71-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe71-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fe71-116">Requirements</span></span>  
 <span data-ttu-id="8fe71-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fe71-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fe71-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fe71-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fe71-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fe71-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fe71-120">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="8fe71-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe71-121">참조</span><span class="sxs-lookup"><span data-stu-id="8fe71-121">See also</span></span>

- [<span data-ttu-id="8fe71-122">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="8fe71-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
