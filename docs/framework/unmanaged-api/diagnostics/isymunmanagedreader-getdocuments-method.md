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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efcf5b6673fbdc37fad99d082f91ab3077abbea9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130600"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="00e74-102">ISymUnmanagedReader::GetDocuments 메서드</span><span class="sxs-lookup"><span data-stu-id="00e74-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="00e74-103">기호 저장소에 정의 된 모든 문서의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00e74-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e74-104">구문</span><span class="sxs-lookup"><span data-stu-id="00e74-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00e74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00e74-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="00e74-106">[in] `pDocs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="00e74-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="00e74-107">[out] 배열 길이 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="00e74-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="00e74-108">[out] 문서 배열을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="00e74-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00e74-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="00e74-109">Return Value</span></span>  
 <span data-ttu-id="00e74-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="00e74-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00e74-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00e74-111">Requirements</span></span>  
 <span data-ttu-id="00e74-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="00e74-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e74-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="00e74-113">See also</span></span>

- [<span data-ttu-id="00e74-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00e74-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
