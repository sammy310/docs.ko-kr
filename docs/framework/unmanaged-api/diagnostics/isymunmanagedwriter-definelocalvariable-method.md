---
description: ISymUnmanagedWriter::D efineLocalVariable 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: cd817e3002c2a55fd8bbd7e565283752926f746b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762372"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="6c4bd-103">ISymUnmanagedWriter::DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="6c4bd-103">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>

<span data-ttu-id="6c4bd-104">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-104">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="6c4bd-105">이 메서드는 범위 전체의 여러 홈이 있는 동일한 이름의 변수에 대해 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-105">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="6c4bd-106">그러나이 경우 `startOffset` 및 `endOffset` 매개 변수의 값이 겹치지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-106">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c4bd-107">구문</span><span class="sxs-lookup"><span data-stu-id="6c4bd-107">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="6c4bd-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c4bd-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="6c4bd-109">진행 지역 변수 이름을 정의 하는에 대 한 포인터입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="6c4bd-109">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="6c4bd-110">진행 지역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-110">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="6c4bd-111">진행 `ULONG32` 버퍼의 크기 (바이트)를 나타내는입니다 `signature` .</span><span class="sxs-lookup"><span data-stu-id="6c4bd-111">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="6c4bd-112">진행 지역 변수 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-112">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="6c4bd-113">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-113">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="6c4bd-114">진행 매개 변수 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-114">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="6c4bd-115">진행 매개 변수 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-115">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="6c4bd-116">진행 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-116">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="6c4bd-117">진행 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-117">[in] The start offset for the variable.</span></span> <span data-ttu-id="6c4bd-118">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-118">This parameter is optional.</span></span> <span data-ttu-id="6c4bd-119">0 인 경우이 매개 변수는 무시 되 고 변수는 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-119">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6c4bd-120">0이 아닌 값인 경우 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-120">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="6c4bd-121">진행 변수의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-121">[in] The end offset for the variable.</span></span> <span data-ttu-id="6c4bd-122">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-122">This parameter is optional.</span></span> <span data-ttu-id="6c4bd-123">0 인 경우이 매개 변수는 무시 되 고 변수는 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-123">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6c4bd-124">0이 아닌 값인 경우 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-124">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c4bd-125">Return Value</span><span class="sxs-lookup"><span data-stu-id="6c4bd-125">Return Value</span></span>  

 <span data-ttu-id="6c4bd-126">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6c4bd-126">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c4bd-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c4bd-127">Requirements</span></span>  

 <span data-ttu-id="6c4bd-128">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6c4bd-128">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c4bd-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c4bd-129">See also</span></span>

- [<span data-ttu-id="6c4bd-130">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c4bd-130">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="6c4bd-131">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="6c4bd-131">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="6c4bd-132">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="6c4bd-132">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
