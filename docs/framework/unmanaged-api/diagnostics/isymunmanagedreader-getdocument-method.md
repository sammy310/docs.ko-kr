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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939479"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="80d69-102">ISymUnmanagedReader::GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="80d69-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="80d69-103">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-103">Finds a document.</span></span> <span data-ttu-id="80d69-104">문서 언어, 공급 업체 및 형식에 대해서는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d69-105">구문</span><span class="sxs-lookup"><span data-stu-id="80d69-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80d69-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80d69-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="80d69-107">[in] 문서를 식별 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="80d69-108">[in] 문서 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-108">[in] The document language.</span></span> <span data-ttu-id="80d69-109">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="80d69-110">[in] 문서 언어에 대 한 공급 업체의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="80d69-111">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="80d69-112">[in] 문서의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-112">[in] The type of the document.</span></span> <span data-ttu-id="80d69-113">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="80d69-114">[out] 반환 되는 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80d69-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="80d69-115">Return Value</span></span>  
 <span data-ttu-id="80d69-116">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="80d69-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80d69-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80d69-117">Requirements</span></span>  
 <span data-ttu-id="80d69-118">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80d69-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d69-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="80d69-119">See also</span></span>

- [<span data-ttu-id="80d69-120">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80d69-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
