---
title: ISymUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448789"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="d8af4-102">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8af4-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="d8af4-103">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="d8af4-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="d8af4-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span><span class="sxs-lookup"><span data-stu-id="d8af4-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8af4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-105">Methods</span></span>  
  
|<span data-ttu-id="d8af4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-106">Method</span></span>|<span data-ttu-id="d8af4-107">설명</span><span class="sxs-lookup"><span data-stu-id="d8af4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8af4-108">GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="d8af4-109">Gets the namespace within which this method is defined.</span><span class="sxs-lookup"><span data-stu-id="d8af4-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="d8af4-110">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="d8af4-111">Returns the offset within this method that corresponds to a given position within a document.</span><span class="sxs-lookup"><span data-stu-id="d8af4-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="d8af4-112">GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="d8af4-113">Gets the parameters for this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="d8af4-114">GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="d8af4-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="d8af4-116">GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="d8af4-117">Gets the root lexical scope within this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="d8af4-118">This scope encloses the entire method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="d8af4-119">GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="d8af4-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span><span class="sxs-lookup"><span data-stu-id="d8af4-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="d8af4-121">GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="d8af4-122">Gets the count of sequence points within this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="d8af4-123">GetSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="d8af4-124">Gets all the sequence points within this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="d8af4-125">GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="d8af4-126">Gets the start and end document positions for the source of this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="d8af4-127">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d8af4-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="d8af4-128">Returns the metadata token for this method.</span><span class="sxs-lookup"><span data-stu-id="d8af4-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8af4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8af4-129">Requirements</span></span>  
 <span data-ttu-id="d8af4-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8af4-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8af4-131">참조</span><span class="sxs-lookup"><span data-stu-id="d8af4-131">See also</span></span>

- [<span data-ttu-id="d8af4-132">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8af4-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
