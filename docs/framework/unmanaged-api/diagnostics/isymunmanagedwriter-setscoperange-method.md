---
title: ISymUnmanagedWriter::SetScopeRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c13eb7ca16cdb7c70f3fef0dd4efcb9362cd3d87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776588"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="f6f1e-102">ISymUnmanagedWriter::SetScopeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="f6f1e-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="f6f1e-103">지정된 어휘 범위에 대한 오프셋 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="f6f1e-104">범위는 현재 범위가 새 하 고 범위 스택에 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="f6f1e-105">범위 계층 구조를 형성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="f6f1e-106">형제 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f1e-107">구문</span><span class="sxs-lookup"><span data-stu-id="f6f1e-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6f1e-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6f1e-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="f6f1e-109">[in] 범위에 대 한 범위 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="f6f1e-110">[in] 메서드의 시작 부분에서 어휘 범위에서 첫 번째 명령의 바이트 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="f6f1e-111">[in] 메서드의 시작 부분에서 어휘 범위에서 마지막 명령의 바이트 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6f1e-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="f6f1e-112">Return Value</span></span>  
 <span data-ttu-id="f6f1e-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6f1e-114">설명</span><span class="sxs-lookup"><span data-stu-id="f6f1e-114">Remarks</span></span>  
 <span data-ttu-id="f6f1e-115">[Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) 사용 하 여 사용할 수 있는 불투명 한 범위 식별자를 반환 합니다 `ISymUnmanagedWriter::SetScopeRange` 범위를 정의 하의 시작과 끝 이후에 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="f6f1e-116">이 경우에 전달 된 오프셋 `ISymUnmanagedWriter::OpenScope` 하 고 [isymunmanagedwriter:: Closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="f6f1e-117">범위 식별자 현재 메서드에서만에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f1e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6f1e-118">Requirements</span></span>  
 <span data-ttu-id="f6f1e-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6f1e-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f1e-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="f6f1e-120">See also</span></span>

- [<span data-ttu-id="f6f1e-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6f1e-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
