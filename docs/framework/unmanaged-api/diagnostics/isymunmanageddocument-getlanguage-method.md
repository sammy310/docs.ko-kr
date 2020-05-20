---
title: ISymUnmanagedDocument::GetLanguage 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
ms.openlocfilehash: 084f3ae12d906f5e80fdb86e65b09d2371fd246b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614593"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="ea04f-102">ISymUnmanagedDocument::GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="ea04f-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="ea04f-103">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea04f-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea04f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea04f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea04f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea04f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ea04f-106">제한이 언어 식별자를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ea04f-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea04f-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="ea04f-107">Return Value</span></span>  
 <span data-ttu-id="ea04f-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea04f-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea04f-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea04f-109">See also</span></span>

- [<span data-ttu-id="ea04f-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea04f-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
