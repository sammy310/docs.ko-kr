---
title: ISymUnmanagedWriter::DefineDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: 02b270677131d0960db67b0ac8db38cba2b5e2df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428049"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="06acb-102">ISymUnmanagedWriter::DefineDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="06acb-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="06acb-103">소스 문서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-103">Defines a source document.</span></span> <span data-ttu-id="06acb-104">알려진 언어, 공급 업체 및 문서 형식에 대 한 Guid가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06acb-105">구문</span><span class="sxs-lookup"><span data-stu-id="06acb-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06acb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06acb-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="06acb-107">진행 문서를 식별 하는 URL (uniform resource locator)을 정의 하는 `WCHAR`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="06acb-108">진행 문서 언어를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="06acb-109">진행 문서 언어의 공급 업체 id를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="06acb-110">진행 문서의 형식을 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="06acb-111">제한이 반환 된 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06acb-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="06acb-112">Return Value</span></span>  
 <span data-ttu-id="06acb-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="06acb-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06acb-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06acb-114">Requirements</span></span>  
 <span data-ttu-id="06acb-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="06acb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06acb-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="06acb-116">See also</span></span>

- [<span data-ttu-id="06acb-117">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06acb-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
