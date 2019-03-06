---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42c677ae5aeb1e1b70ab68be8920fc71215cfe63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471997"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="133a0-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="133a0-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="133a0-103">줄에는이 메서드는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="133a0-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="133a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="133a0-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="133a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="133a0-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="133a0-106">[in] 가리키는 버퍼의 길이 `pcDocs`입니다.</span><span class="sxs-lookup"><span data-stu-id="133a0-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="133a0-107">[out] 에 대 한 포인터를 `ULONG32` 문자 문서를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="133a0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="133a0-108">[in] 문서를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="133a0-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="133a0-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="133a0-109">Return Value</span></span>  
 <span data-ttu-id="133a0-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="133a0-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="133a0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="133a0-111">Requirements</span></span>  
 <span data-ttu-id="133a0-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="133a0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133a0-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="133a0-113">See also</span></span>
- [<span data-ttu-id="133a0-114">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="133a0-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
