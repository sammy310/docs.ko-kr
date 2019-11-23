---
title: ISymUnmanagedReader::GetDocuments 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: c26c0a5f8c597613266e2e6d1998edfca8f17b82
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448333"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="c7f4d-102">ISymUnmanagedReader::GetDocuments 메서드</span><span class="sxs-lookup"><span data-stu-id="c7f4d-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="c7f4d-103">Returns an array of all the documents defined in the symbol store.</span><span class="sxs-lookup"><span data-stu-id="c7f4d-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7f4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7f4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7f4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7f4d-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="c7f4d-106">[in] `pDocs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c7f4d-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="c7f4d-107">[out] A pointer to a variable that receives the array length.</span><span class="sxs-lookup"><span data-stu-id="c7f4d-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="c7f4d-108">[out] A pointer to a variable that receives the document array.</span><span class="sxs-lookup"><span data-stu-id="c7f4d-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7f4d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7f4d-109">Return Value</span></span>  
 <span data-ttu-id="c7f4d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="c7f4d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7f4d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7f4d-111">Requirements</span></span>  
 <span data-ttu-id="c7f4d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c7f4d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f4d-113">참조</span><span class="sxs-lookup"><span data-stu-id="c7f4d-113">See also</span></span>

- [<span data-ttu-id="c7f4d-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7f4d-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
