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
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615126"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="6ee80-102">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ee80-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="6ee80-103">기호 저장소 내의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="6ee80-104">이 인터페이스는 형식 관련 특성이 아닌 메서드의 기호 관련 특성에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ee80-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-105">Methods</span></span>  
  
|<span data-ttu-id="6ee80-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-106">Method</span></span>|<span data-ttu-id="6ee80-107">설명</span><span class="sxs-lookup"><span data-stu-id="6ee80-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ee80-108">GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-108">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="6ee80-109">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="6ee80-110">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-110">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="6ee80-111">문서 내의 지정 된 위치에 해당 하는이 메서드 내의 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="6ee80-112">GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-112">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="6ee80-113">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="6ee80-114">GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-114">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="6ee80-115">문서에서 위치가 지정 된 경우이 메서드 내에서 위치가 포함 되는 MSIL (Microsoft 중간 언어)의 범위에 해당 하는 시작 및 종료 오프셋 쌍의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="6ee80-116">GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-116">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="6ee80-117">이 메서드 내에서 루트 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="6ee80-118">이 범위는 전체 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="6ee80-119">GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-119">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="6ee80-120">이 메서드 내에서 지정 된 오프셋을 둘러싸는 가장 바깥쪽 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="6ee80-121">GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-121">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="6ee80-122">이 메서드 내의 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="6ee80-123">GetSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-123">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="6ee80-124">이 메서드 내의 모든 시퀀스 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="6ee80-125">GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-125">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="6ee80-126">이 메서드의 소스에 대 한 시작 및 끝 문서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="6ee80-127">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="6ee80-127">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="6ee80-128">이 메서드에 대한 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6ee80-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ee80-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ee80-129">Requirements</span></span>  
 <span data-ttu-id="6ee80-130">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6ee80-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee80-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ee80-131">See also</span></span>

- [<span data-ttu-id="6ee80-132">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ee80-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
