---
title: ISymUnmanagedWriter2::DefineLocalVariable2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d336b35e91abd1b7180c2b918edeba2e1eccdbde
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499591"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="006c5-102">ISymUnmanagedWriter2::DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="006c5-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="006c5-103">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="006c5-104">이 메서드는 다중 홈을 범위에 걸쳐 있는 동일한 이름의 변수에 대 한 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="006c5-105">그러나이 경우,:의 값을 `startOffset` 및 `endOffset` 매개 변수는 겹치지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006c5-106">구문</span><span class="sxs-lookup"><span data-stu-id="006c5-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="006c5-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="006c5-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="006c5-108">[in] 로컬 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="006c5-109">[in] 로컬 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="006c5-110">[in] 서명의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="006c5-111">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="006c5-112">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="006c5-113">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="006c5-114">[in] 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="006c5-115">[in] 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="006c5-116">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-116">This parameter is optional.</span></span> <span data-ttu-id="006c5-117">0 인 경우이 매개 변수가 무시 되 고 변수가 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="006c5-118">0이 아닌 값 이면 현재 범위의 오프셋 내에 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="006c5-119">[in] 변수의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="006c5-120">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-120">This parameter is optional.</span></span> <span data-ttu-id="006c5-121">0 인 경우이 매개 변수가 무시 되 고 변수가 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="006c5-122">0이 아닌 값 이면 현재 범위의 오프셋 내에 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="006c5-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="006c5-123">Return Value</span></span>  
 <span data-ttu-id="006c5-124">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="006c5-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="006c5-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="006c5-125">Requirements</span></span>  
 <span data-ttu-id="006c5-126">**헤더:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="006c5-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006c5-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="006c5-127">See also</span></span>
- [<span data-ttu-id="006c5-128">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="006c5-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="006c5-129">DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="006c5-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
