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
ms.openlocfilehash: f6a741df3ea57b5e9b4fa8bc5d304bfedd1d6c15
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428013"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="6addd-102">ISymUnmanagedWriter::DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="6addd-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="6addd-103">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="6addd-104">이 메서드는 범위 전체의 여러 홈이 있는 동일한 이름의 변수에 대해 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="6addd-105">그러나이 경우 `startOffset` 및 `endOffset` 매개 변수의 값이 겹치지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6addd-106">구문</span><span class="sxs-lookup"><span data-stu-id="6addd-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6addd-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6addd-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6addd-108">진행 지역 변수 이름을 정의 하는 `WCHAR`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="6addd-109">진행 지역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="6addd-110">진행 `signature` 버퍼의 크기 (바이트)를 나타내는 `ULONG32`입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="6addd-111">진행 지역 변수 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="6addd-112">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="6addd-113">진행 매개 변수 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="6addd-114">진행 매개 변수 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="6addd-115">진행 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="6addd-116">진행 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="6addd-117">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-117">This parameter is optional.</span></span> <span data-ttu-id="6addd-118">0 인 경우이 매개 변수는 무시 되 고 변수는 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6addd-119">0이 아닌 값인 경우 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="6addd-120">진행 변수의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="6addd-121">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-121">This parameter is optional.</span></span> <span data-ttu-id="6addd-122">0 인 경우이 매개 변수는 무시 되 고 변수는 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6addd-123">0이 아닌 값인 경우 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6addd-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="6addd-124">Return Value</span></span>  
 <span data-ttu-id="6addd-125">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6addd-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6addd-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6addd-126">Requirements</span></span>  
 <span data-ttu-id="6addd-127">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6addd-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6addd-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="6addd-128">See also</span></span>

- [<span data-ttu-id="6addd-129">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6addd-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="6addd-130">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="6addd-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="6addd-131">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="6addd-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
