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
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178993"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="bb5aa-102">ICorDebugCode::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="bb5aa-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="bb5aa-103">디스어셈블리에 대한 서식이 지정된 함수에 대한 모든 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="bb5aa-104">이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="bb5aa-105">대신 [ICorDebugCode2::GetCodeChunks를](icordebugcode2-getcodechunks-method.md) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb5aa-106">구문</span><span class="sxs-lookup"><span data-stu-id="bb5aa-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bb5aa-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb5aa-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="bb5aa-108">【인】 함수 시작 부분의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="bb5aa-109">【인】 함수 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="bb5aa-110">【인】 코드가 반환될 `buffer` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bb5aa-111">【아웃】 코드가 반환되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="bb5aa-112">【아웃】 반환된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb5aa-113">설명</span><span class="sxs-lookup"><span data-stu-id="bb5aa-113">Remarks</span></span>  
 <span data-ttu-id="bb5aa-114">함수의 코드가 여러 청크로 분할된 경우 네이티브 오프셋을 늘리는 순서로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="bb5aa-115">명령 경계는 선택되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb5aa-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb5aa-116">Requirements</span></span>  
 <span data-ttu-id="bb5aa-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb5aa-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb5aa-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb5aa-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb5aa-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb5aa-120">**.NET 프레임워크 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="bb5aa-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5aa-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb5aa-121">See also</span></span>

- [<span data-ttu-id="bb5aa-122">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="bb5aa-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
