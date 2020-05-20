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
ms.openlocfilehash: b8a3a74888a3caae03da6f88a003bd277939ae59
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615048"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="5f838-102">ISymUnmanagedReader::GetDocuments 메서드</span><span class="sxs-lookup"><span data-stu-id="5f838-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="5f838-103">기호 저장소에 정의 된 모든 문서의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f838-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f838-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f838-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f838-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f838-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="5f838-106">[in] `pDocs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5f838-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="5f838-107">제한이 배열 길이를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f838-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="5f838-108">제한이 문서 배열을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f838-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f838-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="5f838-109">Return Value</span></span>  
 <span data-ttu-id="5f838-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5f838-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f838-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f838-111">Requirements</span></span>  
 <span data-ttu-id="5f838-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5f838-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f838-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f838-113">See also</span></span>

- [<span data-ttu-id="5f838-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f838-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
