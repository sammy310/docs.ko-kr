---
title: ISymUnmanagedWriter::CloseScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 264b4487483ed5439a9809feefcdc1b20af402dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428083"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="815a8-102">ISymUnmanagedWriter::CloseScope 메서드</span><span class="sxs-lookup"><span data-stu-id="815a8-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="815a8-103">현재 어휘 범위를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="815a8-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="815a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="815a8-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="815a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="815a8-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="815a8-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span><span class="sxs-lookup"><span data-stu-id="815a8-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="815a8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="815a8-107">Return Value</span></span>  
 <span data-ttu-id="815a8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="815a8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="815a8-109">주의</span><span class="sxs-lookup"><span data-stu-id="815a8-109">Remarks</span></span>  
 <span data-ttu-id="815a8-110">Once a scope is closed, no more variables can be defined within it.</span><span class="sxs-lookup"><span data-stu-id="815a8-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="815a8-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span><span class="sxs-lookup"><span data-stu-id="815a8-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="815a8-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span><span class="sxs-lookup"><span data-stu-id="815a8-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="815a8-113">Scope identifiers are valid only in the current method.</span><span class="sxs-lookup"><span data-stu-id="815a8-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="815a8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="815a8-114">Requirements</span></span>  
 <span data-ttu-id="815a8-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="815a8-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815a8-116">참조</span><span class="sxs-lookup"><span data-stu-id="815a8-116">See also</span></span>

- [<span data-ttu-id="815a8-117">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="815a8-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
