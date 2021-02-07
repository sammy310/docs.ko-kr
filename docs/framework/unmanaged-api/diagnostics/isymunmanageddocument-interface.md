---
description: '자세히 알아보기: ISymUnmanagedDocument 인터페이스'
title: ISymUnmanagedDocument 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: cd1907e570dd15ebcac3ee12aa09c626c9bb7787
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710142"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="37409-103">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37409-103">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="37409-104">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37409-104">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="37409-105">문서는 URL (uniform resource locator) 및 문서 유형 GUID로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37409-105">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="37409-106">URL 및 문서 유형 GUID를 사용 하 여 문서를 저장 하는 방법에 관계 없이 문서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37409-106">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="37409-107">문서 원본을 기호 저장소에 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37409-107">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37409-108">메서드</span><span class="sxs-lookup"><span data-stu-id="37409-108">Methods</span></span>  
  
|<span data-ttu-id="37409-109">메서드</span><span class="sxs-lookup"><span data-stu-id="37409-109">Method</span></span>|<span data-ttu-id="37409-110">설명</span><span class="sxs-lookup"><span data-stu-id="37409-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37409-111">FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-111">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="37409-112">이 문서에서 시퀀스 위치가 될 수도 있고 그렇지 않을 수도 있는 줄을 지정 하 여 시퀀스 위치인 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37409-112">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="37409-113">GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-113">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="37409-114">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37409-114">Gets the checksum.</span></span>|  
|[<span data-ttu-id="37409-115">GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-115">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="37409-116">체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37409-116">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="37409-117">GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-117">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="37409-118">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37409-118">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="37409-119">GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-119">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="37409-120">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37409-120">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="37409-121">GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-121">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="37409-122">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37409-122">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="37409-123">GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-123">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="37409-124">포함 리소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37409-124">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="37409-125">GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-125">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="37409-126">포함 된 소스의 지정 된 범위를 지정 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37409-126">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="37409-127">GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-127">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="37409-128">이 문서에 대 한 URL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37409-128">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="37409-129">HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="37409-129">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="37409-130">`true`문서에 디버깅 기호에 포함 된 소스가 있으면를 반환 하 고, 그렇지 않으면를 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="37409-130">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37409-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37409-131">See also</span></span>

- [<span data-ttu-id="37409-132">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37409-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
