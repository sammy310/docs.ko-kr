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
ms.openlocfilehash: b57bb549278f62cdce6ed5deaaa62f154ec919b5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609367"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="f9dad-102">ISymUnmanagedWriter::SetScopeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="f9dad-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="f9dad-103">지정된 어휘 범위에 대한 오프셋 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="f9dad-104">범위는 새로운 현재 범위가 되 고 범위 스택으로 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="f9dad-105">범위는 계층 구조를 형성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="f9dad-106">형제는 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9dad-107">구문</span><span class="sxs-lookup"><span data-stu-id="f9dad-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9dad-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9dad-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="f9dad-109">진행 범위에 대 한 범위 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="f9dad-110">진행 메서드 시작 부분부터 어휘 범위에 있는 첫 번째 명령의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="f9dad-111">진행 메서드의 시작 부분에서 어휘 범위에 있는 마지막 명령의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9dad-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="f9dad-112">Return Value</span></span>  
 <span data-ttu-id="f9dad-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9dad-114">설명</span><span class="sxs-lookup"><span data-stu-id="f9dad-114">Remarks</span></span>  
 <span data-ttu-id="f9dad-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) 는와 함께 사용 하 여 `ISymUnmanagedWriter::SetScopeRange` 나중에 범위의 시작 및 끝 오프셋을 정의 하는 데 사용할 수 있는 불투명 범위 식별자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="f9dad-116">이 경우 `ISymUnmanagedWriter::OpenScope` 및 [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) 에 전달 된 오프셋은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="f9dad-117">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9dad-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9dad-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9dad-118">Requirements</span></span>  
 <span data-ttu-id="f9dad-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="f9dad-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9dad-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9dad-120">See also</span></span>

- [<span data-ttu-id="f9dad-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9dad-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
