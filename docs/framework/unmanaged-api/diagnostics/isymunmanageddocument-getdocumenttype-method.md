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
ms.openlocfilehash: 5ec69aa06816b117fb05853001e59532629504c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614606"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="221ff-102">ISymUnmanagedDocument::GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="221ff-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="221ff-103">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="221ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="221ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="221ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="221ff-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="221ff-106">제한이 문서 유형을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="221ff-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="221ff-107">Return Value</span></span>  
 <span data-ttu-id="221ff-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="221ff-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221ff-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="221ff-109">See also</span></span>

- [<span data-ttu-id="221ff-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="221ff-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
