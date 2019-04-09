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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ce47953358b7025e30080fbbaf288a6c0e879d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104599"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="f7c63-102">ISymUnmanagedDocument::GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="f7c63-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="f7c63-103">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f7c63-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c63-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7c63-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c63-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7c63-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f7c63-106">[out] 언어 식별자를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c63-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7c63-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f7c63-107">Return Value</span></span>  
 <span data-ttu-id="f7c63-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c63-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c63-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7c63-109">See also</span></span>

- [<span data-ttu-id="f7c63-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7c63-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
