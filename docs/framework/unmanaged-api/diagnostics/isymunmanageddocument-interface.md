---
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
ms.openlocfilehash: 83c683e1f60f13f7cee4ddc6fe5af5a94e36eb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692178"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="b6736-102">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6736-102">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="b6736-103">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="b6736-104">문서는 URL (uniform resource locator) 및 문서 유형 GUID로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="b6736-105">URL 및 문서 유형 GUID를 사용 하 여 문서를 저장 하는 방법에 관계 없이 문서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="b6736-106">문서 원본을 기호 저장소에 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6736-107">메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-107">Methods</span></span>  
  
|<span data-ttu-id="b6736-108">메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-108">Method</span></span>|<span data-ttu-id="b6736-109">설명</span><span class="sxs-lookup"><span data-stu-id="b6736-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6736-110">FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="b6736-111">이 문서에서 시퀀스 위치가 될 수도 있고 그렇지 않을 수도 있는 줄을 지정 하 여 시퀀스 위치인 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="b6736-112">GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="b6736-113">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="b6736-114">GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="b6736-115">체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="b6736-116">GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="b6736-117">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="b6736-118">GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="b6736-119">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="b6736-120">GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="b6736-121">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="b6736-122">GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="b6736-123">포함 리소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="b6736-124">GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="b6736-125">포함 된 소스의 지정 된 범위를 지정 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="b6736-126">GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="b6736-127">이 문서에 대 한 URL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="b6736-128">HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="b6736-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="b6736-129">`true`문서에 디버깅 기호에 포함 된 소스가 있으면를 반환 하 고, 그렇지 않으면를 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6736-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6736-130">참조</span><span class="sxs-lookup"><span data-stu-id="b6736-130">See also</span></span>

- [<span data-ttu-id="b6736-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6736-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
