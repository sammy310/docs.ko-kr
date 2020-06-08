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
ms.openlocfilehash: e2e911fb1d737ebb6b2106c89ac11335788ace4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501731"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="abf5f-102">ISymUnmanagedWriter::CloseScope 메서드</span><span class="sxs-lookup"><span data-stu-id="abf5f-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="abf5f-103">현재 어휘 범위를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="abf5f-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abf5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="abf5f-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="abf5f-106">진행 어휘 범위에서 마지막 명령의 끝에 있는 지점에서의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abf5f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="abf5f-107">Return Value</span></span>  
 <span data-ttu-id="abf5f-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abf5f-109">설명</span><span class="sxs-lookup"><span data-stu-id="abf5f-109">Remarks</span></span>  
 <span data-ttu-id="abf5f-110">범위가 닫히면 변수 내에서 더 이상 변수를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="abf5f-111">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) 는 나중에 범위의 시작 및 끝 오프셋을 정의 하는 [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) 와 함께 사용할 수 있는 불투명 범위 식별자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-111">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="abf5f-112">이 경우 `ISymUnmanagedWriter::OpenScope` 및 `ISymUnmanagedWriter::CloseScope`에 전달된 오프셋은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="abf5f-113">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="abf5f-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf5f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="abf5f-114">Requirements</span></span>  
 <span data-ttu-id="abf5f-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="abf5f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf5f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abf5f-116">See also</span></span>

- [<span data-ttu-id="abf5f-117">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="abf5f-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
