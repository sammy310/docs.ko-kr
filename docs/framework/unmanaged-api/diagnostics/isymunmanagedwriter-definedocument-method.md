---
description: ISymUnmanagedWriter::D efineDocument 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 35e918292e6ee50e17932645e003d19513e2397a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762541"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="dfa25-103">ISymUnmanagedWriter::DefineDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="dfa25-103">ISymUnmanagedWriter::DefineDocument Method</span></span>

<span data-ttu-id="dfa25-104">소스 문서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-104">Defines a source document.</span></span> <span data-ttu-id="dfa25-105">알려진 언어, 공급 업체 및 문서 형식에 대 한 Guid가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-105">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfa25-106">구문</span><span class="sxs-lookup"><span data-stu-id="dfa25-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfa25-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dfa25-107">Parameters</span></span>  

 `url`  
 <span data-ttu-id="dfa25-108">진행 `WCHAR` 문서를 식별 하는 URL (uniform resource locator)을 정의 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-108">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="dfa25-109">진행 문서 언어를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-109">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="dfa25-110">진행 문서 언어의 공급 업체 id를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-110">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="dfa25-111">진행 문서의 형식을 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-111">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dfa25-112">제한이 반환 된 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-112">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfa25-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="dfa25-113">Return Value</span></span>  

 <span data-ttu-id="dfa25-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa25-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfa25-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfa25-115">Requirements</span></span>  

 <span data-ttu-id="dfa25-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="dfa25-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa25-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfa25-117">See also</span></span>

- [<span data-ttu-id="dfa25-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfa25-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
