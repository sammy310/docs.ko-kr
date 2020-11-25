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
ms.openlocfilehash: 6413935df86b85a959fa4f354c6233d18baf99d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727577"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="de7b9-102">ISymUnmanagedWriter::DefineDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="de7b9-102">ISymUnmanagedWriter::DefineDocument Method</span></span>

<span data-ttu-id="de7b9-103">소스 문서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-103">Defines a source document.</span></span> <span data-ttu-id="de7b9-104">알려진 언어, 공급 업체 및 문서 형식에 대 한 Guid가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de7b9-105">구문</span><span class="sxs-lookup"><span data-stu-id="de7b9-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de7b9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de7b9-106">Parameters</span></span>  

 `url`  
 <span data-ttu-id="de7b9-107">진행 `WCHAR` 문서를 식별 하는 URL (uniform resource locator)을 정의 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="de7b9-108">진행 문서 언어를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="de7b9-109">진행 문서 언어의 공급 업체 id를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="de7b9-110">진행 문서의 형식을 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="de7b9-111">제한이 반환 된 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de7b9-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="de7b9-112">Return Value</span></span>  

 <span data-ttu-id="de7b9-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="de7b9-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de7b9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de7b9-114">Requirements</span></span>  

 <span data-ttu-id="de7b9-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="de7b9-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de7b9-116">참조</span><span class="sxs-lookup"><span data-stu-id="de7b9-116">See also</span></span>

- [<span data-ttu-id="de7b9-117">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de7b9-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
