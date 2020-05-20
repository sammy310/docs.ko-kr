---
title: ISymUnmanagedWriter::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 4008b2a7d785781da5f35b3dc1e564487cb8e760
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609783"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="9103b-102">ISymUnmanagedWriter::OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="9103b-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="9103b-103">현재 메서드에서 새 어휘 범위를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="9103b-104">범위는 새로운 현재 범위가 되 고 범위 스택으로 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="9103b-105">범위는 계층 구조를 형성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="9103b-106">형제는 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9103b-107">구문</span><span class="sxs-lookup"><span data-stu-id="9103b-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9103b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9103b-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="9103b-109">진행 메서드 시작 부분부터 어휘 범위에 있는 첫 번째 명령의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9103b-110">제한이 범위 식별자를 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9103b-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="9103b-111">Return Value</span></span>  
 <span data-ttu-id="9103b-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9103b-113">설명</span><span class="sxs-lookup"><span data-stu-id="9103b-113">Remarks</span></span>  
 <span data-ttu-id="9103b-114">`ISymUnmanagedWriter::OpenScope`[ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) 과 함께 사용 하 여 나중에 범위의 시작 및 끝 오프셋을 정의 하는 데 사용할 수 있는 불투명 범위 식별자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="9103b-115">이 경우 `ISymUnmanagedWriter::OpenScope` 및 [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) 에 전달 된 오프셋은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="9103b-116">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="9103b-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9103b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9103b-117">Requirements</span></span>  
 <span data-ttu-id="9103b-118">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9103b-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9103b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9103b-119">See also</span></span>

- [<span data-ttu-id="9103b-120">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9103b-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
