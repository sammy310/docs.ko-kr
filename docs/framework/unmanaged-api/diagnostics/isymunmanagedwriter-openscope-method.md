---
description: '자세히 알아보기: ISymUnmanagedWriter:: OpenScope 메서드'
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
ms.openlocfilehash: 1e47d97941b053fedcf08c7582e1083988a9fed4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762112"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="dd29d-103">ISymUnmanagedWriter::OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="dd29d-103">ISymUnmanagedWriter::OpenScope Method</span></span>

<span data-ttu-id="dd29d-104">현재 메서드에서 새 어휘 범위를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-104">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="dd29d-105">범위는 새로운 현재 범위가 되 고 범위 스택으로 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-105">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="dd29d-106">범위는 계층 구조를 형성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-106">Scopes must form a hierarchy.</span></span> <span data-ttu-id="dd29d-107">형제는 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-107">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd29d-108">구문</span><span class="sxs-lookup"><span data-stu-id="dd29d-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd29d-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd29d-109">Parameters</span></span>  

 `startOffset`  
 <span data-ttu-id="dd29d-110">진행 메서드 시작 부분부터 어휘 범위에 있는 첫 번째 명령의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-110">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dd29d-111">제한이 범위 식별자를 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-111">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd29d-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="dd29d-112">Return Value</span></span>  

 <span data-ttu-id="dd29d-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd29d-114">설명</span><span class="sxs-lookup"><span data-stu-id="dd29d-114">Remarks</span></span>  

 <span data-ttu-id="dd29d-115">`ISymUnmanagedWriter::OpenScope`[ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) 과 함께 사용 하 여 나중에 범위의 시작 및 끝 오프셋을 정의 하는 데 사용할 수 있는 불투명 범위 식별자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-115">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="dd29d-116">이 경우 `ISymUnmanagedWriter::OpenScope` 및 [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) 에 전달 된 오프셋은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="dd29d-117">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd29d-117">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd29d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd29d-118">Requirements</span></span>  

 <span data-ttu-id="dd29d-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="dd29d-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd29d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd29d-120">See also</span></span>

- [<span data-ttu-id="dd29d-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd29d-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
