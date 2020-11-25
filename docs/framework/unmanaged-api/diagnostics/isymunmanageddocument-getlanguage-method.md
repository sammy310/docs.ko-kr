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
ms.openlocfilehash: 075d46b0bbc68add0203daf7430afb712c998fe0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700979"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="191f7-102">ISymUnmanagedDocument::GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="191f7-102">ISymUnmanagedDocument::GetLanguage Method</span></span>

<span data-ttu-id="191f7-103">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="191f7-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="191f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="191f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="191f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="191f7-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="191f7-106">제한이 언어 식별자를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="191f7-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="191f7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="191f7-107">Return Value</span></span>  

 <span data-ttu-id="191f7-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="191f7-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191f7-109">참조</span><span class="sxs-lookup"><span data-stu-id="191f7-109">See also</span></span>

- [<span data-ttu-id="191f7-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="191f7-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
