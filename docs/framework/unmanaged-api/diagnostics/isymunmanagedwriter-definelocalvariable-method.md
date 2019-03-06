---
title: ISymUnmanagedWriter::DefineLocalVariable 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1361d6e93fcf39a86951a78f1245e9158d6ed314
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483617"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="48c6a-102">ISymUnmanagedWriter::DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="48c6a-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="48c6a-103">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="48c6a-104">이 메서드는 다중 홈을 범위에 걸쳐 있는 동일한 이름의 변수에 대 한 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="48c6a-105">그러나이 경우,:의 값을 `startOffset` 및 `endOffset` 매개 변수는 겹치지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c6a-106">구문</span><span class="sxs-lookup"><span data-stu-id="48c6a-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48c6a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48c6a-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="48c6a-108">[in] 에 대 한 포인터를 `WCHAR` 로컬 변수 이름을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="48c6a-109">[in] 로컬 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="48c6a-110">[in] A `ULONG32` 의 크기 (바이트) 나타내는 `signature` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="48c6a-111">[in] 로컬 변수 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="48c6a-112">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="48c6a-113">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="48c6a-114">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="48c6a-115">[in] 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="48c6a-116">[in] 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="48c6a-117">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-117">This parameter is optional.</span></span> <span data-ttu-id="48c6a-118">0 인 경우이 매개 변수가 무시 되 고 변수가 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="48c6a-119">0이 아닌 값 이면 현재 범위의 오프셋 내에 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="48c6a-120">[in] 변수의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="48c6a-121">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-121">This parameter is optional.</span></span> <span data-ttu-id="48c6a-122">0 인 경우이 매개 변수가 무시 되 고 변수가 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="48c6a-123">0이 아닌 값 이면 현재 범위의 오프셋 내에 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48c6a-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="48c6a-124">Return Value</span></span>  
 <span data-ttu-id="48c6a-125">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="48c6a-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48c6a-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48c6a-126">Requirements</span></span>  
 <span data-ttu-id="48c6a-127">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48c6a-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c6a-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="48c6a-128">See also</span></span>
- [<span data-ttu-id="48c6a-129">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48c6a-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="48c6a-130">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="48c6a-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="48c6a-131">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="48c6a-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
