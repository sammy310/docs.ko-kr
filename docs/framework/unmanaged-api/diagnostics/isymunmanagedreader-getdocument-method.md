---
title: ISymUnmanagedReader::GetDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a173c23ea33532f05e30d072677715e15d04018
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093686"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="c6cc1-102">ISymUnmanagedReader::GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="c6cc1-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="c6cc1-103">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-103">Finds a document.</span></span> <span data-ttu-id="c6cc1-104">문서 언어, 공급 업체 및 형식에 대해서는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6cc1-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6cc1-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6cc1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6cc1-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="c6cc1-107">[in] 문서를 식별 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="c6cc1-108">[in] 문서 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-108">[in] The document language.</span></span> <span data-ttu-id="c6cc1-109">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="c6cc1-110">[in] 문서 언어에 대 한 공급 업체의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="c6cc1-111">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="c6cc1-112">[in] 문서의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-112">[in] The type of the document.</span></span> <span data-ttu-id="c6cc1-113">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c6cc1-114">[out] 반환 되는 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6cc1-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6cc1-115">Return Value</span></span>  
 <span data-ttu-id="c6cc1-116">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cc1-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6cc1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6cc1-117">Requirements</span></span>  
 <span data-ttu-id="c6cc1-118">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6cc1-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6cc1-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6cc1-119">See also</span></span>

- [<span data-ttu-id="c6cc1-120">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6cc1-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
