---
title: ISymUnmanagedDocument::GetDocumentType 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7694c9b736700466ac1299b9632440e133109288
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154078"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="01428-102">ISymUnmanagedDocument::GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="01428-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="01428-103">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01428-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01428-104">구문</span><span class="sxs-lookup"><span data-stu-id="01428-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01428-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01428-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="01428-106">[out] 문서 유형을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01428-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01428-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="01428-107">Return Value</span></span>  
 <span data-ttu-id="01428-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="01428-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01428-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="01428-109">See also</span></span>

- [<span data-ttu-id="01428-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01428-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
