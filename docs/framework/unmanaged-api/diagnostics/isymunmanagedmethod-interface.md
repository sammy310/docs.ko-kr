---
description: '자세히 알아보기: ISymUnmanagedMethod 인터페이스'
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
ms.openlocfilehash: 18f87784a959ddc62415592e51d1971ea10f90bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709960"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="6131d-103">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6131d-103">ISymUnmanagedMethod Interface</span></span>

<span data-ttu-id="6131d-104">기호 저장소 내의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-104">Represents a method within the symbol store.</span></span> <span data-ttu-id="6131d-105">이 인터페이스는 형식 관련 특성이 아닌 메서드의 기호 관련 특성에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-105">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6131d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-106">Methods</span></span>  
  
|<span data-ttu-id="6131d-107">메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-107">Method</span></span>|<span data-ttu-id="6131d-108">설명</span><span class="sxs-lookup"><span data-stu-id="6131d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6131d-109">GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-109">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="6131d-110">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-110">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="6131d-111">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-111">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="6131d-112">문서 내의 지정 된 위치에 해당 하는이 메서드 내의 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-112">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="6131d-113">GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-113">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="6131d-114">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-114">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="6131d-115">GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-115">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="6131d-116">문서에서 위치가 지정 된 경우이 메서드 내에서 위치가 포함 되는 MSIL (Microsoft 중간 언어)의 범위에 해당 하는 시작 및 종료 오프셋 쌍의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-116">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="6131d-117">GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-117">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="6131d-118">이 메서드 내에서 루트 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-118">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="6131d-119">이 범위는 전체 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-119">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="6131d-120">GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-120">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="6131d-121">이 메서드 내에서 지정 된 오프셋을 둘러싸는 가장 바깥쪽 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-121">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="6131d-122">GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-122">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="6131d-123">이 메서드 내의 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-123">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="6131d-124">GetSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-124">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="6131d-125">이 메서드 내의 모든 시퀀스 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-125">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="6131d-126">GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-126">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="6131d-127">이 메서드의 소스에 대 한 시작 및 끝 문서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-127">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="6131d-128">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="6131d-128">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="6131d-129">이 메서드에 대한 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6131d-129">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6131d-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6131d-130">Requirements</span></span>  

 <span data-ttu-id="6131d-131">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6131d-131">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6131d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6131d-132">See also</span></span>

- [<span data-ttu-id="6131d-133">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6131d-133">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
