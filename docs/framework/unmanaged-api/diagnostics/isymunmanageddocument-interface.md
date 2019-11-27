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
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449100"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="28ac3-102">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28ac3-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="28ac3-103">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="28ac3-104">문서는 URL (uniform resource locator) 및 문서 유형 GUID로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="28ac3-105">URL 및 문서 유형 GUID를 사용 하 여 문서를 저장 하는 방법에 관계 없이 문서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="28ac3-106">문서 원본을 기호 저장소에 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28ac3-107">메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-107">Methods</span></span>  
  
|<span data-ttu-id="28ac3-108">메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-108">Method</span></span>|<span data-ttu-id="28ac3-109">설명</span><span class="sxs-lookup"><span data-stu-id="28ac3-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28ac3-110">FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="28ac3-111">이 문서에서 시퀀스 위치가 될 수도 있고 그렇지 않을 수도 있는 줄을 지정 하 여 시퀀스 위치인 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="28ac3-112">GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="28ac3-113">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="28ac3-114">GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="28ac3-115">체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="28ac3-116">GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="28ac3-117">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="28ac3-118">GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="28ac3-119">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="28ac3-120">GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="28ac3-121">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="28ac3-122">GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="28ac3-123">포함 소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="28ac3-124">GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="28ac3-125">포함 된 소스의 지정 된 범위를 지정 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="28ac3-126">GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="28ac3-127">이 문서에 대 한 URL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="28ac3-128">HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="28ac3-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="28ac3-129">문서에 디버깅 기호에 포함 된 소스가 있는 경우 `true`을 반환 합니다. 그렇지 않으면 `false`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ac3-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28ac3-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28ac3-130">See also</span></span>

- [<span data-ttu-id="28ac3-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28ac3-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
