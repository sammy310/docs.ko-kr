---
description: '자세히 알아보기: ISymUnmanagedWriter:: SetScopeRange 메서드'
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
ms.openlocfilehash: 43cfbeaa0d366b9f2d25068cfa7b91a0fea8ac59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762060"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="e5c63-103">ISymUnmanagedWriter::SetScopeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="e5c63-103">ISymUnmanagedWriter::SetScopeRange Method</span></span>

<span data-ttu-id="e5c63-104">지정된 어휘 범위에 대한 오프셋 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-104">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="e5c63-105">범위는 새로운 현재 범위가 되 고 범위 스택으로 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-105">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="e5c63-106">범위는 계층 구조를 형성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-106">Scopes must form a hierarchy.</span></span> <span data-ttu-id="e5c63-107">형제는 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-107">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c63-108">구문</span><span class="sxs-lookup"><span data-stu-id="e5c63-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5c63-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5c63-109">Parameters</span></span>  

 `scopeId`  
 <span data-ttu-id="e5c63-110">진행 범위에 대 한 범위 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-110">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="e5c63-111">진행 메서드 시작 부분부터 어휘 범위에 있는 첫 번째 명령의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-111">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="e5c63-112">진행 메서드의 시작 부분에서 어휘 범위에 있는 마지막 명령의 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-112">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5c63-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="e5c63-113">Return Value</span></span>  

 <span data-ttu-id="e5c63-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5c63-115">설명</span><span class="sxs-lookup"><span data-stu-id="e5c63-115">Remarks</span></span>  

 <span data-ttu-id="e5c63-116">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) 는와 함께 사용 하 여 `ISymUnmanagedWriter::SetScopeRange` 나중에 범위의 시작 및 끝 오프셋을 정의 하는 데 사용할 수 있는 불투명 범위 식별자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-116">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="e5c63-117">이 경우 `ISymUnmanagedWriter::OpenScope` 및 [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) 에 전달 된 오프셋은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-117">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="e5c63-118">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c63-118">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c63-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5c63-119">Requirements</span></span>  

 <span data-ttu-id="e5c63-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="e5c63-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c63-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5c63-121">See also</span></span>

- [<span data-ttu-id="e5c63-122">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5c63-122">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
