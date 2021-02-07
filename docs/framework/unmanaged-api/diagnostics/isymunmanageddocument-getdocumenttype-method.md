---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetDocumentType 메서드'
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
ms.openlocfilehash: cf2ceffccb33eb7cba0d45af203e12d1e4244f60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710324"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="ecae0-103">ISymUnmanagedDocument::GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="ecae0-103">ISymUnmanagedDocument::GetDocumentType Method</span></span>

<span data-ttu-id="ecae0-104">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ecae0-104">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecae0-105">구문</span><span class="sxs-lookup"><span data-stu-id="ecae0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecae0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecae0-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="ecae0-107">제한이 문서 유형을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ecae0-107">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecae0-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="ecae0-108">Return Value</span></span>  

 <span data-ttu-id="ecae0-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecae0-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecae0-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecae0-110">See also</span></span>

- [<span data-ttu-id="ecae0-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecae0-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
